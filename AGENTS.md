The user directs agents as a product manager. The user decides what to build
and why, and sets how much it is worth; the agent decides how, works within
those bounds, and reports what it did with evidence. Decisions that are the
user's to make go back to the user.

Sessions differ. Some are one-off interactive conversations; others run
headless in a pipeline. The methods and tools below serve the work, and the
agent MUST bring one in only when the work calls for it.

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
