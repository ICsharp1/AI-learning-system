---
name: learn-session
description: Start or resume a persistent learning project; coordinate planning, concept teaching, and review.
---

Read [state.md](references/state.md) to locate the course and its current records. For a new course, create missing records from `assets/course/` through the environment’s persistent-file workflow. Preserve existing files. Ask which course only if the choice is ambiguous.

Route the next action:
- Unclear goal: `learn-goal`.
- Confirmed brief, no main map: `learn-map`.
- Draft main map: `learn-critique`, then have the planner address findings and show a compact node diagram for the learner’s feedback.
- Approved main map: `learn-units`, then `learn-critique`; show concepts grouped under their main nodes and resolve learner feedback before teaching.
- Approved curriculum: follow the learner’s requested activity; otherwise resume an unfinished lesson, offer a bounded batch of due reviews, then select a new concept with ready prerequisites. Repair a blocking prerequisite first.

When several new concepts have ready essential prerequisites, choose within that ready set using the learner’s zone of proximal development. Prefer a concept that materially advances the confirmed target abilities and is just beyond demonstrated independent performance: neither already effectively mastered nor dependent on unsupported knowledge that makes the jump unreasonable. Use objective evidence, diagnostics, prerequisite performance, and concept scope; do not invent a numeric ability score. Treat `suggested_concept_order` as a coherent default and tie-breaker, not a fixed sequence. If evidence is too weak to distinguish candidates, use the suggested order or a brief diagnostic rather than guessing.

Read only the relevant role: [planner](references/planner.md), [critic](references/critic.md), [teacher](references/teacher.md), or [reviewer](references/reviewer.md). Invoke the role’s matching skill; keep one learner-facing conversation. These are role instructions, not native agent registrations. Use a fresh critic context when delegation is available; otherwise conduct a separate critic pass and describe it accurately. Only one role writes course records at a time.

Show a brief session agenda and proceed; the learner may change or skip it. Use the course’s review budget (default 10 minutes) and timezone. Review dates are checked when a session runs; they do not create background reminders.

At a pause or transition, use `learn-record` to preserve evidence and the exact resume point. Finish by stating the next useful action, without advancing past an unanswered learner question.

When revising these skills, read [design-basis.md](references/design-basis.md) for the authoring rationale.
