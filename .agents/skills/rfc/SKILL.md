---
name: rfc
description: >-
  Use when an RFC is to be added to this repository. Retrieves the published
  text for a given RFC number and writes it under rfc/.
---

# RFC

Run `fetch` with the RFC number alone:

    .agents/skills/rfc/fetch 2119

It retrieves `https://www.rfc-editor.org/rfc/rfc<number>.txt`, writes it
verbatim to `rfc/rfc<number>.txt`, and prints the path. It writes nothing and
exits non-zero if the argument is not a number or the RFC does not exist.

`DEVELOPMENT.md` governs the file once it is written.

@DEVELOPMENT.md
