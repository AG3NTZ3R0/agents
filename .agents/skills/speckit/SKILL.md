---
name: speckit
description: >-
  Use before any work that involves Spec Kit (github/spec-kit). Upgrades the
  specify CLI and the current project's Spec Kit files, then retrieves the
  upstream sources that define Spec Kit's architecture, since what Claude
  remembers of Spec Kit is out of date.
---

# Spec Kit

Run `fetch` with no arguments, from the project directory when there is one:

    .agents/skills/speckit/fetch

It upgrades the installed `specify` CLI when it trails the latest release.
When the current directory holds `.specify/`, it then runs `specify
integration upgrade` and `specify extension update` there, which refresh the
project's Spec Kit commands and templates and leave its specs, constitution,
and code alone.

It then sparse-clones `github/spec-kit` at the latest release and concatenates
the files listed in `fetch`, in that order, into one temporary Markdown file,
each headed by its repository, tag, and path: the product, its history, its
methodology, its primitives, their architecture, and the processes an agent
runs. When the CLI was behind, the release notes since the installed version
follow, and `docs/toc.yml` closes the file as an index of what was left out.
It prints the file's path, and exits non-zero naming the path if one no
longer exists at that tag.

Claude MUST read the printed file in full before answering about Spec Kit,
MUST treat it over anything remembered, and MUST delete it once read. Where it
and `specify <command> --help` disagree, the CLI governs. For a page the file
leaves out, Claude SHOULD read it upstream at the same tag rather than recall
it.

Claude MUST report any upgrade `fetch` performed or failed to perform. When
the file carries release notes, Claude MUST name the versions the CLI moved
between and summarize what those releases added or changed.

When `fetch` fails on a missing path, Claude MUST report it and MUST NOT fall
back to memory; the path list in `fetch` is to be corrected against
`docs/toc.yml` upstream.
