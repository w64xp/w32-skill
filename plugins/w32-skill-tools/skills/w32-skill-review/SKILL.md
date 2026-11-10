---
name: "w32-skill-review"
description: Rewrites another skill in tighter wording with identical behavior, lists every change by location, and suggests cuts or adjustments. Use when the user says "review this skill", "make this skill's wording tighter", "รีวิวสกิลนี้", "ปรับคำในสกิลนี้ให้สื่อความหมายกว่าเดิม". The exact 5-part output format is defined in this file; read it before answering.
---

# W32 Skill Review

Keep the skill's behavior; change only wording, replacing long or vague phrases with fewer, precise ones. Report every change and suggest further cuts or adjustments.

## Inputs
- Required: the skill to review (pasted SKILL.md text, an uploaded .skill / .md file, or the name of an installed skill; read its SKILL.md)
- Optional: wording that must not be touched
Ask for anything missing. Never guess.

## Workflow
1. Read the whole skill and note what it does, rule by rule.
2. Find wording that costs more words than it earns: filler, hedging, restated rules, a phrase where one precise word would do.
3. Mark what must stay verbatim: fixed output formats, exact trigger phrases, anything the user said not to touch.
4. Rewrite each flagged spot in the fewest words that keep the exact meaning, preferring concrete words.
5. Compare old and new; log each change with its location (section and line), confirming every rule remains with the same meaning.
6. Note parts worth cutting or adjusting (too long, redundant, vague, explaining what an AI already knows).
7. When the user has no more changes (suggestions applied or declined), ask whether to package the skill now.

## Output
- Format: chat reply with these 5 parts, in order:
  1. Summary: one line on how much was tightened, with word or line counts before and after
  2. Changes: every edit as location: before -> after, plus a few words on why
  3. New version: the full reworded SKILL.md in a code block
  4. Behavior check: one line confirming behavior is unchanged, or naming what really changed
  5. Suggestions: lettered parts (a, b, c, ...) worth cutting or adjusting, each with location, fix, reason, expected result; not applied in the new version. End by asking which letters to apply
- Language: reply in the user's language; the reworded skill stays in its original language
- Tone: direct, friendly, plain, no jargon

## Restrictions
- Never drop a rule or step; reword it instead. Remove only exact duplicates.
- Never change the meaning, scope, or fixed output format of the reviewed skill.
- Never add rules or content the original did not have.
- Apply a suggestion only after the user agrees.
- If a new wording could shift meaning, keep the original and ask the user.

## Example (abridged)
Summary: wording tightened, 120 -> 85 words, same rules.
Changes: Workflow step 2: "Make sure that you always check whether the file exists before reading it" -> "Check the file exists before reading" (same rule, 9 fewer words).
New version: the full reworded SKILL.md in a code block (omitted here).
Behavior check: behavior unchanged.
Suggestions: "Background" section (8 lines): explains what an AI already knows; consider cutting.
