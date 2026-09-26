# Agentic Software Development Lifecycle

This repository is the environment an agent carries into every repository it
works in: the context and skills that hold wherever it works. `install` links
them in at the user level, so no project repository holds a copy.

A project's own principles are its constitution, kept in that project at
`.specify/memory/constitution.md`.

The agentic software development lifecycle is Spec-Driven Development as Spec
Kit defines it, under the authorities below. An authority is a source taken
over what an agent remembers.

## Fixed authorities

A fixed authority does not change once published. It is vendored here as
published.

### RFC 2119 — Key words for use in RFCs to Indicate Requirement Levels

@rfc/rfc2119.txt

### RFC 8174 — Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words

@rfc/rfc8174.txt

## Living authorities

A living authority changes with each release. It is never vendored; its skill
retrieves it at its latest release.

### Spec Kit — github/spec-kit

Spec Kit defines Spec-Driven Development and the `specify` CLI. The `speckit`
skill retrieves its user documentation.
