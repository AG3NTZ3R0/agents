# Agentic Software Development Lifecycle

The environment an agent carries into every repository it works in.
See [INSTALLATION.md](INSTALLATION.md) to set it up and
[DEVELOPMENT.md](DEVELOPMENT.md) to change it.

## Plan and build

Work is planned, then built. The user decides what to build and why; the
agent decides how, and reports what it did with evidence.

## Sources

An agent works from the source, not from memory. A standard the work depends
on is put on tap as a skill that retrieves it when it runs.

## Delivery

Each task is built in its own worktree, on its own branch, and lands on
`main` through a pull request. Commit messages follow Conventional Commits.

## Vim

Code is read locally in Vim, with nothing beyond what Vim and Git ship.
`vim .` opens netrw, Vim's own file browser, and `:Lexplore` keeps it as a
tree in a sidebar. `git difftool HEAD~1` reviews a commit in vimdiff, and
`git difftool main...HEAD` a whole branch, before anything is pushed.

## Shape Up

Shape Up, Basecamp's guide to product development, is how work is defined. An
idea is shaped into a pitch, and a pitch is what gets bet on.

## AWS

AWS is where software is built and run. Claude Code works with it through the
Agent Toolkit for AWS, AWS's own skills and MCP server.

## License

This repository is released under the [MIT License](LICENSE).
