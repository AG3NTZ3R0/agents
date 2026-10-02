# Agentic Software Development Lifecycle

The environment an agent carries into every repository it works in.
See [INSTALLATION.md](INSTALLATION.md) to set it up.

## Environment

`./install` sets up the machine: it links `AGENTS.md` and each skill in
`.agents/skills/` in at the user level, so no project repository holds a copy,
and installs the tools they use. Skills work only in the current session and
project.

The repository is agent-agnostic and Claude-compliant. Instructions live in
`AGENTS.md` and skills in `.agents/skills/`, conventions any coding agent can
read. What is specific to Claude Code, the `CLAUDE.md` and `.claude/skills`
links and the paths `install` writes to, only adapts it for Claude.

## Vim

Code is read locally in Vim, with nothing beyond what Vim and Git ship.
`vim .` opens netrw, Vim's own file browser, and `:Lexplore` keeps it as a
tree in a sidebar. `git difftool HEAD~1` reviews a commit in vimdiff, and
`git difftool main...HEAD` a whole branch, before anything is pushed.

## Shape Up

Shape Up, Basecamp's guide to product development, is how work is defined. An
idea is shaped into a pitch, and a pitch is what gets bet on.

## Spec Kit

Spec Kit is a tool for building defined work. It gives a coding agent
"structured processes that keep intent and evidence ahead of implementation",
starting with Spec-Driven Development. A project's own principles are its
constitution, kept in that project.

`specify/workflows/` holds Spec Kit workflows to install into a project with
`specify workflow add --dev specify/workflows/<id>`. This repository is not a
Spec Kit project itself; see [DEVELOPMENT.md](DEVELOPMENT.md).

## License

This repository is released under the [MIT License](LICENSE).
