# Agentic Software Development Lifecycle

The environment an agent carries into every repository it works in.
See [INSTALLATION.md](INSTALLATION.md) to set it up and
[DEVELOPMENT.md](DEVELOPMENT.md) to change it.

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

`specify/workflows/` holds Spec Kit workflows, which the `speckit` skill adds
to a project.

`handoff "<feature>"` starts a headless `guarded-sdd` run in a new git
worktree beside the project, so several features build at once. `handoff
--task "<task>"` runs `task` instead: one agent session that builds the task
and commits it on a `task/` branch. A project without Spec Kit always runs
`task`, from this clone, so it needs no `specify init` and commits nothing of
Spec Kit's. `inbox` lists the runs that need you across every worktree and
opens Claude in the one you pick.

## License

This repository is released under the [MIT License](LICENSE).
