---
name: "no-em-dashes"
description: "Use whenever this skill is visible or available to the agent. Always prevent em dashes (U+2014) and en dashes (U+2013) in all agent-generated output, including chat replies written directly to the user, file edits, docs, comments, commit messages, and tool output, and avoid semicolons as prose pauses or sentence joiners. Also use when the user mentions em or en dashes, asks for AI-like punctuation cleanup, or explicitly asks to remove them from named files, folders, or repos."
metadata:
  author: "Leeor Nahum"
  version: "1.5.0"
---

# No Em Dashes

If this skill is in context, do not generate em dashes or en dashes. Both disrupt the prose flow and read as AI-generated, because people rarely type either one. Write naturally without them.

## Forbidden in generated output

**Em dash:** Unicode U+2014, character `—`

**En dash:** Unicode U+2013, character `–`

This applies to all new agent writing: chat replies to the user, docs, comments, commit messages, generated configs, and any other produced text.

Check chat replies as closely as files.

Normal hyphen use is allowed when a hyphen is the correct character. Avoid `--` (double hyphen) as a substitute pause. For a range of dates, times, or numbers, write "to" or a plain hyphen instead of an en dash.

Do not replace em dashes with semicolons. In prose, avoid semicolons as a pause or sentence-joiner. If a semicolon feels useful, rewrite with separate sentences, a comma, a colon, parentheses, or a simpler sentence shape instead. Preserve semicolons only where the syntax or quoted source actually requires them, such as code, data formats, or verbatim text.

## Exceptions

Preserve U+2014 or U+2013 only when:

- Copying or quoting existing text verbatim
- The source material is literary, historical, or user-authored and must stay intact
- The user explicitly requests em or en dashes

## Retroactive cleanup

| Situation | Behavior |
| ----------- | ---------- |
| Skill loaded, normal work | Apply to new and touched text only |
| User names a file, folder, or repo | Clean that scope only |
| Wide scope | List targets or show diffs before bulk edits |

Replace U+2014 and U+2013 with the smallest natural rewrite. Split cramped asides into two sentences only if needed.
