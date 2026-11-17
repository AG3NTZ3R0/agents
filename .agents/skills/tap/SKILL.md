---
name: tap
description: >-
  Use when the user asks to put a source on tap. Builds a skill that
  retrieves the source the user names when it runs.
---

# Tap

The agent MUST copy `template.md`, which sits beside this file, to
`.agents/skills/<name>/SKILL.md` in the current project, fill it from the
source the user names, and write the `fetch` it describes.

The agent MUST run `fetch` once, then run `check` and fix the skill until it
passes:

    <this skill's directory>/check <skill-directory>
