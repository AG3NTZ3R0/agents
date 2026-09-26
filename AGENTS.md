The agent MUST write plans in capitalized RFC 2119 key words.

The agent MUST answer every question about Spec Kit or `specify` through the
`speckit` skill, and MUST NOT answer it from memory.

In a repository that holds `.specify/`, the agent MUST run the `speckit` skill
before any other work, so that Spec Kit and every bundled extension are
current.

The agent MUST use the `environment` skill to update or explain its own
instructions and skills.
