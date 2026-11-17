---
name: conventional-commits
description: >-
  Use when the agent writes, checks, or explains a commit message, or answers
  a question on commit types, scopes, footers, breaking changes, or how
  commits map to SemVer. Retrieves the Conventional Commits 1.0.0
  specification from the source of conventionalcommits.org, since what the
  agent remembers of it is not a source.
---

# Conventional Commits

Run `fetch`, which sits beside this file, with no argument:

    <this skill's directory>/fetch

It prints the whole specification as Markdown. It numbers each list item and
marks each `##` heading with its anchor on the website. It exits non-zero on
an argument or a source it cannot reach.

`fetch` caches the specification under
`${XDG_CACHE_HOME:-~/.cache}/conventional-commits/` after its first retrieval,
because version 1.0.0 is not revised.

## Precedence

What the agent remembers of Conventional Commits MUST NOT be the source of any
answer.

- Every answer about Conventional Commits MUST come from what the agent
  fetches in the same turn.
- Every claim about Conventional Commits MUST cite `#<anchor>`, and
  `#specification rule <number>` for a rule, such as `#specification rule 4`.
  A claim that cannot be cited MUST NOT be made; the agent MUST say
  Conventional Commits does not cover it.
- The specification is licensed CC BY 3.0. The agent MAY quote it with a
  citation, and MUST NOT copy it into a repository.
