---
name: {{The skill's name, the same as its directory's.}}
description: >-
  Use {{when the agent needs the source: the topics, tasks, or questions that
  depend on it}}. Retrieves {{what}} from {{where}}, since what the agent
  remembers of it is not a source.
---

# {{The source's name}}

Run `fetch`, which sits beside this file, {{with the arguments it takes}}:

    <this skill's directory>/fetch {{An example argument, or none.}}

{{What fetch prints, and that it exits non-zero on a bad argument or a source it cannot reach.}}

{{Either: fetch caches each page under `${XDG_CACHE_HOME:-~/.cache}/<name>/` after its first retrieval, because the source is not revised. Or: fetch retrieves the source every time, because it changes.}}

## Precedence

What the agent remembers of {{the source}} MUST NOT be the source of any
answer.

- Every answer about {{the source}} MUST come from what the agent fetches in
  the same turn.
- Every claim about {{the source}} MUST cite `{{The citation form, such as <slug>#<anchor>.}}`.
  A claim that cannot be cited MUST NOT be made; the agent MUST say {{the
  source}} does not cover it.
- {{Who holds the copyright, and what the agent MAY quote and MUST NOT copy into a repository. Or: the source carries no restriction, and why.}}
