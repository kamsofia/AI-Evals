# First LLM-as-a-Judge Eval, Module 1

## Version A, Concise, system prompt used

You are an executive briefing assistant.
Summarize in exactly 3 bullet points under 60 words. No preamble, no extra text.

## Version B, Narrative, system prompt used

You are a PR communications assistant.
Write a 100-word narrative summary highlighting wins first, then risks and next steps. Keep a positive tone. No bullets.

## Eval setup, dataset name + judge model/family

dataset Module1Output + Conciseness LLM-as-a-Judge claude-sonnet-5

## Cold-start, the prompt you used to seed a starter dataset

Generate 20 example rows for evaluating email-summary quality.
Each row: an input email + a candidate summary + a first-pass label ("good" or "bad") + a one-line reason.
Make roughly half concise/faithful ("good") and half verbose or inaccurate ("bad").
Return it as a markdown table.

## Your definition of good vs bad (golden-set criteria) — the graded part, write your own

Good summary:
- Keeps every fact that could change what I do — dates, numbers, deadlines. Drop one and I'm acting on stale or wrong info.
- Leads with the action or outcome. I skim. Anything buried past the first line might as well not be there.
- Represents the actual ask correctly, not a plausible-sounding rewording of it. Get this wrong and I respond to the wrong thing entirely.
- Is exactly as long as it needs to be and no longer. Every extra word is attention I'm not spending on the parts that matter.
- Uses a format I can scan in one pass — bullets for multiple distinct facts, one line if there's really only one thing to say. If I have to reread it to find the deadline, the format failed even if the words are right.

Bad summary:
- Turns a concrete fact vague — "some changes" instead of "12% price increase." I underreact to something that needed urgency.
- Softens bad news — a lost account, an outage — into something neutral-sounding. I don't treat it with the urgency it deserves.
- Adds hedging or speculation that wasn't in the original. I either second-guess something that was actually settled, or chase a problem that isn't real.
- Invents a next step the email never asked for. I think a decision got made when it didn't.
- Is accurate but padded, or wrapped in preamble/narrative framing I have to wade through. Reading it takes as long as reading the email would have — the whole point was to save me that time, and it didn't.
- Mismatches its format to the content — a single simple ask stretched into three bullets, or five distinct facts crammed into one dense sentence. Either way I have to do the reorganizing myself, which defeats the summary.

## Screenshots, links or repo paths (optional if you followed the demo)

_…_

