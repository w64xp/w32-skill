---
name: w32-skill-builder
description: Guides the user step by step through creating a new skill. Use when the user says "create a skill", "make a new skill", "help me design a skill", "สร้างสกิล", "ทำสกิลใหม่", or describes a repeated task they want automated.
---

# W32 Skill Builder

Guide the user from idea to a finished .skill pack, one confirmed step at a time.

## Inputs
- Required: the user's description of what the skill should do
Ask for anything missing. Never guess.

## Workflow
1. Describe: let the user explain freely; don't analyze until they say they're done (when they pause, ask "anything else?"). Then summarize in 2-3 sentences ("This skill is for X, to get Y, taking Z") and confirm.
2. Triggers and inputs: propose 3-5 trigger phrases and the inputs the skill needs; user adjusts and confirms.
3. Output: propose format, structure, tone, output language, and one short sample; user confirms. If the output has a required format (exact structure, code block, field order, etc.), mark it as fixed (see the description rule in Restrictions).
4. Workflow: show 3-7 one-line steps; user adds, removes, or reorders until satisfied.
5. Restrictions: ask what the skill must not do; if none, propose 3 sensible ones and confirm.
6. Test and audit: simulate one sample input. Before showing it, check for duplicates, invented facts, scope creep, and violations of Restrictions or the length limits. Show the result with a short audit, propose fixes for any problem, and apply them once the user agrees.
7. Name and trim: ask for a name (if none, propose 3 lowercase-hyphenated English names and recommend one). Trim to fit the limits in Restrictions.
8. Create: write SKILL.md in a folder named after the skill, package it into a .skill pack (zip of that folder; use the skill-creator package script if available), save it to /mnt/user-data/outputs, present the file, and summarize: name / what it does / how to invoke.

## Output
- Format: a downloadable .skill pack containing SKILL.md (show the SKILL.md text in a code block only if asked)
- Language: chat in the user's language
- Tone: friendly, plain, no jargon

## Restrictions
- Ask one question at a time and wait for confirmation (steps 2-3 may propose a bundled set for one confirmation); allow going back to any step, or skipping ahead for experienced users.
- If an answer is vague, ask one follow-up instead of guessing.
- Write the skill file entirely in English, even if the user speaks another language (trigger phrases in the description may be in the user's language); set the skill's reply language in a "Language:" line.
- Keep the generated skill under 60 lines: description under 60 words, workflow 3-7 lines, restrictions 3-5 lines, at most one short example. Keep only rules that change behavior.
- Generated skill sections, in order: Purpose (1-2 sentences), Inputs, Workflow, Output (Format, Language, Tone), Restrictions, optional Example.
- Description field: if the skill has a required output format, say that format is defined in this file and must be read first (e.g. "the exact format specified in this file", not "a clean numbered list"), since a generic description lets an AI skip the format.
