---
name: no-em-dashes
description: Never use em dashes (U+2014) in any agent-generated text, edits, comments, commit messages, or tool output while this skill is loaded. Always active when present in context. Also use when the user mentions em dashes, wants AI-like punctuation cleaned up, or explicitly asks to remove em dashes from named files, folders, or repos. Full-repo retroactive cleanup only on explicit user request for that scope.
metadata:
  author: Leeor Nahum
  version: "1.0.1"
---

# No Em Dashes

If this skill is in context, do not generate em dashes. Em dashes kill the prose and read as AI-generated. Write naturally without that character.

## Forbidden in generated output

**Em dash:** Unicode U+2014, character `—`

This applies to all new agent writing: replies, docs, comments, commit messages, generated configs, and any other produced text.

Normal hyphen use is allowed when a hyphen is the correct character. Do not use `--` (double hyphen) as a substitute pause. Both kill the prose. Rewrite to flow naturally.

## Exceptions

Preserve U+2014 only when:

- Copying or quoting existing text verbatim
- The source material is literary, historical, or user-authored and must stay intact
- The user explicitly requests em dashes

## While writing

Compose without U+2014 from the start.

## Retroactive cleanup

| Situation | Behavior |
|-----------|----------|
| Skill loaded; normal work | Apply to new and touched text only |
| User names a file, folder, or repo | Clean that scope only |
| Wide scope | List targets or show diffs before bulk edits |

Replace `—` with the smallest natural rewrite. Split cramped asides into two sentences only if needed.
