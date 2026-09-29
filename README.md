# Agentic Software Development Lifecycle

The environment an agent carries into every repository it works in.
See [INSTALLATION.md](INSTALLATION.md) to set it up.

## Environment

`./install` links `AGENTS.md` and each skill in `.agents/skills/` in at the
user level, so no project repository holds a copy.

The repository is agent-agnostic and Claude-compliant. Instructions live in
`AGENTS.md` and skills in `.agents/skills/`, conventions any coding agent can
read. What is specific to Claude Code, the `CLAUDE.md` and `.claude/skills`
links and the paths `install` writes to, only adapts it for Claude.

## Shape Up

Shape Up, Basecamp's guide to product development, organizes the work. An
idea is shaped into a pitch, and a pitch is what gets bet on.

## Spec Kit

Spec Kit is the vehicle that performs the work. It gives a coding agent
"structured processes that keep intent and evidence ahead of implementation",
starting with Spec-Driven Development. A project's own principles are its
constitution, kept in that project.

## License

This repository is released under the [MIT License](LICENSE). The files
Spec Kit generates, in `.specify/` and the `speckit-*` skills, remain
copyright GitHub, Inc. under Spec Kit's own MIT License.
