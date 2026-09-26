---
name: environment
description: >-
  Use to update, inspect, or explain Claude's own environment: the AGENTS.md
  and skills installed from the agents repository into every session.
---

# Environment

Claude's instructions and skills come from one git repository, cloned once
per machine. Its `install` links `AGENTS.md` to `~/.claude/CLAUDE.md` and
each skill in `.agents/skills/` to `~/.claude/skills/<name>`, so every session
in every repository reads them from that clone. `INSTALLATION.md` there
covers the first setup, which has to be done by hand.

Run `sync`, which sits beside this file:

    <this skill's directory>/sync

It finds the clone by resolving its own link, pulls `main` fast-forward only,
and reruns `install`, which links new skills and removes links to deleted
ones. It prints the clone's path and the commits and files that changed. It
refuses and exits non-zero when the clone is off `main` or has uncommitted
changes.

A change to `AGENTS.md` or to a skill's description takes effect in the next
session, not the current one; Claude MUST say so when `sync` reports one.
