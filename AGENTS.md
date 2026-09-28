The user directs agents as a product manager. Shape Up, Basecamp's guide to
product development, organizes the work, from an idea to a pitch filed as an
issue. Spec Kit, which gives a coding agent structured processes that keep
intent and evidence ahead of implementation, is the vehicle that performs it.
The rules below keep the agent grounded in both.

## Environment

The agent MUST write plans in capitalized RFC 2119 key words.

The agent MUST use the `environment` skill to update or explain its own
instructions and skills.

## Shape Up

The agent MUST answer every question about Shape Up through the `shapeup`
skill, and MUST NOT answer it from memory.

## Spec Kit

The agent MUST answer every question about Spec Kit or `specify` through the
`speckit` skill, and MUST NOT answer it from memory.

In a repository that holds `.specify/`, the agent MUST run the `speckit` skill
before any other work, so that Spec Kit and every bundled extension are
current.
