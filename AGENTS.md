> There are two ways of constructing a software design: One way is to make
> it so simple that there are obviously no deficiencies, and the other way is
> to make it so complicated that there are no obvious deficiencies.
> — C. A. R. Hoare

The user directs agents as a product manager. The user decides what to build
and why; the agent decides how and reports what it did with evidence.
Decisions that are the user's to make go back to the user.

## Environment

The agent MUST write plans in capitalized RFC 2119 key words.

The agent MUST use the `environment` skill to update or explain its own
instructions and skills.

## Methods and tools

Shape Up's pitch is how the user defines work before it is built. When the
work involves shaping, appetite, or a pitch, the agent MUST use the `shapeup`
skill, and MUST NOT rely on memory of the book.

Spec Kit is a tool the agent uses to build defined work. When the work
involves Spec Kit or `specify`, the agent MUST use the `speckit` skill, which
brings Spec Kit current first, and MUST NOT rely on memory of it.

Handoff is how the user gives defined work to headless agents, and the user
runs it from the terminal to build the habit. In a project that holds
`.specify/`, when a feature is ready to build, the agent MUST remind the user:
`handoff "<feature>"` starts a `guarded-sdd` run in its own worktree and
returns at once; `inbox` lists the runs that need the user and opens a session
in the one picked.

Vim is how the user reads code and reviews the agent's latest commit locally.
When the agent asks for a review, it MUST remind the user: `vim .` opens the
directory tree, and `Ctrl-w h` and `Ctrl-w l` move between windows;
`git difftool HEAD~1` shows the latest commit, and `:qa!` moves to the next
file.
