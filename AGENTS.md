# Agent entry point

For a learning request, start with [learn-session](skills/learn-session/SKILL.md) and its [state contract](skills/learn-session/references/state.md). Follow the coordinator and read other skills only when needed. If asked to edit this project, do that instead of starting a lesson.

## Running from this clone

- Resolve `learn-*` skill names to `skills/<name>/SKILL.md`. Read and follow the file directly if your tool cannot invoke repository skills. No global installation is required.
- Resolve paths mentioned inside a skill relative to that skill folder. The course templates are in `skills/learn-session/assets/course/`.
- Use `courses/<course-id>/` for learner records by default in this clone. Copy only missing templates, never overwrite existing progress. Ask for a short course name only when it is unclear. Keep records outside the skill folders.
- Before the first session, obtain the learner's timezone and goal, reusing information already provided. Save timezone in `current-session.yaml`.
- Resume from the selected course's `current-session.yaml`; ask if several courses match. Treat empty template values as unknown.
- Source access requires browsing/document tools or learner-provided material. If unavailable, say what source is needed; do not invent references or claim to have read a document.
- The planner, critic, teacher, and reviewer profiles live in `skills/learn-session/references/`. They are portable roles, not native subagent registrations. Use a separate critic context when supported and permitted; otherwise make a distinct critic pass without claiming independence.
- Keep one writer per course. Save assessed responses and the exact pending question before waiting. Never generate learner answers.
- Learning records and source copies are ignored by Git. Do not publish them or override the ignore rules unless the learner explicitly requests it. Local files survive sessions on persistent disks; ephemeral environments need a durable user-approved storage location.

Begin by briefly explaining the next step and asking the first necessary goal question. Do not dump the full curriculum or all skill instructions into the conversation.
