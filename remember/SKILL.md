---
name: remember
description: Saves information to persistent memory. Use when the user says "remember", "make a note", "don't forget", "save this", "keep this in mind", or asks you to record something for future reference. Writes to the appropriate CLAUDE.md or memory file so the information persists across conversations.
---

# Remember

Saves information to persistent memory so it's available in future conversations.

## Instructions

### Step 1: Determine what to remember
Extract the core fact, preference, or context the user wants saved. Strip filler — save the substance.

### Step 2: Determine where to save it

This skill assumes a memory directory at `{MEMORY_DIR}` — set this to your agent's persistent memory path at install time.

- *Personal facts about the user* (preferences, habits, context) → `{MEMORY_DIR}/user.md`
- *Agent's own identity/behavior* → `{MEMORY_DIR}/MEMORY.md` or a relevant topic file
- *Topic-specific knowledge* → create or update the relevant topic file in `{MEMORY_DIR}/` and index it in `MEMORY.md`
- *Operational/system facts* → project `CLAUDE.md` under a relevant section

### Step 3: Write it
- Add concisely to the appropriate file
- Don't duplicate if it's already there
- If creating a new topic file, add it to the index in `MEMORY.md`

### Step 4: Confirm
Tell the user exactly what was saved and where.

## Examples

**User:** "Remember that I prefer responses under 3 sentences when I'm asking quick questions."
→ Add to `user.md` under Communication Preferences.

**User:** "Remember that Bitcoin's halving happens every 210,000 blocks."
→ Add to `crypto.md` under Bitcoin Key Concepts.

**User:** "Remember that my sister's name is Claire."
→ Add to `user.md` under a Personal section.

## Notes
- Be precise — save what was said, not an interpretation of it
- If the fact contradicts something already in memory, update rather than duplicate
- Always confirm what was saved
- Customize `{MEMORY_DIR}` to match your agent's actual memory directory path
