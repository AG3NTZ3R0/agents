---
name: speckit
description: >-
  Use before any work that involves Spec Kit (github/spec-kit). Upgrades the
  installed specify CLI to the latest release and retrieves the upstream
  sources that define it, since what Claude remembers of Spec Kit is out of
  date.
---

# Spec Kit

Run `fetch` with no arguments:

    .agents/skills/speckit/fetch

It reads the installed `specify` version and, when it is behind the latest
release, runs `specify self upgrade`. That replaces the CLI alone; it does not
touch any project's files. It then sparse-clones `github/spec-kit` at the
latest release and concatenates the files listed in `fetch` into one
temporary Markdown file, each headed by its repository, tag, and path. When
the CLI was behind, the file opens with the release notes of every release
since the installed one. It prints the file's path, and exits non-zero naming
the path if one no longer exists at that tag.

Claude MUST read the printed file in full before answering about Spec Kit,
MUST treat it over anything remembered, and MUST delete it once read. Where it
and `specify <command> --help` disagree, the CLI governs.

When the file carries release notes, Claude MUST tell the user which version
the CLI moved from and to, and summarize what those releases added or changed.

Claude MUST NOT run `specify integration upgrade`, `specify extension update`,
or `specify init --force` without the user's approval; those rewrite project
files.

When `fetch` fails on a missing path, Claude MUST report it and MUST NOT fall
back to memory; the path list in `fetch` is to be corrected against
`docs/toc.yml` upstream.
