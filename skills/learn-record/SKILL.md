---
name: learn-record
description: Persist actual learning attempts, concept progress, review material, and precise session resume points.
---

Read the `learn-session` skill’s `references/state.md` before reading or changing course records. Resolve that skill by its frontmatter name; installed folder names may differ. Reuse a contract already loaded in this session.

Read the latest affected records before writing. Persist only observed responses and established decisions; keep inferred gaps tentative when evidence is weak.

Append an event to `sessions.jsonl` with a unique event ID, timestamp, concept/objective/item IDs, question and learner response, help/source access, rubric result, feedback, and next action. Preserve corrections as new events referring to the original. Avoid duplicate events on retries.

Update the concept snapshot using those event IDs: objective evidence, learning state, misconceptions, review history, and next review. Store review questions separately from answer criteria within the record. Reuse the verified source references; prepared questions are not evidence of learning.

Before issuing a question or changing the resume point, append a checkpoint event containing the exact pending prompt, phase, and resume instruction; do not fabricate a response. Update `current-session.yaml` with those same values and the active concept. Check IDs, dates, YAML/JSON parsing, and snapshot/event consistency. If interrupted between writes, reconcile missing snapshot updates from logged events before adding new ones.

Completion means the durable records can resume the interaction without guessing. Persist through the environment’s file workflow; a local scratch write alone is not a completed save. Report a failed save and preserve the unsaved work.
