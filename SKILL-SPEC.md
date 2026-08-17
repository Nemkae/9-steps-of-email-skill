# SKILL-SPEC: 9 Steps of Email

Design record. Everything here was decided in the design phase; Code implements, does not redesign. If something is missing or contradictory, stop and list it for the owner rather than improvising.

## 1. One-liner
The 9 Steps of Email method, applied. Auditing existing systems and building new components are the same rules pointed in two directions. The skill does not know the user's ideal email system; it checks whether theirs is the system they think it is, and builds from what they declared.

## 2. Positioning (drives README, description, all copy)
- Connectors give Claude hands. This skill gives it judgment.
- Grades coherence, not compliance: the standard is the user's own declaration plus a small set of universal structural rules.
- No benchmarks, no thresholds, no scores. Explicit non-findings.
- 2013 origin is the argument for stability, not a heritage claim.
- Read-only always. Won't write blind.

## 3. Components (final files in this bundle)
| File | Status | Code's job |
|---|---|---|
| `skill/SKILL.md` | Near-final draft | Verify frontmatter description triggers correctly; keep under 500 lines; do not rewrite principles or rules |
| `skill/references/intake.md` | Final | Drop in as-is |
| `skill/references/grading-rules.md` | Final | Drop in as-is; fill the "last verified" date in 7.1 |
| `skill/references/paste-mode.md` | Final | Drop in as-is |
| `skill/references/pre-send-checklist.md` | Final | Drop in as-is |
| `skill/assets/audit-report-template.md` | Final | Drop in as-is; fill repo URL in footer |
| `skill/references/klaviyo.md` | Not written | Code writes from Klaviyo's actual MCP/API surface, see §6 |
| `README.md` | Draft | Fill install paths after verifying current UI; owner fills license |
| `CHANGELOG.md` | Not written | Code creates, v1.0.0 entry |
| `LICENSE` | Not written | Owner decision, see README |
| `examples/example-audit.md` | Not written | Deferred to v1.1 (owner produces from a fictional account) |

## 4. Finding taxonomy (binding)
- STRUCTURAL: universal method rule. Binary.
- COHERENCE: observed vs declared. Core type.
- FIT: valid choice vs declared context.
- ADVISORY: recommended, not required, own report section, no severity, no verdict weight.
- UNVERIFIABLE: first-class outcome, always states what evidence would resolve.
Every finding traces: type + step + graded-against + evidence. Every built element carries a trace block.

## 5. Modes (binding)
- Full audit: Phase 0 mode detection, Phase 1 intake, Phase 2 evidence, Phase 3 grading (structural, coherence, fit; then Section 0), Phase 4 report.
- Quick: DRAFT REVIEW, ACME/EMCA TEST (marker scan only), PRE-SEND CHECK.
- Build: EMAIL, FLOW, SEGMENT, CAMPAIGN. Precondition: declaration (full or short intake).

## 6. Platform mapping file spec (`references/<platform>.md`)
Purpose: tell the model where each step's evidence lives in a given platform. Structure per file:
- Header: platform, mapping version, tools/endpoints assumed, last verified date.
- Per step, 1-9: which objects to read (flows, campaigns, segments, lists, forms, metrics), which fields answer which rule IDs, known gaps (what the platform doesn't expose).
- Read-only reminder and any calls that must NOT be made (anything mutating).
- Naming quirks (e.g. what the platform calls a "list" vs a "segment").
Klaviyo ships in v1.0. Code writes it from Klaviyo's real tool surface as exposed in the current MCP/connector, not from memory. If the surface can't be verified, write the file as "generic inventory, unverified" and flag for the owner.
Do NOT write a Bento mapping for the public repo.

## 7. Locked decisions (do not reopen)
- Separate public repo, not a subfolder of the site repo.
- No email generation without a declaration.
- Read-only against connected accounts, no exceptions.
- No thresholds, benchmarks, numeric scores. Section 0's marker-count verdict logic is the only quasi-numeric rule and is internal classification, not a user-facing benchmark.
- MECLABS notation stripped everywhere; credit line in README only.
- 3.1 reply path is ADVISORY, not structural.
- ESP list in description: Klaviyo, Drip, ActiveCampaign, Kit, Beehiiv, Braze, HubSpot, Salesforce, Mailchimp. Bento excluded from public copy.
- Checklist: MD in repo is the working artifact; branded PDF on site is canonical, formula-free in its next regeneration.
- Model recommendation is a README line, generic ("most capable available"), never a specific model name.
- Steps 5-9 rules are v1 depth, marked honestly, expand with articles.

## 8. Voice
Direct, second person, technically precise, no em dashes, no filler, no marketing-blog cadence. Findings state the structural consequence, never a character judgment. Refusals are one line plus an alternative.

## 9. Owner TODOs (not Code's)
- License choice.
- Regenerate the site checklist PDF from `pre-send-checklist.md`, formula-free; upload to R2 (existing TODO).
- Publish Steps 5-9 articles; on each, add the deep link in the report template and bump the rules file.
- Produce `examples/example-audit.md` from a fictional ACME-posture account (v1.1).
- Launch content: LinkedIn post (connectors give hands / skill gives judgment), Reddit r/emailmarketing post leading with a sample report, submissions to awesome-claude-skills lists.
