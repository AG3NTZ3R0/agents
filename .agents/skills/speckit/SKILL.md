---
name: speckit
description: >-
  Use for every question or task that involves Spec Kit (github/spec-kit) or
  the specify CLI. Upgrades specify and the current project's Spec Kit files,
  then syncs Spec Kit's user documentation at the latest release, since what
  Claude remembers of Spec Kit is out of date.
---

# Spec Kit

Run `fetch` with no arguments, from the project directory when there is one:

    .agents/skills/speckit/fetch

It upgrades the installed `specify` CLI when it trails the latest release.
When the current directory holds `.specify/`, it then runs `specify
integration upgrade` and `specify extension update` there, which refresh the
project's Spec Kit commands and templates and leave its specs, constitution,
and code alone.

It then syncs `docs/` and `spec-driven.md` from `github/spec-kit` at the latest
release into a cache directory named for that tag, and prints the versions,
the cache path, the release notes since the installed version when it was
behind, and `docs/toc.yml`.

`docs/toc.yml` indexes Spec Kit's user documentation; its `href` paths are
relative to `docs/`. `spec-driven.md` is the full methodology the README
points users to. Together they are the documentation this skill covers.

## Precedence

What Claude remembers of Spec Kit MUST NOT be the source of any answer.

- Every question about Spec Kit MUST be answered from pages Claude reads from
  the cache in the same turn. A page read in an earlier turn MUST be read
  again.
- Claude MUST read `docs/index.md` and `docs/reference/overview.md` the first
  time it uses this skill in a session, and MUST choose further pages from
  `docs/toc.yml`.
- Every claim about Spec Kit MUST cite `path:line@tag`. A claim that cannot be
  cited MUST NOT be made; Claude MUST say the documentation at that tag does
  not cover it.
- Commands and flags MUST be confirmed with `specify <command> --help`, which
  governs where it and the documentation disagree.
- Contributor documentation outside `docs/toc.yml` and `spec-driven.md`
  (`design/`, `AGENTS.md`, `CONTRIBUTING.md`, `*/ARCHITECTURE.md`) MUST NOT be
  used unless the user asks about Spec Kit's internals.

## Reporting

Claude MUST report any upgrade `fetch` performed or failed to perform. When it
printed release notes, Claude MUST name the versions the CLI moved between and
summarize what those releases added or changed.
