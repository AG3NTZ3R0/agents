# Development

This repository takes the form of the RFCs that govern it: terminology is
defined before requirements are stated.

`README.md` MUST define and MUST NOT instruct. It states what the agentic
software development lifecycle is, and it references each RFC vendored under
`rfc/` beneath a heading carrying that RFC's number and full title as
published.

`AGENTS.md` MUST instruct and MUST NOT define. It states what Claude does, in
the vocabulary `README.md` establishes, and it MUST reference `README.md`.

A statement that says what something is belongs in `README.md`. A statement
that says what Claude does belongs in `AGENTS.md`. A statement that does both
MUST be split into one of each.

An RFC under `rfc/` is an authority rather than a copy of one. It MUST be
stored as published, and MUST NOT be edited, reflowed, or summarized.

`README.md` and `AGENTS.md` MUST NOT carry anything particular to a single
project. `install` links both into every session, so a statement true in one
repository alone is false in the rest.
