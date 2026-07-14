# AGENTS.md

Rules for editing the **no-em-dashes** skill. User-facing guidance lives in `SKILL.md`. `README.md` is the human skim layer.

## File roles

| File | Role |
| --- | --- |
| `SKILL.md` | The character rule, exceptions, and the retroactive cleanup table |
| `README.md` | Short human summary |

## Editing

- Bump `metadata.version` with semver in the same change whenever behavior changes: patch for wording, minor for new guidance, major for a changed scope.
- Quote every frontmatter string value. Keys stay unquoted.
- Keep the single literal U+2014 character reference in the "Forbidden in generated output" section intact. It is necessary technical content, not a style violation, the skill has to show the actual character once to define it unambiguously.
- Capitalized bullets and parallel list voice.

## Before finishing

- The one necessary literal em-dash reference is still present and correct.
- No new literal em dash introduced elsewhere in the file.
- `metadata.version` bumped if and only if behavior changed.
- `README.md` matches the actual file layout.
