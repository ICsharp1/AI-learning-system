**Course records**

Resolve the active course from the user or current course reference. In ChatGPT Work, use the Library skill to find/read existing course files and persist edits with their identities and versions. In an explicit repository/local workspace, use that workspace. Keep course data outside installed skill directories; never overwrite populated records with templates. Ask only when multiple courses match or no durable destination is available.

Load only the records needed for the current action. `assets/course/` contains initial templates. Copy `concept.template.yaml` to `concepts/<stable-id>.yaml` when defining a concept, and use the event template as a schema example, not as a logged attempt. File paths below are relative to the course root. Empty fields in templates are intentional unknowns.

| Record | Contents / ownership |
| --- | --- |
| `learning-brief.md` | Goal and learner agreement; planner writes. |
| `curriculum.yaml` | Main-node definitions, concept membership, dependencies, revisions and approvals; planner writes. |
| `curriculum-review.md` | Findings on a named revision/stage; critic writes. |
| `sources.yaml`, `sources/` | Shared source metadata and available originals; planner/teacher maintain. |
| `concepts/<id>.yaml` | Objectives, dependencies, sources, assessment, evidence and reviews; planner owns definitions, teacher/reviewer own progress. |
| `sessions.jsonl` | Append-only assessment/decision events; teacher/reviewer write. |
| `current-session.yaml` | Course settings, active activity and resume point; coordinator writes, teacher/reviewer checkpoint. |

**Identity and evidence**

Use stable lowercase IDs for nodes, concepts, objectives, questions, sources, and events. Essential prerequisite edges mean “requires”; helpful links do not block study. Main-node dependencies guide ordering; concept prerequisites determine readiness for a particular lesson. Validate cross-node concept dependencies explicitly. Never recycle IDs for changed meanings.

Each objective has a `kind`: `knowledge`, `skill`, or `transfer`, describing what successful performance requires; this does not create a separate progress scale. Concept `status`: `not_started`, `learning`, `demonstrated`, `retained`, or `needs_review`. Objective `evidence`: `unassessed`, `assisted`, `independent`, `delayed_independent`, or `needs_review`.

`demonstrated` requires independent evidence meeting the prepared criteria for every objective; cover explanation and novel application where the objective permits. Correctness after a hint/worked answer is assisted until a fresh unaided task succeeds. `retained` requires delayed independent evidence for every objective. A failed review changes affected objectives to `needs_review`; earlier evidence remains in history. A diagnostic can supply readiness evidence, with its origin recorded. Self-report alone cannot silently waive a prerequisite; a learner may explicitly choose to proceed despite a gap.

Curriculum revision is an integer. Record learner approvals separately for `main_map` and `concept_map`, with revision/date. A content change invalidates affected approvals and critic readiness, not unrelated progress. If an objective’s meaning changes, preserve history and flag its old evidence for reassessment. An approval remains valid across unrelated edits; retain its original revision/date and record why its stage is unaffected. The review report must identify the revision it actually checked.

**Source rules**

Choose a small set of suitable textbooks/university materials as the foundation. Browse for missing coverage or newer evidence. Inspect the actual relevant passage/figure before teaching or validating an answer. Record author, title, edition/date, URL or stored document, locator, inspected date, and covered objective IDs. Mark access as `candidate`, `inspected`, or `unavailable`.

Store accessible originals once, where permitted, retaining figures and page/section locations; mark extracted text and AI summaries as derivatives linked to the original. Cite the material actually read. An inaccessible title, search snippet, or model memory is not a verified source. Verify outside-source elaborations before grading them. Recheck disputed claims or changing topics; disclose unresolved conflicts and omit unsupported items from grading. Shared source IDs in concept records prevent duplicated documents. Source access helps verification but is no accuracy guarantee.

**Review schedule**

Default gaps are 1, 3, 7, 14, then 30 days after each successful assessment, measured from the actual assessment date in the course timezone. This is a configurable V1 heuristic. After first independent completion, set `step=0` and due date +1 day. A successful delayed, unaided review covering the concept’s objectives advances one step; cap at the final interval. An assisted/failed review resets step=0 and sets due +1 day. For a partial failed/assisted review, use the earlier of the existing due date and +1 day so untested objectives are not postponed. A successful partial review updates objective evidence but keeps the existing step and due date. Missing assessments never advance scheduling. Repair success during the same session does not count as delayed success. A partly learned concept stays available for resumption and may receive review questions for taught objectives.

**Writes and handoffs**

One active writer per course. Reread affected versions; preserve unrelated fields and changes. Append events first, then update snapshots with their IDs, then the resume pointer. Reconcile an interrupted save before retrying; never invent missing learner responses. Save after meaningful assessed responses and before waiting with a new pending question. Before issuing a new question, log a checkpoint event with its exact pending prompt, phase, and resume instruction, then save the pointer; this makes interrupted writes recoverable without revealing answers. Keep answers/rubrics out of learner-facing questions; file separation is a teaching convention, not access control.

On handoff pass course location, role, relevant concept IDs, action, and unresolved issues. Keep answers and source material out of the handoff unless required by that role. A fresh critic is preferred where available; role switching is a fallback, not independent review. Source gaps block affected teaching only. Do not create scheduled automations merely because a review date exists.
