---
name: rfc
description: >-
  Use when the published text of an RFC is needed. Retrieves it by number
  from the RFC Editor, since what the agent remembers of it is not a source.
---

# RFC

Run `fetch`, which sits beside this file, with the RFC number alone:

    <this skill's directory>/fetch 2119

It prints `https://www.rfc-editor.org/rfc/rfc<number>.txt` as published, and
exits non-zero if the argument is not a number or the RFC cannot be reached.

`fetch` caches each RFC under `${XDG_CACHE_HOME:-~/.cache}/rfc/` after its
first retrieval, because an RFC is not revised once published.

## Precedence

What the agent remembers of an RFC MUST NOT be the source of any answer.

- Every answer about an RFC MUST come from what the agent fetches in the same
  turn.
- Every claim about an RFC MUST cite `RFC <number> §<section>`, such as
  `RFC 2119 §1`. A claim that cannot be cited MUST NOT be made; the agent
  MUST say the RFC does not cover it.
- Each RFC names its copyright holder in its own text. The agent MAY quote
  short passages in an answer, and MUST NOT copy an RFC into a repository.
