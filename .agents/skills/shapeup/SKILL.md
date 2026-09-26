---
name: shapeup
description: >-
  Use for every question or task that involves Shape Up, Basecamp's product
  development method: shaping, appetite, pitches, betting, or cycles.
  Retrieves the book's index and chapters from basecamp.com/shapeup, since
  what the agent remembers of it is not a source.
---

# Shape Up

Run `fetch`, which sits beside this file, with no arguments to print the
book's index:

    <this skill's directory>/fetch

The index lists each part, each chapter's slug and title, and each section's
slug and anchor. Run `fetch` with a chapter's slug to print that chapter,
with each heading's anchor in braces:

    <this skill's directory>/fetch 1.5-chapter-06

The book is not revised, so `fetch` caches each page under
`${XDG_CACHE_HOME:-~/.cache}/shapeup/` after its first retrieval.

## Precedence

What the agent remembers of Shape Up MUST NOT be the source of any answer.

- Every answer about Shape Up MUST come from chapters the agent fetches in
  the same turn. A chapter read in an earlier turn MUST be fetched again.
- The agent MUST fetch the index the first time it uses this skill in a
  session, and MUST choose chapters from it.
- Every claim about Shape Up MUST cite `<slug>#<anchor>`, such as
  `1.5-chapter-06#ingredient-2-appetite`. A claim that cannot be cited MUST
  NOT be made; the agent MUST say the book does not cover it.
- The book is copyrighted by 37signals. The agent MUST NOT copy its text into
  a repository; it MAY quote short passages in an answer.
