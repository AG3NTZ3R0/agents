---
name: rfc
description: >-
  Use when the published text of an RFC is needed. Retrieves it by number
  from the RFC Editor.
---

# RFC

Run `fetch`, which sits beside this file, with the RFC number alone:

    <this skill's directory>/fetch 2119

It prints `https://www.rfc-editor.org/rfc/rfc<number>.txt` as published, and
exits non-zero if the argument is not a number or the RFC does not exist.
