---
name: speckit
description: >-
  Use before any work that involves Spec Kit (github/spec-kit). Retrieves the
  current upstream sources that define it, since what Claude remembers of Spec
  Kit is out of date.
---

# Spec Kit

Run `fetch` with no arguments:

    .agents/skills/speckit/fetch

It sparse-clones `github/spec-kit` at the tag matching the installed
`specify` CLI, or the latest release when none is installed, and concatenates
the files listed in `fetch` into one temporary Markdown file, each headed by
its repository, tag, and path. It prints that file's path. It exits non-zero
and names the path if one no longer exists at that tag.

Claude MUST read the printed file in full before answering about Spec Kit,
MUST treat it over anything remembered, and MUST delete it once read. Where it
and `specify <command> --help` disagree, the CLI governs.

When `fetch` fails on a missing path, Claude MUST report it and MUST NOT fall
back to memory; the path list in `fetch` is to be corrected against
`docs/toc.yml` upstream.
