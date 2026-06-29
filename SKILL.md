---
name: "no-em-dashes"
description: "Use whenever this skill is visible or available to the agent. Always prevent em dashes (U+2014) in all agent-generated replies, text, edits, docs, comments, commit messages, and tool output. Also use when the user mentions em dashes, asks for AI-like punctuation cleanup, or explicitly asks to remove em dashes from named files, folders, or repos. Full-repo retroactive cleanup only on explicit user request for that scope."
metadata:
  author: "Leeor Nahum"
  version: "1.2.0"
---

# No Em Dashes

If this skill is in context, do not generate em dashes. Em dashes disrupt the prose flow and read as AI-generated. Write naturally without that character.

## Forbidden in generated output

**Em dash:** Unicode U+2014, character `—`

This applies to all new agent writing: replies, docs, comments, commit messages, generated configs, and any other produced text.

Normal hyphen use is allowed when a hyphen is the correct character. Avoid `--` (double hyphen) as a substitute pause.

Semicolons are the most common direct fallback for em dashes. Do not use a semicolon to join what should be two sentences, or to create a pause where an em dash would otherwise go. If the semicolon only exists because an em dash would have fit there, remove the pause: write two sentences, use a comma, or restructure the clause.

## Exceptions

Preserve U+2014 only when:

- Copying or quoting existing text verbatim
- The source material is literary, historical, or user-authored and must stay intact
- The user explicitly requests em dashes

## While writing

Compose without U+2014 from the start.

## Retroactive cleanup

| Situation | Behavior |
| ----------- | ---------- |
| Skill loaded; normal work | Apply to new and touched text only |
| User names a file, folder, or repo | Clean that scope only |
| Wide scope | List targets or show diffs before bulk edits |

Replace `—` with the smallest natural rewrite. Split cramped asides into two sentences only if needed.
