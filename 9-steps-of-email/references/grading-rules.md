# Grading rules

## How to read this file

Every rule has: ID (step.number), TYPE, GRADED AGAINST, EVIDENCE, and either a RULE (structural) or LOGIC (coherence/fit). Many rules carry a FINDING TEMPLATE and a NON-FINDING entry. Non-findings are as binding as findings: they state what this skill refuses to grade. Do not fill those gaps with general marketing opinion.

Finding types:
- **STRUCTURAL**: universal method rule. Binary, non-negotiable.
- **COHERENCE**: observed system vs the user's own declaration (intake). The core type.
- **FIT**: a valid choice mismatched to declared context.
- **ADVISORY**: recommended, not required. Not a finding. No severity, no verdict weight. Reported in its own section.
- **UNVERIFIABLE**: rule could not be evaluated for lack of evidence. First-class outcome; state what evidence would resolve it.

Grading order within each step: structural, then coherence, then fit.

Table of contents:
- Section 0: ACME/EMCA assessment
- Steps 1-9
- Section 10: Pre-send check
- Build modes

---

## Section 0: ACME/EMCA assessment

Two archetypes of email sender, from the method's founding distinction. ACME uses email to extract from subscribers. EMCA uses email to deliver value to subscribers. Neither is a moral category; the method's claim is structural: ACME behavior sends a system into the engagement-decline spiral, EMCA behavior keeps it out. The assessment exists to make posture visible, not to shame anyone. Most senders drift ACME under KPI pressure without deciding to.

### 0.1 What is assessed
Observable behaviors only. The assessment never grades what the user says their philosophy is; it grades what the system does. A user who declares EMCA intent in intake and runs an ACME system gets the ACME verdict plus a coherence finding, which is the most valuable output this section can produce.

### 0.2 Marker set
Each marker is detected from evidence already gathered by the step rules; Section 0 aggregates, it does not re-inspect. Cross-references in brackets.

ACME markers:
- A1 Send rationale is "we can," not "they'd want" [3.5]
- A2 Volume to unengaged audiences rising, especially under declining results [7.2]
- A3 Full-list sends despite declared multiple personas [4.8, 6.1]
- A4 Manufactured urgency, fake scarcity, countdowns to nothing [4.6]
- A5 Subject lines that promise what the body doesn't deliver [4.7]
- A6 Unsubscribe made hard, hidden, or multi-step [2.1, 2.2]
- A7 Content mix dominated by promotional sends against a non-promotional value declaration [1.2]
- A8 Metrics watched are opens/clicks/sales only, never placement, complaints, or list health [8.2]
- A9 Affiliate or third-party offers to a list that opted in for something else [1.2, 3.5]
- A10 Frequency escalation as the response to falling numbers (user-reported in D1/D2 or visible in send history) [7.2]

EMCA markers:
- E1 Every observed send traceable to a declared goal and a subscriber-side benefit [3.5]
- E2 Engagement-aware segmentation exists and gates sending [6.3]
- E3 One-click unsubscribe, visible, named [2.1]
- E4 Reply path open and monitored [3.1 advisory; counted here as positive marker when present]
- E5 Content exclusive to or shaped for the channel [3.3]
- E6 Subject lines that identify the email's point honestly [4.7]
- E7 Fewer, better sends chosen over more, when D1/D2 describes a decision to reduce [7.2]
- E8 Placement, complaint rate, or list health among metrics watched [8.2]
- E9 Journey-shaped flows that move subscribers by state, not calendar [6.2]

### 0.3 Verdict logic
No numeric scoring. The verdict is one of three, chosen by pattern:
- **ACME posture**: three or more A markers present with fewer than two E markers, or A2/A10 present at all (the spiral markers dominate).
- **EMCA posture**: three or more E markers present with A2, A6, A10 all absent.
- **Mixed / Drifting**: everything else, which is most real systems. Named "drifting" when A markers concentrate in recent sends vs older flows (the system started EMCA and is sliding), "mixed" otherwise.

The verdict is stated with its markers listed. "ACME posture because: A1, A3, A6, evidence at [rules]" is a finding. "You seem kind of extractive" is not, and the skill never emits that.

### 0.4 What the assessment refuses
- No verdict from a single email in isolation. Quick-mode ACME/EMCA TEST on a pasted email produces a marker scan ("this email shows A4 and A5, no E markers"), explicitly not a posture verdict, and says so.
- No verdict from tone. Enthusiastic promotional copy is not an A marker; a promotional send with no traceable subscriber value is (A1). The difference is evidence.
- No moralizing. The report states the structural consequence the method claims (spiral risk, placement decline, churn cost), never a character judgment.
- No "everybody does it" excuse accepted, no "we're different" claim accepted. Markers or nothing.

### 0.5 Placement in report
Verdict appears after the D4 answer and the self-diagnosis table, before per-step findings, because it frames everything below it. For drifting verdicts, the report names the direction of drift and the earliest marker in the sequence, which is usually where the fix starts.

---

## Step 1: Identify (goals, value proposition, personas, commitment)

### 1.1 Value proposition answerable
TYPE: STRUCTURAL
GRADED AGAINST: method rule
EVIDENCE: B2 answer
RULE: The subscriber-side value proposition must be completable as a concrete sentence. "They get our updates" and "they hear about offers" are sender-side sentences wearing a disguise; they describe what you send, not what the subscriber gets. If B2 could not be answered after one push-back, that is finding #1 of the audit, severity high, because every coherence finding downstream inherits this hole: a system cannot be graded against an intent that was never formed.
FINDING TEMPLATE: "The value proposition of the email channel could not be stated from the subscriber's side. Until it exists, content decisions have no reference point and relevance cannot be graded. This is the first gap to close; most findings below depend on it. [Step 1]"

### 1.2 Value proposition vs observed content
TYPE: COHERENCE
GRADED AGAINST: B2 declaration
EVIDENCE: live: last 10-20 sends across flows and campaigns; paste: item 2 (three representative emails)
LOGIC: Grade the observed content mix against the B2 sentence. The test per email: does this email deliver, advance, or at minimum relate to the declared reason to stay? Tally, don't cherry-pick. A list where the dominant share of observed emails serves something other than the declared value proposition earns the finding regardless of performance metrics, because the declaration, not the open rate, is the standard the user set for themselves.
FINDING TEMPLATE: "You declared: subscribers stay because [B2]. Of [N] observed emails, [X] serve that declaration, [Y] serve something else, mostly [pattern]. Either the declaration or the content is wrong; the audit cannot tell you which, but the system currently pulls in two directions. [Step 1]"

### 1.3 Goal ranking vs observed send mix
TYPE: COHERENCE
GRADED AGAINST: B1 ranking
EVIDENCE: same as 1.2, plus flow inventory
LOGIC: Classify observed sends by which B1 goal each serves. Compare distribution against ranking. The finding triggers on inversion, not imprecision: the bottom-ranked goal consuming the largest share of sends, or the top-ranked goal having no dedicated flow at all. Do not grade proportionality finely; ranked goals are ordinal, and demanding percentage alignment would be inventing a threshold the method does not claim.
NON-FINDING: the goals themselves. The skill never grades whether retention should outrank acquisition. It grades whether the system serves the ranking the user declared.

### 1.4 Commitment vs system weight
TYPE: FIT
GRADED AGAINST: B5 (resources, ownership)
EVIDENCE: B5 answers; observed system complexity (flow count, segment count, platform tier)
LOGIC: Two directions, both gradeable:
a) Declared ambition exceeds declared resources: B1 ranks three or more active goals, B4 describes a multi-stage journey, but B5 says one person, a few hours weekly, testing the channel. The finding is a warning, not a verdict: the method's position is that an under-resourced email program degrades into ACME behavior under KPI pressure, because shortcuts are all that fit in the hours available.
b) System exceeds operator: observed flow and segment complexity that B5's declared ownership cannot plausibly maintain. Orphaned automation is a liability; flows nobody remembers send emails nobody checks.
FINDING TEMPLATE (a): "Your declared goals require [inferred workload class]. Declared resources: [B5]. The method's warning: this gap is where extraction habits start, not because anyone decides to extract, but because it's what fits the hours. Options: narrow B1 to the top goal, or resource the channel to match. [Step 1]"

### 1.5 Personas gradeable
TYPE: COHERENCE
GRADED AGAINST: B3 answers
EVIDENCE: B3; observed content addressing (live/paste as in 1.2)
LOGIC: Two-part check:
a) B3 quality: a persona is gradeable if it names what the person wants to achieve and what blocks them. "Women 25-45" is an ad targeting bracket, not a persona; nothing about content relevance can be graded against it. Recorded as declared, flagged as ungradeable, one push-back allowed during intake.
b) If B3 is gradeable: do observed emails address any declared persona's want or obstacle, or are they persona-blind (product announcements addressed to everyone, which is to say no one)?
NON-FINDING: persona count. One persona well-drawn beats three brackets. The method does not require multiplicity.

STEP 1 UNVERIFIABLE CONDITIONS: 1.2, 1.3, 1.5b require observed content; in paste mode with fewer than three emails provided, mark accordingly and state what evidence would verify.

---

## Step 2: The Flow (opt-in, journeys, opt-out)

### 2.1 One-click unsubscribe
TYPE: STRUCTURAL
GRADED AGAINST: method rule
EVIDENCE: unsubscribe link placement and destination (live: template footers + unsubscribe page; paste: item 4)
RULE: Unsubscribing requires exactly one click after the email. No login, no email re-entry, no multi-step confirmation, no "manage preferences" as the only path. Preference centers may exist alongside, never instead.
FINDING TEMPLATE: "Unsubscribe requires [observed steps]. Method rule: one click. Users who cannot leave easily report spam instead, and Gmail runs no feedback loop, so those reports are invisible to you until placement drops. [Step 2]"

### 2.2 Hidden unsubscribe
TYPE: STRUCTURAL
GRADED AGAINST: method rule
EVIDENCE: footer link visibility (font size, contrast, wording)
RULE: The unsubscribe link is visible and named. Not "update your preferences here" in 8px grey.
FINDING TEMPLATE: as 2.1, evidence-specific.

### 2.3 Entry point protection vs funnel context
TYPE: FIT
GRADED AGAINST: declared context (A3 conversion distance, A4 margin, C2 jurisdiction, C3 protections)
EVIDENCE: C3 answers; live: signup form inspection + presence of confirmation flow; paste: item 3
LOGIC:
- No protections at all (no captcha, no syntax check, no verification, no confirmation email) = finding at any context. Severity scales with list size and send volume.
- Single opt-in + no verification service + thin margin = fit gap: the context cannot absorb hygiene damage and cannot afford the cleanup either. Options: add verification API, or switch to confirmed opt-in. Tradeoffs stated (cost vs conversion friction).
- Double opt-in + long funnel = coherent, no finding.
- Single opt-in + captcha + verification service = coherent regardless of funnel shape.
- EU/Canada jurisdiction (C2) + no consent capture = flag under 2.6, not here.
NON-FINDING: the single-vs-double choice itself. Never graded as philosophy.

### 2.4 Declared journey vs observed flow
TYPE: COHERENCE
GRADED AGAINST: user's B4 walk-through
EVIDENCE: live: actual flow/automation inventory with triggers; paste: items 1-2
LOGIC: Compare the journey the user described in B4 with what flows exist. Grade three gaps separately:
a) Declared but absent: user described a first email / progression / pre-conversion email that does not exist in the system.
b) Present but undeclared: flows running that the user did not mention. Not automatically bad; surfaced as "your system does things you didn't describe; confirm they're intentional."
c) The same-newsletter answer: if B4's honest answer was "everyone gets the same newsletters" AND intake B1 ranks nurture or retention top-two, that combination is the finding. B4's answer alone is not.
FINDING TEMPLATE: "You described [B4 quote]. The system shows [observed]. The gap: [a/b/c specifics]. Graded against your own declaration, not a method ideal. [Step 2]"

### 2.5 Commodity/journey mismatch in flow shape
TYPE: FIT
GRADED AGAINST: A2 declaration
EVIDENCE: flow inventory, sequence lengths, content of first 3 emails
LOGIC:
- A2 = commodity, observed = long belief-building nurture before the conversion event is reachable: fit gap (friction added to buyers who already know what they want).
- A2 = journey, observed = single blast list, no progression: fit gap (nothing builds the beliefs the journey requires).
- Mixed A2: grade per product line if evidence allows, else note scope limit.

### 2.6 Consent capture vs jurisdiction
TYPE: FIT (legal-adjacent, see SKILL.md Boundaries)
GRADED AGAINST: C2
EVIDENCE: signup form fields, checkbox presence/state, confirmation flow
LOGIC: EU/Canada-style + no explicit consent mechanism observed = flag, classified as consent-shaped hole, worded with the lawyer disclaimer. US-only = no finding on consent, note on opt-out compliance only. C2 = "unsure" = the finding is the unsureness itself: resolving jurisdiction is prerequisite work.

### 2.7 Churn visibility
TYPE: COHERENCE
GRADED AGAINST: B1 (if retention/nurture ranked top-two)
EVIDENCE: live: unsubscribe + spam complaint stats per flow, if exposed; paste: item 5, optional
LOGIC: Retention-focused declaration + no visibility into where in the lifecycle people leave = coherence gap: the declared priority cannot be managed with the instrumentation present. UNVERIFIABLE if stats absent in paste mode, stated as such.

---

## Step 3: Sync (email strategy, message types, content)

### 3.1 Reply path open
TYPE: ADVISORY
EVIDENCE: From-address of observed emails; presence of "do not reply" language in body or address
ADVICE: Send from an address that accepts and is monitored for replies. Replies are among the strongest positive signals a mailbox provider can observe, and inviting them is free deliverability that most senders decline. A noreply@ address or "do not reply" copy forgoes that signal and tells subscribers the conversation is one-way. Strongly advised, not mandatory; many senders have no real mailbox behind the address, and the skill does not grade that as a violation. Counted as EMCA marker E4 when present.

### 3.2 Message type coverage vs declared journey
TYPE: COHERENCE
GRADED AGAINST: B4 walk-through, A3 conversion event
EVIDENCE: flow inventory classified by type (transactional, lifecycle/triggered, campaign/broadcast)
LOGIC: The declared journey implies a minimum message-type skeleton: an entry acknowledgment (what happens when they sign up), at least one progression mechanism between entry and the A3 conversion event, and the conversion-adjacent message B4 described. Grade presence, not sophistication. A journey declared in three acts with only broadcasts in the system means the journey exists in the user's head and nowhere else.
FINDING TEMPLATE: "Your declared journey: [B4 compressed]. Message types present: [inventory]. Missing skeleton: [gaps]. The journey you described has no delivery mechanism for acts [N]. [Step 3]"

### 3.3 Channel-exclusive value
TYPE: COHERENCE
GRADED AGAINST: B2 declaration
EVIDENCE: observed email content vs user's other public channels (checked lightly: does the newsletter reproduce the blog/social feed verbatim)
LOGIC: Graded only when B2 claims something exclusive ("first access," "subscriber-only," "insights we don't publish"). If B2 makes the claim and observed emails are cross-posts of public content, the declaration is unserved. If B2 claims no exclusivity, cross-posting produces no finding here; note under 1.1's logic that a value proposition resting entirely on convenience ("same content, your inbox") is thin, stated as observation, not violation.
NON-FINDING: cross-posting as practice. The method's claim is that exclusive email content strengthens the channel; it is not a ban on distribution.

### 3.4 Strategy documented vs oral tradition
TYPE: FIT
GRADED AGAINST: B5 (ownership, resources)
EVIDENCE: intake conversation itself (did answers come readily or get constructed on the spot); existence of any written strategy, process map, or editorial calendar the user can point to
LOGIC: Scaled to B5. A solo operator testing the channel is not graded for lacking a process map; the finding would be noise. The finding triggers when B5 declares committed, multi-person, or agency-managed ownership AND no documented strategy exists: at that scale, undocumented strategy means the strategy is whoever sends next. Severity rises if intake answers visibly contradicted each other (B1 ranking vs B4 journey), which is what oral-tradition strategy looks like from outside.
NON-FINDING: absence of formal documentation at declared-small scale.
ADVISORY attached: the method treats a general content strategy as a prerequisite for the email strategy. Not gradeable without defining one; recommended at report level when 3.4 fires.

### 3.5 Send rationale
TYPE: COHERENCE
GRADED AGAINST: B1 + B2 jointly
EVIDENCE: campaign/broadcast history (live: last 60-90 days of campaigns; paste: item 1 + item 2)
LOGIC: For each observed broadcast, ask: which declared goal does this serve, and what did the subscriber get? Broadcasts answering neither are excuse-to-email sends, the method's marker of extraction posture (A1). The finding names the pattern, not individual emails, unless one example is unusually clean.
FINDING TEMPLATE: "Of [N] recent broadcasts, [X] have no traceable goal from your B1 ranking and no subscriber-side value under your B2 declaration. Pattern: [e.g. sales pushes to full list during gaps in content production]. This is the send-because-we-can pattern; in the method's experience it is the most common precursor to placement decline. [Step 3]"

STEP 3 UNVERIFIABLE CONDITIONS: 3.3 needs at least a glance at one public channel; if none provided or found, mark unverifiable. 3.5 needs send history; three pasted emails support only a weak-evidence version, stated as such.

---

## Step 4: Define (point of each email, design for conversion)

### 4.1 Point of email stateable
TYPE: STRUCTURAL
GRADED AGAINST: method rule
EVIDENCE: the email under review; in full audit, each reviewed email
RULE: Every email has a point describable in one sentence without "and". Two points in one email is zero points. In DRAFT REVIEW mode the user states the point before grading begins and the draft is graded against their statement; in full audit, the point is inferred from the email and the inference is shown ("this email's point appears to be X; if that's wrong, the email failed to state it").
FINDING TEMPLATE: "The point of this email cannot be stated in one sentence without 'and': [the two-plus competing points observed]. Each additional point taxes the first one. Split or cut. [Step 4]"

### 4.2 Point serves declaration
TYPE: COHERENCE
GRADED AGAINST: B1/B2 (full audit) or the user's stated point (draft review)
EVIDENCE: email content vs its stated/inferred point
LOGIC: The email's actual content weight must serve its point. An email whose stated point is "get the reader to book a call" but whose content is 80% company news buries its own point. 4.1 asks whether a single point exists; 4.2 asks whether the email is actually built around it.

### 4.3 Conversion elements evaluation
TYPE: COHERENCE (per element, graded against the email's own point)
GRADED AGAINST: the stated/inferred point from 4.1
EVIDENCE: the email under review
LOGIC: Five questions, each answered with evidence from the email, none scored numerically:
- RELEVANCE: is it clear within the first two seconds of reading who this is for and why now? Graded against B3 personas where available.
- OFFER VALUE: is what the reader gets stated, or does the email assume the reader will infer it?
- INCENTIVE TO ACT: is there a reason to act now rather than never? (Deadline, scarcity, sequence position, consequence of waiting. Manufactured urgency is graded under 4.6, not rewarded here.)
- FRICTION: count the asks. Every additional link target, decision, and form field is friction. The method does not prescribe a number; it requires that friction be spent on the point, not on ornamentation.
- ANXIETY: what could make the reader hesitate at the click (unclear destination, commitment ambiguity, trust gap), and does the email address it or ignore it?
OUTPUT FORMAT: five short verdicts with evidence, not a score. This is a lens, not a leaderboard.

### 4.4 Landing page continuity
TYPE: COHERENCE
GRADED AGAINST: the email's promise
EVIDENCE: the email's primary CTA destination (live or pasted URL; fetched where tools allow, else user describes or screenshots)
LOGIC: The method's claim: the click is the only thing email can win, and the landing page decides whether the win survives. Graded as continuity questions: does the page's first screen repeat or advance the email's motivation, or reset it? Is the promised thing (offer, content, price) present without hunting? Do incentives stated in the email survive to the page? A page that greets a specific email's click with the generic homepage is the archetypal finding.
UNVERIFIABLE when the destination cannot be inspected; state what a screenshot would verify.

### 4.5 Structure proportions
TYPE: COHERENCE
GRADED AGAINST: the email's point (4.1)
EVIDENCE: the email under review
LOGIC: The method's primary/supporting/additional structure is applied as a dominance test, not a percentage audit: the primary message visibly dominates; supporting elements reinforce rather than compete; anything else earns its place or goes. Grade by asking what a reader skimming for three seconds would take away, and whether that matches the point. Exact ratios are not measured and never cited as violations.
NON-FINDING: an email that is 100% primary message. Short is not a gap.

### 4.6 CTA discipline
TYPE: STRUCTURAL (first two) + COHERENCE (rest)
GRADED AGAINST: method rules / the email's point
EVIDENCE: the email under review
RULES (structural):
- The primary CTA works without images rendered (text link or bulletproof button, not image-only).
- The primary CTA is identifiable as the primary: one visually dominant action per email. Secondary links may exist; a reader asked "what does this email want me to do" must have exactly one honest answer, which must match 4.1's point.
COHERENCE checks:
- CTA copy states the action and the outcome, not "click here".
- Urgency, if present, is real (a date that exists, a limit that is true). Manufactured countdowns and fake scarcity are graded as an anxiety generator and as ACME marker A4.
- Tap-target size and placement work on mobile (advisory-level when unverifiable from paste).

### 4.7 Subject line serves the open, honestly
TYPE: COHERENCE
GRADED AGAINST: the email's content
EVIDENCE: subject line + body of the email under review
LOGIC: The method's claim: subject lines don't sell, they earn the open. Two checks:
- The subject makes a promise the body keeps. Bait-and-switch subjects (question the body never answers, claim the body never supports) are graded as a trust withdrawal that pays for one open with future ignores, and as ACME marker A5.
- The subject would identify this email among twenty others from competitors: does it carry the point, or is it a generic wrapper ("March Newsletter") that outsources the open decision to sender-name loyalty alone? The second is an observation-level note, not a violation; generic-but-honest beats clever-but-false.
NON-FINDING: subject line length, emoji use, personalization tokens, capitalization style. The method has no rules there, and pretending otherwise would be inventing tactics.

### 4.8 One email, one audience
TYPE: COHERENCE
GRADED AGAINST: B3 personas (full audit)
EVIDENCE: the email under review; recipient segment if known
LOGIC: An email addressed to everyone on the list must survive the question: is there a declared persona for whom this email's point is irrelevant or wrong? If yes, and the send was full-list, the finding is a segmentation gap surfaced at the email level (cross-ref Step 6). Not graded when B3 declared a single persona or the segment is known to match.

STEP 4 UNVERIFIABLE CONDITIONS: 4.4 without destination access; 4.6 mobile checks from paste; 4.8 without segment information.
ADVISORIES ATTACHED TO STEP 4: mobile rendering advice when unverifiable; plain-text alternative advice (advised, not mandatory).

---

## Step 5: Code and Test (rendering, QA)

### 5.1 Renders without images
TYPE: STRUCTURAL
GRADED AGAINST: method rule
EVIDENCE: email HTML (live: template source; paste: item 2 if HTML provided, else UNVERIFIABLE)
RULE: The email communicates its point and its primary CTA with images blocked. Alt text on meaningful images, text-based or bulletproof primary CTA (cross-ref 4.6), no image-only emails. Image blocking is a default state in enough clients that an image-dependent email is a coin-flip email.

### 5.2 QA process exists
TYPE: FIT
GRADED AGAINST: B5 (resources)
EVIDENCE: user asked directly during evidence phase: what happens between "email written" and "email sent"?
LOGIC: Scaled like 3.4. Solo operator: the finding triggers only if the answer is "nothing, I hit send" AND observed emails show rendering or link defects, in which case the defect is the evidence. Committed/team ownership: absence of any defined check (test send, link click-through, rendering check on at least one mobile client) is the finding regardless of visible defects, because at that scale defects are a when, not an if.
NON-FINDING: absence of paid testing tools. The method requires a process, not a subscription.

### 5.3 Broken mechanics
TYPE: STRUCTURAL
GRADED AGAINST: method rule (an email's links must work)
EVIDENCE: observed emails; links spot-checked where fetchable
LOGIC: Dead links, placeholder text ({first_name} unrendered, "INSERT SUBJECT"), broken personalization fallbacks. Binary, evidence-based, no judgment involved. Highest-confidence finding type in the audit when found; also the most embarrassing, so the report words it factually and moves on.

---

## Step 6: Dynamic Automated User Segments

### 6.1 Segments exist beyond "everyone"
TYPE: COHERENCE
GRADED AGAINST: B1 + B3 declarations
EVIDENCE: live: segment/list inventory with definitions; paste: item 6
LOGIC: Graded against declarations, not against a segmentation ideal. A single-persona (B3), single-goal (B1) sender with one list is coherent; no finding. The finding triggers when declared personas or ranked goals imply differentiated messaging AND the system shows one audience receiving everything. Cross-ref 4.8, which surfaces the same gap at the email level; here it is graded at the system level.

### 6.2 Static lists doing dynamic work
TYPE: COHERENCE
GRADED AGAINST: B4 journey declaration
EVIDENCE: segment definitions: rule-based (auto-updating on behavior/attributes) or manually maintained lists?
LOGIC: A declared journey implies movement: subscribers change state (new, engaged, converted, dormant). Manually maintained lists cannot track movement; they fossilize the day they were made. The finding names specific declared transitions (from B4) that no dynamic rule currently detects.
UNVERIFIABLE in paste mode if item 6 lists names without definitions; the names alone often tell the story ("Newsletter Final List 2 REAL") but are graded only as advisory-level observation.

### 6.3 Engagement data feeds segmentation
TYPE: COHERENCE
GRADED AGAINST: B1 (when retention/nurture ranked top-two)
EVIDENCE: segment definitions: does any segment key on engagement recency or behavior (email or site), or are all segments attribute-based (signup source, geography, purchase category)?
LOGIC: Retention-ranked declarations require the system to know who is drifting before they're gone. All-attribute segmentation means the system cannot distinguish an engaged subscriber from a ghost. Finding severity rises when combined with observed full-list sending (cross-ref 7.2).
NON-FINDING: the absence of a formal engagement data model. The method's Step 6 ideal (mirrored DB, unified metrics) is report-level advice at most scales; the gradeable minimum is "at least one engagement-aware segment exists and is used."

---

## Step 7: Send and Deliver

### 7.1 Authentication baseline
TYPE: STRUCTURAL
GRADED AGAINST: method rule, citing the current industry-mandatory state (SPF, DKIM, DMARC at minimum policy)
EVIDENCE: live: sending domain DNS lookup where tools allow; paste: user asked for sending domain, checked if fetchable, else UNVERIFIABLE
RULE: Mandatory since the 2024 Gmail/Yahoo bulk sender requirements. This is the one place the method cites an external mandate rather than its own rule, because the mailbox providers made it non-optional. Missing DMARC or unaligned SPF/DKIM is a finding at any scale.
MAINTENANCE NOTE: cites external requirements that change. Last verified: 2026-08-17. Revisit on each major sender-requirement update.

### 7.2 Send volume concentration
TYPE: COHERENCE
GRADED AGAINST: B1 + declared list composition
EVIDENCE: live: send logs per segment, 60-90 days; paste: item 5 plus item 1
LOGIC: The method's spiral warning made checkable without inventing a frequency threshold: what share of total volume goes to segments with no engagement filter? Rising volume to unfiltered audiences is the observable signature of the KPI-pressure spiral from the method's core narrative. The finding cites the trajectory, not a number: "volume to unengaged is growing while engagement declines" is gradeable from the user's own data at any threshold.
NON-FINDING: any specific send frequency. Frequency is observed, never prescribed.

### 7.3 Transactional/marketing separation
TYPE: FIT
GRADED AGAINST: system scale (observed volume, list size)
EVIDENCE: live: sending infrastructure inventory (domains, subdomains, IPs where exposed); paste: user asked
LOGIC: At meaningful scale, transactional and marketing sends share a reputation if they share infrastructure, and a marketing misstep then takes password resets down with it. Graded as FIT because at small scale on a shared-pool ESP, separation is neither possible nor necessary. The finding triggers at dedicated-infrastructure scale without separation, or when observed marketing troubles are already bleeding into transactional placement (user-reported in D2).

### 7.4 Bounce and complaint hygiene
TYPE: STRUCTURAL
GRADED AGAINST: method rule (bounces and complaints must be processed, not accumulated)
EVIDENCE: live: suppression list existence, bounce handling settings; paste: item 5, else UNVERIFIABLE
RULE: Hard bounces suppressed after first occurrence, complaint feedback loops honored where the ESP exposes them, no re-sending to suppressed addresses. Most ESPs automate this; the finding usually appears only on self-hosted or hybrid infrastructure, where it is severe.

---

## Step 8: Analyze and Learn

### 8.1 Testing tests something
TYPE: COHERENCE
GRADED AGAINST: user's D1/D2 self-diagnosis and stated practices
EVIDENCE: user asked: what was your last test, what did it teach you, what changed because of it?
LOGIC: The method's claim: test for knowledge, not results. The gradeable version: a test that produced no decision is decoration. The finding triggers when the user reports testing activity (subject line A/Bs are the usual answer) but cannot name one thing the last three tests changed. No finding for not testing at all at small scale; a solo sender's resources may be better spent elsewhere, and pretending otherwise would be tactics theater.
NON-FINDING: absence of a formal testing program. Graded on declared activity vs its yield, not on presence.

### 8.2 Metrics watched match goals declared
TYPE: COHERENCE
GRADED AGAINST: B1 ranking
EVIDENCE: D1/D2 language + user asked: which numbers do you check after a send?
LOGIC: The vanity-metric check, graded against their own goals. Retention ranked first but only open rates watched: the declared goal has no instrument. Conversion ranked first but click-through never traced to the A3 conversion event: same gap. The finding names the unmeasured declaration, not the metric choice itself.
NON-FINDING: any particular metric being good or bad. Open rates post-Apple-MPP get a reliability note when the user leans on them, worded as measurement caveat, not violation.

---

## Step 9: Iterate and Improve

### 9.1 Learnings have a home
TYPE: FIT
GRADED AGAINST: B5 (scaled like 3.4, 5.2)
EVIDENCE: user asked: where does what you learned live? Would a new owner of this channel inherit it or start from zero?
LOGIC: At committed/team scale, learnings that live in one person's head are a liability the method treats as unfinished Step 9. At solo scale, advisory at most.

### 9.2 The loop actually loops
TYPE: COHERENCE
GRADED AGAINST: D1/D2 + observed system age markers
EVIDENCE: live: flow last-edited dates where exposed; user asked: when did a finding from your data last change a flow, a segment, or a message?
LOGIC: The method's Step 9 is a return arrow to Step 4, and the gradeable question is whether the arrow has ever been traversed. Flows untouched for years while D2 reports declining results is the finding: the system emits data no one feeds back. Severity scales with the gap between declared analysis activity (8.1) and observed system stasis.
NON-FINDING: stability itself. An untouched flow that works is not a gap; untouched AND underperforming AND unexamined is.

STEPS 5-9 ROADMAP NOTE: rules above are v1 depth, drawn from the method's outline; they expand alongside the step-by-step articles as published. Structural rules here are complete; coherence rules gain platform-specific evidence paths (`references/<platform>.md`) in v1.x.

---

## Section 10: Pre-send check

Interactive mode. Read `references/pre-send-checklist.md` and walk the user through it group by group, user confirms each item. Items carry rule IDs; an item the user cannot confirm becomes a pointer to the relevant rule's evidence requirement, not a lecture. Output: the checklist with each item marked confirmed / not confirmed / not applicable, plus a one-line verdict: send, fix first, or hold. "Hold" only for structural items (marked *) unconfirmed. Everything else is the user's call, stated as their call.

---

## Build modes

Preconditions for all build modes:
- A system declaration exists (full intake, or the short build intake in `references/intake.md`). No declaration, no build. Ask the questions first, every time; state why in one line: the method builds from intent, and there is no intent on file.
- Read-only remains absolute. Build modes output drafts, specs, and definitions as text or files. Nothing is written into a connected ESP. State this once at the start of any build.
- Every built element carries its trace block. A trace block is not decoration; it is the self-grade, produced before the user sees the draft. Element without a trace is not finished.

### BUILD: EMAIL
Input: the element-level point (short intake Q7 or user-stated), persona, journey position. Optionally the user's rough notes or an existing draft to rebuild.
Process:
1. Restate the point back. If it fails 4.1 (two points), split before writing: "that's two emails; which goes first?"
2. Answer the five conversion elements as requirements before drafting (4.3 inverted): who it's for and why now; what they get, stated; why act now, real reason only; the one ask; what will make them hesitate and how the copy addresses it. Show these to the user as the brief. Get a nod.
3. Draft. Structure by dominance (4.5): primary message visibly dominant, supporting elements only if they reinforce. One primary CTA, action-plus-outcome wording, text-based (4.6). Subject line carries the point and promises only what the body delivers (4.7). Voice from the user's samples if provided; otherwise plain and direct, and say so.
4. Self-grade: run Step 4 rules on the draft as if reviewing. Fix what fails before presenting. If something can't be fixed without the user (missing landing page, unknown offer detail), mark it.
5. Landing page requirements (4.4): state what the destination must show in its first screen for the click to survive. The skill doesn't build the page; it specifies continuity.
Output: subject line, preheader, body, CTA, plus TRACE BLOCK: point · persona · journey stage · B1 goal served · B2 value delivered · conversion elements (five one-liners) · rules self-graded [4.1-4.8] · landing page requirements · open items.
Refusals inside build: manufactured urgency, fake scarcity, bait subjects, "click here." Each refusal names the marker (A4, A5) and offers the honest alternative. One line and the alternative, not a lecture.

### BUILD: FLOW
Input: flow purpose (welcome, onboarding, nurture, win-back, post-conversion, abandoned action, other) plus declaration.
Process:
1. Position the flow in the declared journey (B4): what state enters it, what state should exit it, what B1 goal it serves. If B4 has no such stage, the finding comes first: "your declared journey has no place for this flow; either the journey or the flow needs revising."
2. Define entry and exit as states, not calendar (6.2 inverted): trigger condition, exit condition (goal reached, opt-out, engagement threshold the user names, or handoff to another flow), and the segment logic gating each send (6.3).
3. Sequence: for each email in the flow, one line: point (4.1), what the subscriber must believe or agree to at this step to move forward (Step 2's belief-building logic), and what advances them to the next. The belief chain is the spine; email count follows from it, not the other way. No fixed "5-email welcome series" defaults; the number of emails is however many beliefs need building, stated honestly.
4. Timing: expressed as conditions and ranges the user chooses, never prescribed intervals. "After confirmation; then after first login or 3 days, whichever first" is a spec; "day 1, day 3, day 7" is a template someone else wrote.
5. Self-grade against Steps 2, 3, 6: journey coherence, message type skeleton (3.2), state-based movement (6.2), engagement gating (6.3), unsubscribe present in every send (2.1).
6. Optionally proceed to BUILD: EMAIL per sequence item.
Output: flow spec as a table or list: entry, exit, per-email point and belief, gating, timing conditions, plus TRACE BLOCK: journey stage · goal served · states in/out · rules self-graded [2.x, 3.x, 6.x] · what the user must decide (thresholds, timing ranges) · ESP-agnostic notes on where this maps (platform file cross-ref if one exists).

### BUILD: SEGMENT
Input: what the user wants to distinguish and why (which declaration it serves).
Process:
1. Trace to a declaration first: which B1 goal or B3 persona makes this segment necessary. A segment with no declared purpose is a list, not a segment; say so and stop.
2. Define as a rule, not a membership: attribute conditions plus engagement conditions where the goal is retention or nurture (6.3). Prefer dynamic definitions; if the user's ESP can't do dynamic, state that as a limitation of the tool, not a change to the definition.
3. Name it for what it does, not when it was made ("engaged non-buyers, 90d" not "list 2 final"). One line on why naming matters: the segment name is the only documentation most systems will ever have (9.1).
4. State what sends this segment gates and what it excludes: a segment used only to add volume, never to withhold, is A2 in disguise.
Output: segment definition, name, purpose trace, gating use, plus TRACE BLOCK: declaration served · dynamic/static · rules [6.1-6.3] · platform mapping note.

### BUILD: CAMPAIGN (single broadcast)
Thin wrapper on BUILD: EMAIL with two additions before drafting:
- Send rationale (3.5): which B1 goal, what the subscriber gets. If neither can be stated, the campaign fails before the first word: "this is a send-because-we-can; what would make it worth a subscriber's attention?" One push-back, then build if the user insists, with the A1 marker noted in the trace.
- Audience (4.8, 6.1): who receives it and why not everyone. Full-list default triggers the question, not a refusal.
Then BUILD: EMAIL, then the pre-send checklist (Section 10) as the closing step, automatically.
