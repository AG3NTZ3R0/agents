# Installation

Requires `git`, `curl`, `jq`, and an authenticated `gh`.

    git clone https://github.com/AG3NTZ3R0/agents.git
    cd agents
    ./install

`install` symlinks `AGENTS.md` to `~/.claude/CLAUDE.md`, each skill in
`.agents/skills/` to `~/.claude/skills/<name>`, and each script in `bin/`,
such as `inbox`, to `~/.local/bin/<name>`, which must be on your `PATH`. It is
safe to rerun, repairs links left by a moved clone, removes links to deleted
skills and scripts, and refuses to replace anything else.

After that, the `environment` skill keeps it current: ask the agent to update
its environment.

`specify` is not required up front: the `speckit` skill reports when it is
missing and has Spec Kit's installation guide at hand.
