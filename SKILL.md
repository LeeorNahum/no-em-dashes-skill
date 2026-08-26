---
name: "no-em-dashes"
description: "Use whenever this skill is visible or available to the agent. Always prevent em dashes (U+2014) in all agent-generated output, including chat replies written directly to the user, file edits, docs, comments, commit messages, and tool output, and avoid semicolons as prose pauses or sentence joiners. Also use when the user mentions em dashes, asks for AI-like punctuation cleanup, or explicitly asks to remove em dashes from named files, folders, or repos. Full-repo retroactive cleanup only on explicit user request for that scope."
metadata:
  author: "Leeor Nahum"
  version: "1.4.0"
---

# No Em Dashes

If this skill is in context, do not generate em dashes. Em dashes disrupt the prose flow and read as AI-generated. Write naturally without that character.

## Forbidden in generated output

**Em dash:** Unicode U+2014, character `—`

This applies to all new agent writing: chat replies to the user, docs, comments, commit messages, generated configs, and any other produced text.

**The surface most often missed is the reply to the user.** Files get checked, because a file can be grepped, diffed and reviewed, so a skill like this one reads as repository hygiene and gets applied there. Chat output gets none of that scrutiny, and it is the one surface the user actually reads. A session that leaves every file clean while writing em dashes into every message has failed this skill completely, not partially. Check your own prose as you write it, not just the files you touch.

Normal hyphen use is allowed when a hyphen is the correct character. Avoid `--` (double hyphen) as a substitute pause.

Do not replace em dashes with semicolons. In prose, avoid semicolons as a pause or sentence-joiner. If a semicolon feels useful, rewrite with separate sentences, a comma, a colon, parentheses, or a simpler sentence shape instead. Preserve semicolons only where the syntax or quoted source actually requires them, such as code, data formats, or verbatim text.

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
| Skill loaded, normal work | Apply to new and touched text only |
| User names a file, folder, or repo | Clean that scope only |
| Wide scope | List targets or show diffs before bulk edits |

Replace `—` with the smallest natural rewrite. Split cramped asides into two sentences only if needed. Do not make `;` the replacement.
