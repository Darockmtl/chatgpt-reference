---
created: 2026-03-12
updated: 2026-03-12
tags:
  - note/reference
  - status/locked
  - topic/marketing
  - topic/publicspeaking
  - topic/business
---

# English to French Rebuilder Pipeline

Two-prompt system for rebuilding English text into natural, formal, professional Québec French.

**How to use:**
At the start of a translation session, tell Claude: "load the French rebuild pipeline." Claude reads this file and runs both prompts internally. You paste one section at a time and say "go." Claude returns the tagged analysis and the French version in one response. You never interact with the prompts manually.

**Scope:** English to French only. Works on any text type — MC scripts, course content, marketing copy, positioning documents, workshop materials.

**Section size:** Copy-paste by section, not full documents. Let the natural breaks in your document guide the sections — by topic, by speaker, by moment.

---

## PROMPT 1 — Content Context Tagger

Purpose: Identify what a text section is doing and flag translation risks before reconstruction begins.

```
You are analyzing a section of English text that will be rebuilt into Québec French.

Do not rewrite the text.

Your job is to identify what the section is doing and flag everything that creates risk in French reconstruction.

The input may not be explicitly labeled. Analyze the section by what it is doing, not by its label.

Analyze the section and return the following:

1. Section Function
Choose the closest match:
opening
context-setting
core argument
supporting detail
transition
call to action
closing
other

2. Tonal Register
Choose the tone this section must carry into French:
high energy
warm and inviting
grounded and authoritative
tight and practical
ceremonial or formal
informational
other

3. Meaning Certainty
Choose one:
fully clear
mostly clear
partially unclear

4. Non-Negotiables
List what must remain untouched in reconstruction:
names
titles
facts
dates and timing references
instructions
callbacks to other sections
structural logic
special wording that must stay verbatim

5. Translation Risk
Flag expressions, idioms, or sentence structures that are known to produce translation smell or fail in French:
- English idioms with no direct French equivalent
- Phrasal verbs that flatten when translated literally
- English sentence logic that runs long and needs to be broken for French rhythm
- Motivational or marketing phrasing that sounds borrowed in French
- Any expression where a word-for-word version would sound wrong out loud

For each flag, note what the risk is — not what the solution is. The rebuilder handles solutions.

Rules:
Do not rewrite.
Do not improve.
Do not summarize the whole section.
Do not invent missing context.
If something is unclear, say so.

Section to analyze:
[PASTE SECTION]
```

---

## PROMPT 2 — Québec French Rebuilder

Purpose: Rebuild a section into formal, professional, accessible Québec French using the tagger output as its instructions.

```
You are rebuilding a section of English text into Québec French.

The source may contain idioms, English sentence logic, or phrasing that does not survive reconstruction into French. The tagger has already identified the risks.

This is not a translation task.
This is not a proofreading task.
This is a reconstruction task.

Priority order:
1. Preserve factual meaning
2. Preserve the section's function within the larger piece
3. Preserve the tonal register
4. Neutralize every flagged translation risk
5. Make it sound like it was written in French from the start

Target style:
formal and professional but accessible Québec French
clear structure
precise without being cold
confident without being stiff
fluid enough to read naturally — not dense, not bureaucratic

Preserve:
names
facts
dates and timing references
core logic and transitions between ideas
metaphors or expressions that still work in French

Avoid:
English sentence structure hidden in French words
France-French business or media register
overly casual or familiar register (tu form unless the source clearly uses it)
overwriting
generic motivational phrasing
written-page rhythm when the section needs to flow naturally

Use these inputs from the tagger:

Section Function:
[PASTE]

Tonal Register:
[PASTE]

Non-Negotiables:
[PASTE]

Translation Risks:
[PASTE]

Now produce:

1. Reconstructed Québec French version

2. Change Notes
For each flagged translation risk — explain what you did and why.
Only note changes that required a real reconstruction decision.
Skip mechanical substitutions.

3. Uncertainty Flag
Flag any line whose meaning was unclear in the source.
If a flagged risk had no clean solution, say so here.

Source section:
[PASTE SECTION]
```
