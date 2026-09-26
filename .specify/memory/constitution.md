# Agents Constitution

## Core Principles

### I. Every Repository

`install` links `AGENTS.md` and every skill into every session, so each instruction and
skill MUST hold in every repository the agent works in. An instruction MUST NOT assume a
project's language, layout, or tooling unless it first checks for them, as the `speckit`
instruction checks for `.specify/`. A project's own principles MUST stay in that project's
constitution, not here.

### II. Agent-Agnostic

Instructions MUST live in `AGENTS.md` and skills in `.agents/skills/`, conventions any
coding agent can read. They MUST NOT depend on a feature only one coding agent has. What an
agent requires beyond `AGENTS.md` and `.agents/skills/`, such as `CLAUDE.md`,
`.claude/skills`, and the paths `install` writes to, MUST stay in links and `install`.

### III. Retrieve Upstream, Never Copy

Documentation that changes upstream MUST NOT be copied into this repository; a skill MUST
retrieve it at the current release when it runs. An answer about an upstream tool MUST come
from what the skill retrieved in that session, not from what the agent remembers.

Rationale: copied documentation goes stale without warning, and the agent's memory of
fast-moving tools is already out of date.

### IV. Self-Contained Skills

A skill MUST name its files relative to its own directory, so it works wherever `install`
links it. A skill's executable steps MUST sit beside its `SKILL.md` and MUST be runnable
with no arguments where the skill's purpose allows.

### V. Safe Installation

`install` and every skill that changes the machine MUST be safe to rerun. `install` MUST
repair links left by a moved clone, MUST remove links to deleted skills, and MUST refuse to
replace anything it did not link. A skill that updates the environment MUST refuse to act
on a clone that is off `main` or has uncommitted changes.

Rationale: the environment is loaded into every session, so a destructive or partial run
breaks every repository at once.

## Writing Conventions

Instructions, skills, plans, and this constitution MUST state requirements with
capitalized RFC 2119 key words. Each requirement MUST be one testable statement. Prose
SHOULD stay short: a line that no agent would act on SHOULD be removed.

Customizations to Spec Kit's behavior MUST go in a preset, never in the files Spec Kit
manages. Spec Kit's managed files MAY be overwritten by an upgrade without review.

## Development Workflow

Work MUST follow Spec-Driven Development as Spec Kit defines it: specify, plan, tasks,
implement, converge. Each change MUST land on a feature branch through a pull request to
`main`; `main` MUST NOT receive direct commits. Commit messages MUST follow Conventional
Commits.

Before merging, the reviewer MUST confirm that the change complies with every principle
above and that `install` still runs cleanly on an existing installation.

## Governance

This constitution supersedes every other practice in this repository. `DEVELOPMENT.md`
MUST point to it and MUST NOT restate its rules.

An amendment MUST be made through `/speckit-constitution`, MUST land by pull request, and
MUST state its version bump:

- MAJOR: a principle or rule is removed or redefined incompatibly.
- MINOR: a principle or section is added or materially expanded.
- PATCH: wording, clarification, or typo fixes that change no requirement.

Every plan MUST check itself against this constitution, and any violation MUST be
justified in the plan's complexity tracking or removed.

**Version**: 1.0.0 | **Ratified**: 2026-09-25 | **Last Amended**: 2026-09-25
