# Development

This repository takes the form of the RFCs that govern it: terminology is
defined before requirements are stated.

What `install` links is present in every session, so it MUST hold in every
repository an agent works in. A statement true in one repository alone is
false in the rest; it MUST NOT be added here, and belongs in that repository's
constitution.

`README.md` MUST define and MUST NOT instruct. It states what this repository
and the agentic software development lifecycle are, and it references each
authority beneath a heading carrying its name as published, or for an RFC its
number and full title as published.

`AGENTS.md` MUST instruct and MUST NOT define. It states what Claude does, in
the vocabulary `README.md` establishes, and it MUST reference `README.md`.

A statement that says what something is belongs in `README.md`. A statement
that says what Claude does belongs in `AGENTS.md`. A statement that does both
MUST be split into one of each.

An RFC under `rfc/` is an authority rather than a copy of one. It MUST be
stored as published, and MUST NOT be edited, reflowed, or summarized. A living
authority MUST NOT be stored here in any form; its skill retrieves it.

A skill lives in `.agents/skills/<name>/` and MUST name its files relative to
its own directory. A skill that maintains this repository is linked into
`.claude/skills/` here and is not installed; `install` links every other skill
into every session.
