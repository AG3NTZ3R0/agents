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

The agent MUST load the `shapeup` skill and fetch `1.5-chapter-06` before
drafting, and MUST judge each ingredient against that chapter rather than
against memory. It MAY fetch the chapters on appetite (`1.2-chapter-03`) or
rabbit holes (`1.4-chapter-05`) when an ingredient needs more.

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

The agent MUST NOT draft the issue until the problem, appetite, and solution
are all filled. It SHOULD point out when the solution will not fit the
appetite or does not answer the problem. It MUST NOT invent content the user
did not give or agree to.

## Draft

The agent MUST show the user the full issue before filing it: a title that
names the idea in a few words, and this body:

    ## Problem

    ## Appetite

    ## Solution

    ## Rabbit holes

    ## No-gos

An optional section with nothing in it MUST read `None identified.` The body
MUST NOT quote the book.

## File

The agent MUST file only after the user approves the draft, and MUST revise
and show it again for any change the user asks for.

1. The agent MUST confirm the current directory is a GitHub repository with
   `gh repo view`, and MUST stop and say so when it is not.
2. When `gh label list --search pitch` shows no `pitch` label, the agent MUST
   ask the user before running
   `gh label create pitch --description "Shape Up pitch"`.
3. The agent MUST file with
   `gh issue create --title "<title>" --label pitch --body-file <file>`,
   writing the body to a temporary file, and MUST give the user the issue's
   URL.
