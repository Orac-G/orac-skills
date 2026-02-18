---
name: clear
description: Compacts the current conversation by summarizing what matters and preserving critical context in SESSION.md. Use when the user says "/clear", "clear context", "compact the conversation", or the conversation is getting very long. Reduces token load while preserving continuity.
---

# Clear

Compacts the conversation context to reduce token load while preserving everything important.

## Instructions

### Step 1: Summarize the current conversation
Identify and extract:
- *Decisions made* — anything agreed upon, approved, or confirmed
- *Work completed* — files created/modified, tasks finished, bugs fixed
- *Active threads* — topics or tasks still in progress
- *Key facts learned* — new information relevant to future sessions
- *Open questions* — things pending an answer or action

Discard: exploratory tangents, superseded ideas, verbose back-and-forth that led nowhere.

### Step 2: Update SESSION.md
Write the summary to `/workspace/group/SESSION.md` under a `## Session Compaction` section. Preserve all existing `## Active Instructions` content — only update the `## Current State`, `## In Progress`, and `## Blockers` sections based on what was learned in this session.

Format:
```
## Compacted: [date/time]

### Decisions
- [bullet list]

### Work Completed
- [bullet list]

### Active Threads
- [bullet list]

### Open Questions
- [bullet list]
```

### Step 3: Update memory files if needed
If the session surfaced anything worth preserving long-term:
- New facts about John → `john.md`
- New capabilities or gaps → `capabilities.md`
- Significant work → `ACHIEVEMENTS.md`
- Infrastructure changes → `HEARTBEAT.md`

### Step 4: Confirm
Tell the user:
- What was preserved
- What was discarded
- Current SESSION.md word count (aim for under 400 words)

## Notes
- The goal is continuity, not completeness — capture what the next session needs, not everything that happened
- Active Instructions in SESSION.md are sacrosanct — never modify them
- If unsure whether something matters, keep it — err on the side of preservation
- After compaction, the conversation context resets but SESSION.md carries forward
