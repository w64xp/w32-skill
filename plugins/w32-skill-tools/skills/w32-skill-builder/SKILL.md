---
name: w32-skill-builder
description: Guides the user step by step through creating a new skill. Use when the user says "create a skill", "make a new skill", "help me design a skill", "สร้างสกิล", "ทำสกิลใหม่", or describes a repeated task they want automated.
---

# W32 Skill Builder

Guide the user from a free-form idea to a finished, concise skill pack (.skill), one confirmed step at a time.

## Inputs
- Required: the user's description of what the skill should do
Ask for anything missing. Never guess.

## Workflow
1. Describe: let the user explain freely; analyze nothing until they say they are done. Then summarize in 2-3 sentences ("This skill is for X, to get Y, taking Z") and confirm.
2. Triggers and inputs: propose 3-5 trigger phrases and the inputs the skill needs; user adjusts and confirms.
3. Output: propose format, structure, tone, output language, and one short sample; user confirms. If the output has a required format (exact structure, code block, field order, etc.), mark it as fixed; the description rule in step 7 then applies.
4. Workflow: show 3-7 one-line steps; user adds, removes, or reorders until satisfied.
5. Restrictions: ask what the skill must not do; if none, propose 2-3 sensible ones and confirm.
6. Test and audit: simulate one sample input. Before showing it, check for duplicates, invented facts, scope creep, and rule violations. Show the result with a short audit, propose fixes for any problem, and apply them once the user agrees.
7. Name and create: ask for a name (if none, propose 3 lowercase-hyphenated English names and recommend one). Trim to fit the limits in Restrictions, then write SKILL.md in a folder named after the skill, package it into a .skill pack (zip of that folder; use the skill-creator package script if available), present the file, and summarize: name / what it does / how to invoke. When writing the description field: if the skill has a required output format, the description must say that format is defined in this file and must be read first, not give a generic summary (e.g. prefer "the exact format specified in this file" over "a clean numbered list"), since a generic description lets an AI assume it knows the format and skip it.

## Output
- Format: a downloadable .skill pack containing SKILL.md (show the SKILL.md text in a code block only if asked)
- Language: chat in the user's language
- Tone: friendly, plain, no jargon

## Restrictions
- Ask one question at a time and wait for confirmation; allow going back to any step, or skipping ahead for experienced users.
- If an answer is vague, ask one follow-up instead of guessing.
- Write the skill file entirely in English, even if the user speaks another language; set the skill's reply language in a "Language:" line.
- Keep the generated skill under 60 lines: description under 60 words, workflow 3-7 lines, restrictions 3-5 lines, at most one short example. Cut filler and keep only rules that change behavior.
- Generated skill sections, in order: Purpose (1-2 sentences), Inputs, Workflow, Output (Format, Language, Tone), Restrictions, optional Example.
