# Platform mapping: Klaviyo

**Platform:** Klaviyo
**Mapping version:** 1.1
**Tools/endpoints assumed:** Klaviyo MCP server (remote, OAuth; exposes ~200 tools and supports a read-only configuration) or the Klaviyo REST API, revision `2026-07-15`, with a private key limited to read scopes. Tool names below follow the MCP server's catalog; REST paths are given where they matter.
**Last verified:** 2026-08-17 against documentation. The items marked **(live 2026-09)** were verified against the claude.ai Klaviyo connector on two accounts, 2026-09-10 to 24. **Everything else is UNVERIFIED AGAINST LIVE CONNECTOR:** treat those tool names and fields as indicative. At the start of a live audit, list the tools actually present in the session and adapt; if a named tool or field is missing, downgrade the affected rules to UNVERIFIABLE rather than guessing.

If the session's Klaviyo connector offers a read-only mode, prefer it.

---

## Connector and session (live 2026-09)

- The connector's name in claude.ai doesn't identify the account; one name was re-pointed to another account. Call `get_account_details` first and confirm the account before any pull.
- Many tools are deferred: load their schemas before calling them. Some need a hidden `model` parameter.
- Large results (profile pages, event pages) exceed the tool-result display and land in files: parse them with a script. A 100-profile page with subscriptions is about 150 KB; dropping `properties` from `fields[profile]` shrinks it.
- Profile counts drift within a day (checkouts create profiles): give every count a pull time.

---

## Per-step evidence map

### Step 1: Identify (rules 1.2, 1.3, 1.5b)
Read:
- `get_campaigns` (REST `GET /api/campaigns`, channel filter required: `filter=equals(messages.channel,'email')`), include `campaign-messages`. Gives the recent send list for the 1.2 content-mix tally and the 1.3 goal classification. Message content (subject, body) via `get_campaign_message` and the assigned template.
- `get_flows` with `include=flow-actions` for the flow inventory: 1.3 checks whether the top-ranked B1 goal has a dedicated flow at all. Per-email content via `get_flow_message` and `get_email_template`.
- Fields that matter: campaign `send_time`, `status` (grade sent campaigns, not drafts), message subject/preview and body content.
Gaps: none material. Content lives in messages and templates; pull 10-20 most recent sent items across both objects, don't cherry-pick.

### Step 2: The Flow (rules 2.1, 2.2, 2.3, 2.4, 2.5, 2.6, 2.7)
Read:
- 2.1/2.2 (unsubscribe): template HTML via `get_email_template` / `list_email_templates`; footer unsubscribe link presence, wording, styling are visible in the HTML. The rendered destination (Klaviyo-hosted unsubscribe/preference page) is NOT exposed through the API. If the session can fetch URLs, follow the link from one real email; otherwise ask the user to click it and describe, else UNVERIFIABLE. The hosted pages' text (not their rendering) is readable as a translation collection, `consent-page::web::$all`, one page at a time with `get_translation` and `page_type` (live 2026-09).
- 2.3 (entry protection): `get_lists` (REST `GET /api/lists`), field `opt_in_process`: `single_opt_in` or `double_opt_in`, per list. `get_forms` / `get_form` for signup forms (`status`, `ab_test`, `created_at`, `updated_at`) and `get_form_version` for versions. Combine with C3 answers. `get_form` returns the full definition: steps, blocks, hidden `$source` fields, triggers, URL rules, teaser. The top-level `status` can read draft while the live version is live: read the version's status. `updated_at` stays equal to `created_at` after editor edits, so it is not a last-edited signal (live 2026-09).
- 2.4 (declared vs observed): `get_flows`: `trigger_type` (`Added to List`, `Metric`, `Date Based`, `Price Drop`, `Low Inventory`, `Unconfigured`), `status`, `archived`. `get_flows_triggered_by_list` / `get_flows_triggered_by_segment` to see what entering a list or segment actually starts. Compare against the B4 walk-through. `get_flows` with `include=flow-actions` returns the actions inline, under `relationships.flow-actions.data[].attributes.definition`, not in `included`. Trigger, flow filter and re-entry come from `get_flow` with `additional_fields_flow=definition`; `reentry_criteria` was missing on most flows, so re-entry is UNVERIFIABLE through the API: ask for a screenshot (live 2026-09).
- 2.5 (commodity/journey shape): flow length and first-emails content via `flow-actions` and flow messages.
- 2.6 (consent): profile-level consent evidence: `get_profiles` with `additional-fields[profile]=subscriptions`, object `subscriptions.email.marketing`: `consent`, `consent_timestamp`, `can_receive_email_marketing`. No tool creates a bulk export job (only the get and download tools exist), so full-population consent counts come from paginated `get_profiles`. Its filters don't support consent, and only one timestamp filter is accepted per call. The metrics `Subscribed to Email Marketing`, `Unsubscribed from Email Marketing` and `Manually Suppressed from Email Marketing` carry `method` (e.g. `INTEGRATION_SHOPIFY`, `BOT_PROTECTION`) and `method_detail` (e.g. `Historical Sync`): reading them by day shows whether live consent sync works. `query_metric_aggregates` with `by: ["Method"]` returned one blank dimension; read the events (live 2026-09).
- 2.7 (churn visibility): `get_flow_report` (REST `POST /api/flow-values-reports`) and `get_campaign_report` (REST `POST /api/campaign-values-reports`): `unsubscribe_rate`, `spam_complaint_rate` per flow and per campaign show where in the lifecycle people leave.
Gaps: the API does not expose the signup form's anti-bot configuration (captcha and similar) in a documented field; the form-version schema is not fully documented. Ask the user or inspect the live form. The unsubscribe click-path beyond the link itself is not exposed.

### Step 3: Sync (rules 3.1 advisory, 3.2, 3.3, 3.5)
Read:
- 3.1 (reply path): from-address and reply-to on campaign message content and flow message content; "do not reply" language in body HTML.
- 3.2 (message-type skeleton): classify the flow inventory by `trigger_type` plus the campaign list: transactional and lifecycle sends are flows triggered by metrics or list joins; broadcasts are campaigns. Grade skeleton presence against B4. `get_applications` lists installable marketplace apps, not the account's integrations. No read tool exposes the Shopify integration settings (subscriber sync, target list): they are UNVERIFIABLE without a screenshot. The only sync liveness signals are `get_metrics`' `integration` field and `get_events`' `$extra.webhook_topic` (live 2026-09).
- 3.3 (channel-exclusive value): email content from templates vs the user's public channels. The public-channel side lives outside Klaviyo: fetch the blog or feed if the session has web access, else ask for one example, else UNVERIFIABLE.
- 3.5 (send rationale): campaign history for the last 60-90 days: `get_campaigns` filtered to sent email campaigns, with `audiences` and message content per campaign.
Gaps: none beyond the external evidence 3.3 needs by design.

### Step 4: Define (rules 4.1-4.8)
Read:
- The email under review: subject and preview via `get_campaign_message` / `get_flow_message`; full HTML via `get_email_template`; `render_email_template` to check personalization output where template variables obscure the copy.
- 4.4 (landing page continuity): CTA destination URLs are extractable from template HTML; the page itself is outside Klaviyo. Fetch the URL if the session allows, else ask for a screenshot, else UNVERIFIABLE.
- 4.6 (CTA discipline): button vs image-link construction is visible in the HTML; `tracking_options` on the campaign shows click tracking and UTM handling.
- 4.8 (one email, one audience): campaign `audiences.included` / `audiences.excluded` (list and segment IDs; resolve names via `get_list` / `get_segment`). Full-list sends against multiple declared personas are read directly from this field.
Gaps: none material for pasted or fetched emails.

### Step 5: Code and Test (rules 5.1, 5.3; 5.2 is asked, not read)
Read:
- 5.1 (renders without images): template HTML from `get_email_template`: alt text on meaningful images, text or bulletproof-button CTA, image-only construction.
- 5.3 (broken mechanics): links extracted from HTML, spot-checked where the session can fetch; unrendered placeholder patterns checked via `render_email_template` output. Coupons: `get_coupons` doesn't list Shopify coupons created in Klaviyo's UI, and `render_email_template` fails with 400 for templates that use them. Verify coupons in the UI (live 2026-09).
- 5.2 (QA process) is a user question in the evidence phase; Klaviyo has no object for it.
Gaps: actual client rendering (Outlook, Gmail clipping) is not exposed by any endpoint; grade from HTML structure and mark client behavior UNVERIFIABLE.

### Step 6: Dynamic Automated User Segments (rules 6.1, 6.2, 6.3)
Read:
- `get_lists` and `get_segments` for the full audience inventory. In Klaviyo the object type IS the static/dynamic distinction: lists are static membership, segments are rule-based and auto-updating. That maps directly onto 6.2.
- Segment definitions: `get_segment` with `fields[segment]=definition,definition.condition_groups` exposes the actual rule logic. 6.3 checks whether any active segment's conditions key on engagement (opened, clicked, active on site, recency windows) rather than attributes only.
- Segment activity fields: `is_active`, `is_processing`, `is_starred`, `created`, `updated`.
- What gates sending: campaign `audiences` (which segments are actually used, and whether any appear in `excluded`) and `get_flows_triggered_by_segment`.
- `query_segment_values` / `query_segment_series` for membership size and growth where useful. `get_segments` returns no count; one `query_segment_values` call with `any(segment_id,[...])` and `total_members` sizes the whole inventory (live 2026-09).
- Condition types seen (live 2026-09): `profile-metric` (with `measurement_filter`, `timeframe_filter`, optional `metric_filters`), `profile-group-membership`, `profile-marketing-consent` (`can_receive_marketing`, subscription any / subscribed / never_subscribed), predictive `historic_clv`. Groups AND together; conditions inside a group OR. Metric ids are opaque: resolve them with `get_metrics`.
- Segment conditions can use `properties['$locale_language']` and `$locale_country`, derived from the profile's `locale`; they never appear in profile `properties` (live 2026-09).
Gaps: none material; this is the best-instrumented step in Klaviyo. Catalog tools cover only the `$custom` integration: Shopify-synced products are never returned, so an empty catalog read is not evidence of an empty catalog (live 2026-09).

### Step 7: Send and Deliver (rules 7.1, 7.2, 7.3, 7.4)
Read:
- 7.1 (authentication): `get_sending_domains` exists and works (live 2026-09). An empty array means no dedicated sending domain (Klaviyo's shared domain). A dynamic (NS-delegated) domain reports `status: active` while every `dns_records` entry says `verified: false`: trust `status`. For SPF/DKIM/DMARC, check DNS if the session has shell or web tools: `dig` returns nothing inside a Claude Code sandbox, so use DNS-over-HTTPS (dns.google JSON). Else UNVERIFIABLE, stating that a DNS check of the sending domain would resolve it.
- 7.2 (volume concentration): per-campaign `audiences` joined with `get_campaign_report` recipient counts over 60-90 days: what share of volume went to audiences with no engagement condition in their definition (cross-check the 6.3 segment analysis). Trajectory, not threshold. Volume and plan: `get_billing_usage` and `list_billing_usage` exist. Billing "active profiles" are profiles with an email and no email suppression; never-subscribed profiles count. The API shows caps, not the plan's name or price (live 2026-09).
- 7.3 (transactional/marketing separation): sending infrastructure (dedicated IPs, subdomains) is account configuration not exposed by the public API. Ask the user; grade only at evident scale.
- 7.4 (bounce and complaint hygiene): suppression evidence on profiles: `subscriptions.email.marketing.suppression` with reasons `HARD_BOUNCE`, `INVALID_EMAIL`, `SPAM_COMPLAINT`, `UNSUBSCRIBE`, `USER_SUPPRESSED`. There is no `list_suppressions` tool: suppression evidence is on each profile (live 2026-09). Klaviyo suppresses hard bounces automatically on its own sending; the finding to look for is circumvention (imports re-adding suppressed addresses) or hybrid sending outside Klaviyo. Complaint rate via the reporting endpoints.
Gaps: DNS records' own verification state (see 7.1), infrastructure inventory, mailbox-provider placement data (Klaviyo has no seed-list or placement endpoint; Gmail Postmaster and similar are outside the platform).

### Step 8: Analyze and Learn (rules 8.1, 8.2)
Read:
- 8.2 (metrics watched vs goals): what the platform CAN measure, to compare against what the user says they watch: `get_campaign_report` / `get_flow_report` statistics include opens, clicks, `open_rate`, `click_rate`, `click_to_open_rate`, `delivered`, `bounced`, `bounce_rate`, `spam_complaint_rate`, `unsubscribe_rate`, and conversion statistics (`conversions`, `conversion_value`, `revenue_per_recipient`, `average_order_value`). Conversion tracing to the A3 event: `get_metrics` / `get_metric` for the tracked events (for example Placed Order) and `query_metric_aggregates` for their history. If the user's A3 conversion event exists nowhere in `get_metrics`, that absence is the 8.2 evidence.
- `query_metric_aggregates` (live 2026-09): the range is capped at one year. Bucket labels are UTC instants of local midnight, and the first bucket can be extra or partial: anchor tables on local dates. `by: ["Message Type"]` on Received Email returns blank for flows and "campaign" for campaigns. Shopify `Ordered Product` emits one event per unit, not per line item, and aggregates can't group it by product.
- Attributed revenue (live 2026-09): on Klaviyo's default window (an open or a click within 5 days, Apple's automatic opens included) it can read far above the store's own email referrer share. Report both, each defined.
- 8.1 (testing tests something) is primarily a user question. Forms expose an `ab_test` flag; campaign-level A/B configuration is not clearly documented. Do not infer testing activity from the API alone.
- Apply the open-rate reliability caveat from rule 8.2 when Apple MPP inflation is relevant; Klaviyo reports opens as recorded, it does not separate machine opens.
Gaps: campaign A/B detail, historical test decisions (no platform object records what a test changed).

### Step 9: Iterate and Improve (rules 9.1, 9.2)
Read:
- 9.2 (the loop loops): `get_flows` fields `created` and `updated` are the last-edited proxy per flow; campaign `updated_at` likewise. Weak evidence: `updated` can move on status toggles, not only meaningful edits. Corroborate with the user's answer to "when did data last change a flow" before grading.
- 9.1 (learnings have a home) is a user question; no platform object.
Gaps: no edit history or changelog is exposed, only the latest timestamps.

---

## Read-only contract

The skill never mutates a connected Klaviyo account. Forbidden, without exception, even if the user asks mid-audit (point them to build modes, which output specs they apply themselves):

- Any tool or endpoint whose name starts with `create_`, `update_`, `delete_`, `bulk_`, `upload_`, `merge_`, `assign_`, `tag_`, `subscribe_`, `unsubscribe_`, `send_`, `cancel_`, `refresh_`.
- Explicitly including: `create_campaign`, `update_campaign`, `delete_campaign`, `send_campaign`, `create_campaign_clone`, `assign_template_to_campaign_message`, `create_flow`, `update_flow`, `delete_flow`, `update_flow_action`, `create_segment`, `update_segment`, `delete_segment`, `create_list`, `update_list`, `delete_list`, `add_profiles_to_list`, `remove_profiles_from_list`, `create_profile`, `update_profile`, `create_or_update_profile`, `subscribe_profile_to_marketing`, `unsubscribe_profile_from_marketing`, `bulk_suppress_profiles`, `bulk_unsuppress_profiles`, `bulk_import_profiles`, `merge_profiles`, `request_profile_deletion`, `create_event`, `bulk_create_events`, `create_email_template`, `update_email_template`, `delete_email_template`, `clone_email_template`, `create_form`, `delete_form`, `create_tag`, `delete_webhook`, and every catalog, coupon, image, brand, translation, or sending-domain mutation.
- `create_template_preview_send_job` sends mail; it is forbidden despite the word "preview."

Allowed despite the POST verb, because they are queries: the reporting endpoints (`POST /api/campaign-values-reports`, `POST /api/flow-values-reports`, form and segment series/values queries) and `query_metric_aggregates`. They read aggregates; they change nothing.

Rate-limit courtesy: profile reads with `additional-fields[profile]=predictive_analytics` carry reduced limits. Request them only when per-buyer spend is needed and no store export exists. `historic_number_of_orders` is null, not 0, for non-buyers, and predicted fields were empty on accounts below Klaviyo's eligibility (live 2026-09).

## Naming quirks

- **List vs segment:** a Klaviyo "list" is static membership (people join via form, import, or API). A "segment" is a dynamic rule that re-evaluates automatically. When the method says "dynamic segment," Klaviyo's segment is the native equivalent; a list doing a segment's job is exactly rule 6.2's finding.
- **Flow vs campaign:** "flow" is a triggered automation sequence; "campaign" is a one-off broadcast. The method's "journey" maps to flows, "broadcast" to campaigns.
- **Suppression vs unsubscribe:** Klaviyo suppression is the umbrella state (reasons: unsubscribe, hard bounce, spam complaint, user-suppressed, invalid email). An "unsubscribed" profile is one suppression reason among five. Read the reason field, not just the state.
- **Audiences:** on a campaign, `audiences.included`/`excluded` hold list and segment IDs, not names; resolve them before reporting.
- **Smart Sending:** a per-campaign/flow `send_options` setting that skips recently-messaged profiles. Its presence or absence is evidence for 7.2, not a method rule either way.
- **Metrics:** Klaviyo calls tracked event types "metrics" (Placed Order, Opened Email). The reporting statistics (open rate and so on) are computed over these. "Metric" in Klaviyo docs usually means the event type, not the KPI.
