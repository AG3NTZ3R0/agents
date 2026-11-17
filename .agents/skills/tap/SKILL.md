---
name: tap
description: >-
  Use when the user asks to put a source on tap. Builds a skill that
  retrieves the source the user names when it runs.
---

# Tap

A tap skill retrieves an authoritative source when it runs. `template.md`,
which sits beside this file, is the contract for every tap skill.

The user names the source. The agent MUST NOT choose or replace it.

## Gather

The agent MUST find each of these from the source and the conversation, and
MUST ask the user one or two questions at a time for any it cannot find:

- **Source**: where the source the user named lives: a URL, or a local path
  the user saved when the source sits behind a login or a form.
- **Trigger**: the topics, tasks, or questions that depend on it.
- **Retrieval**: the arguments `fetch` takes, such as none for an index or an
  identifier for one page.
- **Freshness**: whether the source is revised, which decides whether `fetch`
  caches it.
- **Citation**: the form a claim cites, so the user can check it.
- **Rights**: who holds the copyright, and what the agent may quote.

## Build

The agent MUST build the skill in the current project's `.agents/skills/`.
When the source serves every repository and the current project is not the
agent's environment, the agent MUST say so and stop, so the user can build
it from the environment's clone instead.

1. The agent MUST copy `template.md` to `<name>/SKILL.md`, replace each
   `{{...}}` placeholder with what it describes, and keep every section and
   the Precedence rules as the template states them.
2. The agent MUST write an executable `fetch` beside it. `fetch` MUST print
   the source as text, and MUST exit non-zero with a usage line on a bad
   argument or a source it cannot reach.
3. The agent MUST run `fetch` against the source and show the user what it
   printed.
4. The agent MUST run `check`, which sits beside this file, on the new
   skill's directory, and fix the skill until it passes:

       <this skill's directory>/check <skill-directory>
