# AGENTS.md

Rules for editing the **no-em-dashes** skill. User-facing guidance lives in `SKILL.md`. `README.md` is the human skim layer.

## File roles

| File | Role |
| --- | --- |
| `SKILL.md` | The character rule, exceptions, and the retroactive cleanup table |
| `README.md` | Short human summary |

## Editing

- Bump `metadata.version` by the release-versioning skill's rules for skills.
- Quote every frontmatter string value. Keys stay unquoted.
- Keep the single literal U+2014 character reference in the "Forbidden in generated output" section intact. It is necessary technical content, not a style violation, the skill has to show the actual character once to define it unambiguously.
- Capitalized bullets and parallel list voice.

## Design notes

- The chat reply is named in the body because it is the surface most often missed. A file can be grepped, diffed, and reviewed, so the skill tends to get applied as repository hygiene, while the reply gets none of that scrutiny and is the one surface the user actually reads. A session that leaves every file clean while writing em dashes into every message has failed the skill completely, not partially.

## Before finishing

- The one necessary literal em-dash reference is still present and correct.
- No new literal em dash introduced elsewhere in the file.
- `metadata.version` bumped as the release-versioning skill requires.
- `README.md` matches the actual file layout.
