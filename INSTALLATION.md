# Installation

Requires `git`, `curl`, and an authenticated `gh`.

    git clone https://github.com/AG3NTZ3R0/agents.git
    cd agents
    ./install

`install` symlinks `AGENTS.md` to `~/.claude/CLAUDE.md` and each skill in
`.agents/skills/` to `~/.claude/skills/<name>`. It is safe to rerun, and it
refuses to replace a file already at either location.

The links point into the clone, so `git pull` updates every session. A skill
added upstream needs `./install` again.

`specify` is not required up front: the `speckit` skill reports when it is
missing and has Spec Kit's installation guide at hand.
