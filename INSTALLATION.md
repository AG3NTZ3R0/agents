# Installation

Requires `git`, `curl`, `jq`, and `uv`.

    git clone https://github.com/AG3NTZ3R0/agents.git
    cd agents
    ./install

`install` symlinks:

- `AGENTS.md` to `~/.claude/CLAUDE.md`
- each skill in `.agents/skills/` to `~/.claude/skills/<name>`
- `vim/vimrc` to `~/.vim/vimrc`, warning if a `~/.vimrc` exists, since Vim
  reads that instead

It adds `git/gitconfig` to `include.path` in `~/.gitconfig`.

It installs Claude Code's `aws-core` plugin, and merges `claude/settings.json`
into `~/.claude/settings.json`, keeping any value already set.

After that, ask the agent to update its environment.
