# Agentic Software Development Lifecycle

The environment an agent carries into every repository it works in.
`./install` links `AGENTS.md` and each skill in `.agents/skills/` in at the
user level, so no project repository holds a copy.

The repository is agent-agnostic and Claude-compliant. Instructions live in
`AGENTS.md` and skills in `.agents/skills/`, conventions any coding agent can
read. What is specific to Claude Code, the `CLAUDE.md` and `.claude/skills`
links and the paths `install` writes to, only adapts it for Claude.

The lifecycle is Spec-Driven Development as Spec Kit defines it. A project's
own principles are its constitution, kept in that project.
