# Installation

Requires `git` and `curl`.

    git clone https://github.com/AG3NTZ3R0/agents.git
    cd agents
    ./install

`install` symlinks:

- `AGENTS.md` to `~/.claude/CLAUDE.md`
- each skill in `.agents/skills/` to `~/.claude/skills/<name>`
- `vim/vimrc` to `~/.vim/vimrc`, warning if a `~/.vimrc` exists, since Vim
  reads that instead

It adds `git/gitconfig` to `include.path` in `~/.gitconfig`.

After that, ask the agent to update its environment.
