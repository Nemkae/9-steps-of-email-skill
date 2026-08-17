# Intake: the system declaration

Run conversationally, section by section. Read each intro (in prose) before its questions. Constrained answer formats are mandatory: offer the options, accept free text only where marked. Save the completed intake as the user's system declaration file; it is the standard every COHERENCE finding is graded against, and it is printed in the report.

**Push-back protocol:** exactly one push-back on any vague answer, worded as a request for the concrete version, not as criticism. If the second answer is still vague, record it as declared and note it; vagueness at B2, B3, B4 is itself gradeable (rules 1.1, 1.5a, 2.4c).

**Never ask about** send frequency, open rates, budgets, or tech stack. Frequency and metrics are observed in the evidence phase; the stack is detected or revealed by the paste.

---

## Section A: Business frame

**Intro:** "First, the business itself, ignoring email entirely. What you sell and how people get to it sets the frame that email is judged against later. Don't mention email in these answers."

**A1.** What does the business sell, in one sentence?
Free text.
NOTE: baseline for all relevance findings; detect content-sensitive categories for consent implications (2.6).

**A2.** Do your customers already know what they want and shop on price and convenience, or do they need to be led to a solution they don't fully understand yet?
Options: know what they want (commodity) / need to be led (journey) / some products one, some the other.
NOTE: feeds 2.5, 3.2. Mixed answer: ask which product line the audit should focus on, or grade per line if evidence allows.

**A3.** What counts as "it worked," the main conversion event?
Options: purchase / application submitted / call or demo booked / profile or setup completed / subscription started / other (name it).
Then: roughly how long from first contact to that event?
Options: hours / days / weeks / months.
NOTE: defines point Z. Feeds 2.3, 3.2, 4.4, 8.2 (conversion tracing).

**A4.** Ask only if the conversion event involves payment. Say why: "This calibrates which suggestions the audit can responsibly make. Thin margins rule out discount-based tactics and paid protections like email verification services; better to know now than to suggest a 20% off win-back to someone with 8% margins."
Options: thin / moderate / comfortable.
For non-payment conversions: "What does one conversion cost or earn you, roughly? 'Unknown' is a valid answer."
NOTE: feeds 2.3 fit logic and suggester eligibility. "Unknown" narrows suggestions, produces no finding.

## Section B: Email channel intent

**Intro:** "Now email specifically. Your business wants revenue; that's not what this asks. This asks what job email does inside the business. 'We need sales' and 'email nurtures leads until they're ready to talk' are different answers, and the second kind is what belongs here."

**B1.** Rank your goals for email as a channel. Order these, drop what doesn't apply, add what's missing: sales/conversion, retention, nurture/education, engagement/traffic, brand awareness, lead qualification.
Ranked list required. If the user says "all equally": push-back once ("if you could only have one, which").
NOTE: the reference frame for 1.3, 3.5, 6.1, 6.3, 7.2, 8.2. Top two matter most; several rules key on "retention or nurture in top two."

**B2.** Complete from the subscriber's side, one sentence: "I stay on this list because ___."
One sentence. Push-back once if the answer describes what you send rather than what they get ("we send updates" is sender-side; "I get X before anyone else" is subscriber-side).
NOTE: rule 1.1 (structural if unanswerable), 1.2, 3.3, 3.5. The single most load-bearing answer in intake.

**B3.** Who are you talking to? Name one to three subscriber types in plain words. For each: what are they trying to achieve, and what stands in their way?
Constrained: want + obstacle per type. Push-back once on demographic brackets ("women 25-45" is a targeting bracket; what does she want and what blocks her).
NOTE: 1.5, 4.3 relevance, 4.8, 6.1. One good persona beats three brackets; count is never graded.

**B4.** Walk one subscriber type from B3 through your emails as they exist in your head: what's the first email they get, what happens over the following weeks, and what does the last meaningful email before conversion look like? If the honest answer is "they get the same newsletters as everyone," say that.
Free text, anchored to specific emails, not philosophy.
NOTE: 2.4 (all three gap types), 2.5, 3.2, 6.2. The escape hatch is deliberate; the honest lazy answer is gradeable, the dressed-up one isn't. Do not accept a restatement of A2.

**B5.** Are you committed to email as a channel, or testing it? Who works on it, and roughly how much of their time?
Options for commitment: committed / testing / inherited it, deciding. Free text for who and how much.
NOTE: the scaling input for 1.4, 3.4, 5.2, 9.1. Findings calibrate to declared resources; no data model recommendations to a solo operator with two hours a week.

## Section C: Acquisition and consent

**Intro:** "How people get on and off your list. No philosophy questions, just what actually happens at the edges."

**C1.** Where do subscribers come from? List entry points.
Options, multi-select: signup form / checkout / lead magnet / popup / import / offline or events / other.
NOTE: 2.3 inventory; each entry point checked against C3.

**C2.** Where are you legally, and where are your subscribers mostly?
Options: EU/UK/Canada-style consent laws / US-style / mixed / unsure.
NOTE: 2.6. "Unsure" is valid and produces a flag, worded as prerequisite work, not a lecture. Never give legal advice; classify and refer.

**C3.** What stands between a fake or mistyped email address and your list?
Options, multi-select: captcha or bot check / syntax check on the form / verification service / confirmation email (double opt-in) / nothing / don't know.
NOTE: 2.3 fit logic, combined with A3, A4, C2. Never ask "single or double opt-in" as a preference question; grade the protection combination against context.

**C4.** How does someone leave your list? Describe the actual unsubscribe path as far as you know it.
Free text. "As far as you know it" is deliberate.
NOTE: 2.1, 2.2. Not knowing is itself a finding (the owner can't describe the exit). Verified against evidence in Phase 2.

## Section D: Current state and self-diagnosis

**Intro:** "Your own read on the situation. Answer honestly, not strategically. These are hypotheses the audit will test, and a refuted hypothesis is one of the most useful things you can get out of this."

**D1.** What is working, in your view?
**D2.** What is not working, in your view?
Free text, both. Record as discrete hypotheses (split compound answers).
NOTE: each hypothesis gets a row in the report's self-diagnosis table: Confirmed / Refuted / Unverifiable. Feeds 7.2, 8.1, 8.2, 9.2. Watch for the classic misdiagnosis pattern (attributing low results to spam placement when open rates say otherwise); test, don't accept.

**D3.** What triggered this audit?
Options: routine check / specific problem / deliverability scare / new ownership of the channel / preparing to scale / other.
NOTE: report ordering. Deliverability scare puts Step 7 first; new ownership puts the declaration and 9.1 first.

**D4.** If the audit could answer one question, what would it be?
One question, free text.
NOTE: answered first in the report, verbatim, with finding references. If unanswerable from evidence, say what would answer it.

## Section E: System access

**Intro:** "Last thing: what the audit can look at. It reads; it never changes anything in your account."

**E1.** Confirm mode.
LIVE: "I can see [platform] connected. I'll read flows, campaigns, segments, forms, the unsubscribe path, and stats where exposed. Read-only. OK to proceed?"
PASTE: "No account connected. I'll ask for six things; send what you have, and I'll mark anything I can't verify." See `references/paste-mode.md`.
NOTE: explicit consent moment. Do not pull before the yes.

---

## Short build intake

Used by build modes when no full declaration exists. Seven questions, constrained formats, about five minutes:

1. What does the business sell, and what is the conversion event? (A1 + A3 compressed)
2. Email channel goals, ranked. (B1)
3. "Subscribers stay because ___." (B2), one push-back allowed.
4. Who is this element for: one persona, want and obstacle. (B3, single)
5. Where in the subscriber's journey does this element sit: before what, after what? (B4, local)
6. Jurisdiction, one word. (C2)
7. What must this element accomplish, in one sentence without "and"? (element-level point, feeds 4.1)

Saved as a partial declaration; a later full audit expands it. Same push-back protocol.
