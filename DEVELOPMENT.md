# Development

Terminology is defined before requirements are stated, and requirements use
the key words of RFC 2119.

What `install` links is present in every session, so it MUST hold in every
repository an agent works in. A statement true in one repository alone is
false in the rest; it MUST NOT be added here, and belongs in that repository's
constitution.

`README.md` MUST define and MUST NOT instruct. It states what this repository
and the agentic software development lifecycle are, and names each authority
and convention they rest on.

`AGENTS.md` MUST instruct and MUST NOT define. It states what Claude does, in
the vocabulary `README.md` establishes, and it MUST reference `README.md`.

A statement that says what something is belongs in `README.md`. A statement
that says what Claude does belongs in `AGENTS.md`. A statement that does both
MUST be split into one of each.

An authority MUST NOT be stored here in any form; its skill retrieves it.

A skill lives in `.agents/skills/<name>/`, which `.claude/skills` links to,
MUST name its files relative to its own directory, and is linked by `install`
into every session.
