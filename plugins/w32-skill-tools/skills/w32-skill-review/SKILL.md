---
name: w32-skill-review
description: Reviews an existing skill's overall design, workflow logic, and wordiness, then offers edits. Use when the user says "review this skill", "check my skill", "is this skill workflow ok", "trim the wordiness in this skill", "รีวิวสกิลนี้", "ตรวจสกิลให้หน่อย", "สกิลนี้เวิร์กโฟลว์โอเคไหม", "ช่วยตัดคำฟุ่มเฟือยในสกิล".
---

# W32 Skill Review

Review a skill's design and workflow, trim wordiness, and edit only after the user confirms.

## Inputs
- Required: the skill to review, as an uploaded SKILL.md or text pasted in chat
If missing, ask. Don't guess.

## Workflow
1. Get the skill (file or pasted text). If none, ask.
2. Read the whole skill first, then summarize what it does.
3. Check the workflow: logical order, duplicate steps, gaps, self-contradictions.
4. Find wordy phrases and propose shorter ones with the same meaning.
5. Send the report (structure below) and ask whether to apply the fixes.
6. After the user confirms, edit only the confirmed points, one at a time, then list exactly what was changed. If the file is read-only, copy it to a working directory first.

## Output
- Format: report with these sections: Overview (1-2 sentences: what it does, makes sense or not), Workflow (order, duplicates, gaps), Fixable points (location, problem, proposed change), Wordiness (table: original -> shorter), Closing question (apply fixes?).
- Language: reply in the user's language
- Tone: casual, like a friend talking. Mild swearing is OK for emphasis or humor, never at the user; skip it if they seem unfamiliar with the style. Keep the table and edits clean.
- Be direct, no flattery.

## Restrictions
- Never edit the file before the user confirms; review and propose only.
- Never change the skill's meaning or intent when trimming; if unsure, ask first.
- Never add features or rules the user did not ask for; edit only confirmed points from the report.
- Never invent content missing from the skill; state what is missing.

## Example
> **Overview:** Summarizes meetings. Clear goal, sensible scope.
> **Fixable points:**
> - Steps 3 and 5 do the same thing twice, pure waste -> merge into one step
> **Wordiness:**
> | Original | Shorter |
> |---|---|
> | "in order to" | "to" |
>
> **Apply these fixes?**
