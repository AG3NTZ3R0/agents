---
name: speckit
description: >-
  Use for every question or task that involves Spec Kit (github/spec-kit) or
  the specify CLI. Upgrades specify and the current project's Spec Kit files,
  then syncs Spec Kit's user documentation at the latest release, since what
  the agent remembers of Spec Kit is out of date.
---

# Spec Kit

Run `fetch`, which sits beside this file, with no arguments and from the
project directory when there is one:

    <this skill's directory>/fetch

It upgrades the installed `specify` CLI when it trails the latest release.
When the current directory holds `.specify/`, it then brings the project
current:

- `specify integration upgrade --force` replaces the project's Spec Kit
  commands, templates, and scripts with the release's, when the version its
  integration manifest records is not the installed CLI's. Specs, the
  constitution, and code are left alone.
- `specify extension update` updates installed extensions.
- `specify extension add` adds each bundled extension the project lacks.
- `specify workflow update` updates installed workflows.
- `specify workflow add` adds each bundled workflow the project lacks.
- `specify workflow add --dev` adds each workflow in the agents clone's
  `workflows/`, such as `guarded-sdd`, and re-adds one whose installed copy
  differs from the clone's.

Customizations to Spec Kit's behavior MUST go in a preset, never in the
managed files.

It then syncs `docs/` and `spec-driven.md` from `github/spec-kit` at the latest
release into a cache directory named for that tag, and prints the versions,
the cache path, the release notes since the installed version when it was
behind, and `docs/toc.yml`.

`docs/toc.yml` indexes Spec Kit's user documentation; its `href` paths are
relative to `docs/`. `spec-driven.md` is the full methodology the README
points users to. Together they are the documentation this skill covers.

## Initializing a project

To set up Spec Kit in a project, the agent MUST run `init`, which sits beside
this file, from the project directory with its own Spec Kit integration, such
as `claude` for Claude Code, and MUST NOT run `specify init` itself:

    <this skill's directory>/init <integration>

`init` runs `specify init --here` non-interactively with every bundled
extension, then `fetch`. In a project that already holds `.specify/`, it only
runs `fetch`.

## Precedence

What the agent remembers of Spec Kit MUST NOT be the source of any answer.

- Every question about Spec Kit MUST be answered from pages the agent reads
  from the cache in the same turn. A page read in an earlier turn MUST be read
  again.
- The agent MUST read `docs/index.md` and `docs/reference/overview.md` the
  first time it uses this skill in a session, and MUST choose further pages
  from `docs/toc.yml`.
- Every claim about Spec Kit MUST cite `path:line@tag`. A claim that cannot
  be cited MUST NOT be made; the agent MUST say the documentation at that tag
  does not cover it.
- Commands and flags MUST be confirmed with `specify <command> --help`, which
  governs where it and the documentation disagree.

## Reporting

The agent MUST report any upgrade `fetch` performed or failed to perform.
When it printed release notes, the agent MUST name the versions the CLI moved
between and summarize what those releases added or changed.
