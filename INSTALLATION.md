# Installation

Requires `git`, `curl`, `jq`, `uv`, and an authenticated `gh`.

    git clone https://github.com/AG3NTZ3R0/agents.git
    cd agents
    ./install

`install` is the only thing that changes the machine. It symlinks:

- `AGENTS.md` to `~/.claude/CLAUDE.md`
- each skill in `.agents/skills/` to `~/.claude/skills/<name>`
- each script in `bin/`, such as `inbox`, to `~/.local/bin/<name>`, which
  must be on your `PATH`
- `vim/vimrc` to `~/.vim/vimrc`, warning if a `~/.vimrc` exists, since Vim
  reads that instead
- `specify/workflows/` to `~/.local/share/agents/workflows`, where the
  `speckit` skill adds them to a project from

It adds `git/gitconfig` to `include.path` in `~/.gitconfig`.

It installs the `specify` CLI at the latest Spec Kit release with `uv`, or
upgrades it with `specify self upgrade` when it trails, and prints the release
notes it moved past.

It sets `permissions.defaultMode` to `auto` in `~/.claude/settings.json`,
since workflows in `specify/workflows/`, such as `guarded-sdd`, run Claude
Code headless, where no one is present to approve a tool call. It leaves every
other setting alone, and only warns when you chose another mode.

It is safe to rerun, repairs links left by a moved clone, removes links to
deleted skills and scripts, and refuses to replace anything else.

After that, the `environment` skill keeps it current: ask the agent to update
its environment, and it pulls `main` and reruns `install`.
