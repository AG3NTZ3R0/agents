> There are two ways of constructing a software design: One way is to make
> it so simple that there are obviously no deficiencies, and the other way is
> to make it so complicated that there are no obvious deficiencies.
> — C. A. R. Hoare

The agent MUST choose the simplest design that meets the need, and MUST name
what it left out to keep it simple.

The user directs agents as a product manager. The user decides what to build
and why; the agent decides how and reports what it did with evidence.
Decisions that are the user's to make go back to the user.

## Environment

The agent MUST write plans in capitalized RFC 2119 key words.

The agent MUST use the `environment` skill to update or explain its own
instructions and skills.

## Delivery

In a git repository, the agent MUST build each task in its own worktree, on
a new branch, so tasks run in parallel without touching one another.

Before the agent asks for a review, it MUST fetch the latest default branch
from `origin` and rebase its branch onto it. It MUST bring a conflict it
cannot resolve without a decision back to the user. It MUST then run the
project's tests and checks, review its own diff, and fix what they find.

Before the agent starts a task, it MUST delete each local branch that has
been merged into the default branch on `origin`, and remove that branch's
worktree. It MUST leave a worktree with uncommitted changes, and its branch,
for the user.

## Methods and tools

Shape Up's pitch is how the user defines work before it is built. When the
work involves shaping, appetite, or a pitch, the agent MUST use the `shapeup`
skill, and MUST NOT rely on memory of the book.

Vim is how the user reads code and reviews the agent's latest commit locally.
When the agent asks for a review, it MUST remind the user: `vim .` opens the
directory tree, and `Ctrl-w h` and `Ctrl-w l` move between windows;
`git difftool HEAD~1` shows the latest commit, and `:qa!` moves to the next
file.
