# Changelog

## v1.1.0 (unreleased)

- Klaviyo mapping 1.1: 22 corrections verified against the claude.ai Klaviyo connector on two live accounts, 2026-09-10 to 24, each marked "(live 2026-09)"; everything else stays marked unverified
- New "Connector and session" section: confirm the account with `get_account_details` first, deferred tools, large results, counts that drift within a day
- Corrected: `get_sending_domains` works (was "beta, may be absent"); `list_suppressions` and bulk export jobs don't exist; consent counts come from paginated `get_profiles`; predictive analytics may be requested when no store export exists
- Added read facts for forms, flow definitions and re-entry, consent metrics, consent page text, integrations, segment sizing and conditions, catalog, billing, metric aggregates, attributed revenue, coupons

## v1.0.0 (2026-08-17)

First public release.

- Full audit: mode detection (live/paste), intake as a saved system declaration, evidence phase, grading Steps 1-9, report from template
- Finding taxonomy: STRUCTURAL, COHERENCE, FIT, plus ADVISORY entries and UNVERIFIABLE as a first-class outcome; every finding traces to type, step, standard, and evidence
- Section 0 ACME/EMCA posture assessment, marker-based, no numeric scoring
- Quick modes: draft review, ACME/EMCA marker scan, interactive pre-send check
- Build modes: email, flow, segment, campaign; all require a declaration (full intake or the seven-question short intake) and output drafts with trace blocks
- Grading rules: Steps 1-4 at published-article depth; Steps 5-9 at v1 outline depth, marked as such in the rules file
- Paste mode evidence protocol (six items) for sessions with no connected ESP
- Pre-send checklist, working markdown version
- Audit report template with step article links for Steps 1-4
- Klaviyo platform mapping, sourced from Klaviyo's public API and MCP server documentation (revision 2026-07-15); unverified against a live connector
- Read-only against connected accounts, no exceptions
