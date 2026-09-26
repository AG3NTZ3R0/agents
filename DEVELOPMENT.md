# Development

This repository is written once and used everywhere. `install` links its
instructions and skills in at the user level of each machine it is cloned
onto, so every session in every repository starts with them. That decides what
may be added here.

A statement belongs here only if it holds in every repository an agent works
in. One that holds in a single repository would be false in all the others, so
it MUST NOT be added here; it belongs in that repository's constitution.

Terms are defined before requirements are stated, and requirements use the key
words of RFC 2119.

## Files

`README.md` states what this repository and the agentic software development
lifecycle are. `AGENTS.md` states what Claude does, in the terms `README.md`
defines, and references it. `README.md` MUST NOT instruct and `AGENTS.md` MUST
NOT define; a statement that does both MUST be split into one of each.

## Skills

A skill lives in `.agents/skills/<name>/`. `.claude/skills` links there so
skills are available while working here, and `install` links each one into
every session. A skill runs from whatever repository an agent is in, so it
MUST name its files relative to its own directory.

Documentation that changes upstream MUST NOT be copied here, because a copy
goes stale; a skill retrieves it at its current version.
