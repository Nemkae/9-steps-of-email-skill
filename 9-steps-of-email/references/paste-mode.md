# Paste mode: evidence request

Used when no ESP/CRM is connected. Request the six items below, in priority order, and accept whatever subset arrives. State upfront which findings will be marked UNVERIFIABLE based on what is missing. Partial pastes produce honest partial audits, never confident guesses.

Opening line to the user, in prose: "No account connected, so I'll work from what you paste. Six things, in order of usefulness; send what you have. Anything I can't verify gets marked as such, not guessed."

## The six items

**1. Flow inventory**
List of active automations/flows and scheduled campaign types, with triggers if known. A screenshot of the automations screen is fine.
Feeds: Steps 2, 3 (2.4, 2.5, 3.2, 3.5), 6.2, 7.2 (weak), 9.2 (if last-edited dates visible).

**2. Three representative emails, full content**
One automated (welcome or onboarding), one typical campaign or newsletter, one the user considers their best performer. Subject lines included. HTML source if available; rendered copy otherwise.
Feeds: Step 1 (1.2, 1.3, 1.5b), Step 4 (all), 5.1 (HTML only), 5.3.

**3. The signup path**
URL of the main signup form or a screenshot, plus the confirmation email if one exists.
Feeds: 2.3, 2.6.

**4. The unsubscribe experience**
What the footer link says and where it leads; screenshot if possible.
Feeds: 2.1, 2.2.

**5. Numbers, if accessible (optional)**
Last 30-90 days: opens, clicks-to-opens, bounces, unsubscribes, spam complaints, list growth. Per flow or per campaign if the platform shows it. Explicitly framed as optional.
Feeds: 2.7, 7.2, 7.4, 8.2 (partial). Absence downgrades these to UNVERIFIABLE, not blocking.

**6. Segment list**
Names and rough definitions of segments actually used for sending.
Feeds: 6.1, 6.2, 6.3, 4.8.

## Also ask during evidence phase (short, conversational)
- Sending domain (for 7.1, checked if tools allow DNS lookup)
- What happens between "email written" and "email sent" (5.2)
- Last test run, what it taught, what changed (8.1)
- Which numbers get checked after a send (8.2)
- Where learnings live (9.1)
- When data last changed a flow, segment, or message (9.2)

## Handling partial delivery
Map missing items to rule IDs and print them in the report's "What the audit did not check" section, grouped by the evidence that would resolve them. This doubles as the upgrade path: a paste-mode user who provides the missing items gets a fuller audit on the next pass.
