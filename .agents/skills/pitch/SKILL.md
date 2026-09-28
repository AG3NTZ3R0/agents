---
name: pitch
description: >-
  Use when the user asks to write up, draft, or file an idea as a Shape Up
  pitch. Fills the pitch's five ingredients from the conversation, asks for
  what is missing, and files the approved pitch as a GitHub issue labeled
  `pitch` in the current repository.
---

# Pitch

A pitch presents a shaped idea as a potential bet. This skill turns what the
user and the agent worked out in conversation into a GitHub issue that others
can read before deciding whether to bet on it.

## Ground in the book

The agent MUST load the `shapeup` skill, fetch `1.5-chapter-06`, and judge
each ingredient against it. When an ingredient needs more, the agent MUST use
the `shapeup` skill to find it.

## Fill the ingredients

The agent MUST gather each ingredient from the conversation so far, then ask
the user about each one that is missing or vague, one or two questions at a
time:

- **Problem**: REQUIRED. A specific story of what goes wrong today, not a
  feature request.
- **Appetite**: REQUIRED. How much time the idea is worth, such as two weeks
  or six weeks, and what that rules out.
- **Solution**: REQUIRED. The core elements of the approach, rough enough to
  leave the builders room for the details.
- **Rabbit holes**: OPTIONAL. Risky details, with how the pitch settles each.
- **No-gos**: OPTIONAL. What the pitch deliberately leaves out.

The agent MUST NOT draft the issue until every REQUIRED ingredient is filled.
It MUST derive each OPTIONAL ingredient from the conversation, and when it
finds none, MUST state why in the pitch. It SHOULD point out when the
ingredients do not fit each other, such as a solution too big for the
appetite or one that does not answer the problem. It MUST NOT add anything
the conversation did not raise.

## Draft

`template.md`, which sits beside this file, is the contract for every pitch's
body. The agent MUST copy it and replace each `{{...}}` placeholder with the
content the placeholder describes.

- The agent MUST keep every heading and bold field, in the template's order
  and spelled exactly as it spells them, and MUST NOT add, rename, or remove
  any.
- The `Size` field MUST be exactly one of the three sizes the template lists.
- A numbered or bulleted placeholder MUST become a list of that kind, one item
  per element, risk, or exclusion.
- An optional field or section with nothing in it MUST read
  `None identified: <reason>.`, where the reason says why the pitch has none.
- The body MUST NOT quote the book.

The title MUST read `Pitch: <idea>`, where `<idea>` names the idea in a few
words.

The agent MUST write the body to a temporary file and run `check`, which sits
beside this file, on it:

    <this skill's directory>/check <body-file>

It MUST fix the body until `check` passes, then show the user the title and
full body before filing.

## File

The agent MUST file only after the user approves the draft, and MUST revise
and show it again for any change the user asks for.

1. The agent MUST confirm the current directory is a GitHub repository with
   `gh repo view`, and MUST stop and say so when it is not.
2. When `gh label list --search pitch` shows no `pitch` label, the agent MUST
   ask the user before running
   `gh label create pitch --description "Shape Up pitch"`.
3. The agent MUST rerun `check` on the approved body, then file with
   `gh issue create --title "<title>" --label pitch --body-file <body-file>`,
   and MUST give the user the issue's URL.
