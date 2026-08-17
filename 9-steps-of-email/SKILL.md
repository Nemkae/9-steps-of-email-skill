---
name: 9-steps-of-email
description: Audit, grade, and build email marketing systems using the 9 Steps of Email method (est. 2013, tool-agnostic). Use whenever the user wants their email marketing audited, reviewed, or graded; asks whether their email program, flows, segments, or opt-in process are set up well; pastes an email draft for review; asks for a pre-send check; wants to build or plan an email, campaign, flow, or segment against a method; mentions auditing or working with a Klaviyo, Drip, ActiveCampaign, Kit, Beehiiv, Braze, HubSpot, Salesforce, Mailchimp, or other ESP/CRM account; or asks why their email results are declining. Also use for ACME vs EMCA assessment of emails or campaign plans. This skill grades against the user's declared intent and the method's structural rules; it never benchmarks against industry averages and it will not write emails without a system declaration.
---

# 9 Steps of Email

The 9 Steps of Email method (9steps.email), applied. Auditing existing systems and building new components are the same rules pointed in two directions.

The skill does not know the user's ideal email system. It checks whether their system is the system they think it is, and when it builds, it builds from what they declared.

## Operating principles

1. **Three finding types, plus advisories.**
   - STRUCTURAL: violates a universal method rule. Rare, non-negotiable.
   - COHERENCE: observed system contradicts the user's own declared intent from intake. The core finding type.
   - FIT: a choice that is valid in general but mismatched to the user's declared context (funnel length, margin, jurisdiction, resources).
   - ADVISORY: something the method recommends but does not require. Not a finding. No severity, no verdict weight, own report section.
2. **Every finding traces.** Finding type + step + what it was graded against (rule / user's declaration / user's context) + evidence observed. No untraceable findings. Every built element carries a trace block: the same discipline, inverted.
3. **Read-only, always.** Never modify flows, segments, templates, or settings in a connected account, even if asked. Build modes output drafts, specs, and definitions as text or files; the user applies them.
4. **No benchmarks, no thresholds.** Never grade against industry averages or invented numbers. Send frequency is observed, never prescribed. "Is 20% open rate good" is a coherence question: good for what declared goal?
5. **No declaration, no build.** The skill will not write blind. Generation is constrained by the user's declaration and the rules, or it doesn't happen. Short build intake exists for this (7 questions).
6. **The method has explicit non-findings.** Rules state what the skill refuses to grade (opt-in philosophy, subject line length, persona count, testing at small scale). Do not fill those gaps with general marketing opinion.

## Workflow: full audit

### Phase 0: Mode detection
Check available tools for a connected ESP/CRM.
- Connected: LIVE MODE. Tell the user what you can read, confirm read-only scope, get an explicit yes before pulling anything.
- Not connected: PASTE MODE. Read `references/paste-mode.md`. State upfront that findings without evidence will be marked UNVERIFIABLE, not guessed.

Both modes require intake first. Never audit without intake: grading without declared intent produces opinions, and this skill has none.

### Phase 1: Intake
Read `references/intake.md`. Run conversationally, section by section, with the section intros as written. Constrained answer formats are mandatory. One push-back on vague answers, then record as declared. Save the completed intake as a file the user keeps: their system declaration. Re-audits diff against it.

### Phase 2: Evidence
LIVE: inventory flows, campaigns, segments, signup forms, unsubscribe path, and stats per `references/<platform>.md`. If no mapping file exists for the platform, inventory what the tools expose and say the mapping is generic.
PASTE: request the six evidence items from `references/paste-mode.md`; accept partial delivery.

### Phase 3: Grading
Read `references/grading-rules.md`. Apply per step, 1 through 9, in this order within each step: structural checks, then coherence against intake, then fit against context. Skip nothing; a step with no evidence yields UNVERIFIABLE findings, not silence. Then run Section 0 (posture) over the aggregated markers.

### Phase 4: Report
Use `assets/audit-report-template.md`. The user's D4 question answered first. Findings ordered by the D3 trigger, then structural, then severity. Every suggestion states the gap it closes and its tradeoff; options plural where the method allows plural; never "best practice is."

## Quick modes (no full intake)

- **DRAFT REVIEW**: user pastes one email. Ask two questions first: what is this email's one-sentence point, and what does the recipient get from it. Grade against those answers, Step 4 rules only.
- **ACME/EMCA TEST**: marker scan (Section 0) on a pasted email or plan. Output is the markers found, explicitly not a posture verdict; say so.
- **PRE-SEND CHECK**: interactive walk through `references/pre-send-checklist.md`, group by group. Verdict: send / fix first / hold. Hold only for unconfirmed structural items.

## Build modes

Read `references/grading-rules.md`, "Build modes" section. Precondition for all: a system declaration exists (full intake or the short build intake in `references/intake.md`). Ask first, every time, and say why in one line.

- **BUILD: EMAIL**: point stated, five conversion elements answered as a brief before drafting, draft, self-grade on Step 4, landing page continuity requirements, trace block.
- **BUILD: FLOW**: position in declared journey, entry/exit as states, sequence as a belief chain (email count follows from beliefs, no fixed templates), timing as conditions the user chooses, self-grade on Steps 2, 3, 6, trace block.
- **BUILD: SEGMENT**: trace to a declaration first, define as a rule, name for function, state what it gates and excludes, trace block.
- **BUILD: CAMPAIGN**: send rationale and audience checks, then BUILD: EMAIL, then the pre-send checklist automatically.

Refusals inside build modes are marker-based (manufactured urgency, bait subjects, send-because-we-can): one line naming the marker, plus the honest alternative. Not a lecture.

## Boundaries

- Legal questions (GDPR, CASL, CAN-SPAM): flag and classify, tell the user to verify with a lawyer. The skill spots consent-shaped holes; it does not give legal advice.
- Deliverability crises with an active blacklist entry: diagnose the chain, then recommend specialist help and stop. Wrong advice at that stage does damage.
- Model note: audits and builds are reasoning-heavy; the README recommends the most capable model available. The skill compensates partially by forcing structure (finding types, traces, non-findings), which constrains lazy reasoning regardless of model.
- Method reference: 9steps.email/method. Findings for Steps 1-4 link to step articles; Steps 5-9 cite the step by name until published.
