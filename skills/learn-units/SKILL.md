---
name: learn-units
description: Expand approved subject nodes into ordered concepts, objectives, dependencies, and source references.
---

Read the `learn-session` skill’s `references/state.md` before reading or changing course records. Resolve that skill by its frontmatter name; installed folder names may differ. Reuse a contract already loaded in this session.

Read the approved main map and learning brief. Process each main node within its agreed scope.

Define concept units with stable IDs, observable objectives, essential prerequisites, helpful links, and exact source locators. Classify each objective by its primary learning demand: `knowledge` (explain, distinguish, predict, or reason about the idea), `skill` (perform or use it independently when the relevant method is apparent), or `transfer` (recognize when and how to use it in a fresh or messy context without being told the target concept). Use `transfer` only where the learning goal genuinely requires it; do not force trivial facts or vocabulary into artificial transfer tasks. Link shared prerequisites across main nodes. Each unit should support a coherent explanation and meaningful practice; split units whose objectives need substantially different lessons.

Write one `concepts/<id>.yaml` record per unit from the shared template, and list its ID under the parent node. Inspect source sections for coverage; label unmapped objectives as source gaps. Sources may be completed just before teaching, but make gaps visible to the critic. Preserve existing learning evidence during revisions.

For teaching preparation, the teacher will derive held-out questions from these objectives before the lesson begins. This stage specifies content and dependencies, not a script for every interaction.

Completion means each main node is covered by scoped objectives and the concept graph resolves without essential cycles. Increment curriculum revision, request `learn-critique`, address its findings, and show the grouped concept map to the learner for approval.
