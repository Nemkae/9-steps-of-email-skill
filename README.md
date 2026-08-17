# 9 Steps of Email: a Claude Skill

The 9 Steps of Email method, applied by an AI. It audits your email marketing system against your own declared intent, and it builds new emails, flows, and segments from that same declaration.

It does not know your ideal email system. It checks whether yours is the system you think it is.

## Why this exists

Everyone is connecting Claude to their ESP or CRM. Nobody is telling it what good looks like. A connector gives the model hands; without a method, the judgment it applies is whatever marketing content dominated its training data, which is mostly vendor blogs. That produces inconsistent audits biased toward volume and extraction.

This skill fixes the rubric. The 9 Steps of Email is a tool-agnostic framework from 2013 that has survived every platform shift since. It grades structure, not tactics: it never claims to know how often you should send or what your open rate should be. It checks whether your system serves the goals you say it has, and it flags the small set of things the method treats as non-negotiable.

Method: https://9steps.email/method

## What it does

**Full audit.** Intake (your system declaration), evidence (from a connected ESP or from what you paste), grading against the 9 steps, report. Findings come in three types: STRUCTURAL (a universal method rule broken), COHERENCE (your system contradicts your own declaration), FIT (a valid choice mismatched to your context). Every finding traces to a step, a standard, and evidence. Nothing is graded against industry averages.

**ACME/EMCA posture.** The method's core distinction between senders who extract from a list and senders who deliver value to it, assessed from observable behaviors, never from tone.

**Quick modes.** Draft review of one email. ACME/EMCA marker scan. Interactive pre-send checklist.

**Build modes.** Email, flow, segment, campaign, built from your declaration with the rules as constraints, each output carrying a trace block that shows which goal, persona, journey stage, and rules it satisfies. The skill won't write blind: no declaration, no build. Short intake takes about five minutes.

**Always read-only.** With a connected ESP the skill reads flows, campaigns, segments, forms, and stats. It never modifies anything. Build outputs are drafts and specs you apply yourself.

## Install

**Claude.ai / Claude Desktop:** download `9-steps-of-email.zip` (or the identical `.skill` file) from [Releases](https://github.com/Nemkae/9-steps-of-email-skill/releases). In Claude, enable code execution once under Settings > Capabilities ("Code execution and file creation"; on Team and Enterprise an owner enables it in organization settings). Then go to Customize > Skills, click +, choose Create skill, then Upload a skill, and select the downloaded file. Available on Free, Pro, Max, Team, and Enterprise plans.

**Claude Code:** copy the `9-steps-of-email` folder into `~/.claude/skills/` (personal, available in all your projects) or into a project's `.claude/skills/` (that project only), so that `SKILL.md` sits at `~/.claude/skills/9-steps-of-email/SKILL.md`. The skill loads when relevant, or invoke it directly with `/9-steps-of-email`.

Read the method without installing anything: https://9steps.email

## Model recommendation

Audits and builds involve multi-step reasoning across your answers and your account data. Use the most capable model available to you for those. Lighter models are fine for the pre-send checklist.

## Connected platforms

The skill is connector-agnostic. It adapts to whatever ESP/CRM tools are present in the session and falls back to paste mode when none are. Platform mapping files (where each step's evidence lives inside a given platform's data model) ship progressively: Klaviyo in v1.0; Mailchimp, HubSpot, ActiveCampaign, and others planned. Without a mapping file the skill still runs a generic inventory.

## Roadmap and honesty about depth

Grading rules for Steps 1-4 are drawn from the published step articles and are complete. Rules for Steps 5-9 are drawn from the method's outline and are v1 depth; they expand as each step's article is published at 9steps.email. This is marked in the rules file itself.

Planned: additional platform mappings; expanded Steps 5-9 rules; a sample audit report on a fictional account.

## What it refuses to do

Benchmark against industry averages. Prescribe send frequency. Score emails out of ten. Write emails without a declaration. Modify anything in your account. Give legal advice on consent (it flags consent-shaped holes and tells you to verify with a lawyer). Diagnose past an active blacklist entry (it recommends specialist help and stops).

## Credits

Method and rules: Nem Puhalo, 9 Steps of Email, since 2013. Elenion Digital.
The conversion elements evaluation is informed by heuristics popularized by MECLABS Institute; no proprietary notation is reproduced here.

## License

[Owner TODO: choose. Recommendation: CC BY 4.0 for the method text and rules, MIT for any scripts. This is a citable-standard play, so a permissive license with attribution is consistent with the positioning.]

## Contributing

Issues and PRs welcome for: rule wording clarity, evidence paths for additional platforms, false-positive reports with the finding ID and why. Not accepted: added thresholds, benchmarks, generation templates, or platform-specific "best practices" that contradict the method's non-findings.
