# AI Learning System

A small set of agent instructions for learning an entire subject, from defining the goal to curriculum design, interactive lessons, and spaced review. Built initially around neuroscience, usable for other subjects.

## Start with Codex or OpenCode

Give your agent this repository's URL and say:

> Clone this repository, read AGENTS.md, and use it to help me learn neuroscience. Start by understanding my goal and background.

Or clone it yourself, open the folder in your agent, and say:

> Read AGENTS.md and start a learning session.

No package install or application server is needed. The agent needs file access and a way to inspect credible source material. These are Markdown workflows; an agent can read them directly even without native skill discovery. Platform-specific agent registration is not included.

## What happens

1. Clarify your purpose, scope, background, and desired ability.
2. Map main subjects and prerequisites; critique the map and get your agreement.
3. Expand subjects into ordered concepts with objectives and sources; critique and agree again.
4. Teach one concept through short explanations, questions, hints, and independent checks.
5. Save actual evidence and review concepts in later sessions.

| Skill | Responsibility |
| --- | --- |
| `learn-session` | Coordinate and resume |
| `learn-goal` | Define the destination |
| `learn-map` | Map subjects and prerequisites |
| `learn-units` | Design concepts and objectives |
| `learn-critique` | Check curriculum quality |
| `learn-teach` | Teach and assess a concept |
| `learn-record` | Persist evidence and checkpoints |
| `learn-review` | Review and repair gaps |

The four role profiles and shared state contract live under `skills/learn-session/references/`. Blank course templates live under `skills/learn-session/assets/course/`.

## Your learning data

Each course normally lives in `courses/<course-id>/`, with its curriculum, sources, per-concept progress, attempt history, and exact resume point. That directory is ignored by Git; keep a personal backup. Say “Resume my neuroscience course” to continue from its files.

Sources are verified before teaching and stored once when permitted. The repo includes no textbooks or learner history. Review dates are checked when you start a session; no background reminders are installed. The initial 1/3/7/14/30-day schedule is a configurable V1 heuristic.

## Design

Small composable skills, concise entry points, and shared rules stored once, informed by [Matt Pocock's writing-for-agents guide](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-for-agents/SKILL.md). See [design basis](skills/learn-session/references/design-basis.md).

V1: iterate from real learning sessions. File structure and instruction flow have been checked; end-to-end behavior depends on the agent and its available tools.
