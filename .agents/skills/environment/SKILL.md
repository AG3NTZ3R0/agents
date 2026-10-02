---
name: environment
description: >-
  Use to update, inspect, or explain the agent's own environment: the AGENTS.md,
  skills, and tools installed from the agents repository into every session.
---

# Environment

The agent's environment comes from one git repository, cloned once per
machine. Its `INSTALLATION.md` says what `install` sets up.

Run `sync`, which sits beside this file:

    <this skill's directory>/sync

It pulls `main` and reruns `install`, then prints the clone's path and what
changed.

A change to `AGENTS.md` or to a skill's description takes effect in the next
session, not the current one; the agent MUST say so when `sync` reports one.

The agent MUST report any `specify` upgrade `install` performed or failed to
perform. When it printed a changelog, the agent MUST name the versions the
CLI moved between and summarize what those releases added or changed.
