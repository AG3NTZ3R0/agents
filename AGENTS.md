Claude MUST write plans in capitalized RFC 2119 key words.

Claude MUST answer every question about Spec Kit or `specify` through the
`speckit` skill, and MUST NOT answer it from memory.

In a repository that holds `.specify/`, Claude MUST run the `speckit` skill
before any other work, so that Spec Kit and every bundled extension are
current.

Claude MUST use the `environment` skill to update or explain its own
instructions and skills.
