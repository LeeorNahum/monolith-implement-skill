# Maintenance contract: monolith-implement

Rules for editing this skill. User-facing guidance lives in `SKILL.md`. `README.md` is the human skim layer.

## File roles

| File | Role |
| --- | --- |
| `SKILL.md` | The implementing methodology, in the order it runs: scope, grounding, cross-checking, applicable skills, layer coverage, building, subagent confirmation, reconfirming, and close-out |
| `README.md` | Short human summary |

## Editing

- Keep it manual-only. There is no frontmatter flag for this: manual-only behavior must live entirely in the `description` text (it already states the skill is strictly manual and must only be invoked by name). Never add a frontmatter key outside the six the specification defines to try to enforce this.
- The skill carries out a job the user states and finishes it. Planning a vague idea, pushing back on a plan, and hunting problems with no job stated belong to the monolith-audit skill. Keep that boundary: this skill asks what is wanted when no job is stated, and never grows a planning or interviewing step of its own. It needs no audit before it, and it verifies itself the whole way.
- Keep it usable for any deliverable. Software is one case, named where its layers are listed, and the rest of the wording fits a document, an agreement, an assignment, a model, or a skill equally. When a new line would only make sense for code, generalize it or put it under the software case.
- Keep it generic and placeholder-only. No real repo, vendor, provider, protocol, or project names belong in `SKILL.md`. Project-specific anchors (a docs URL, a directory to focus, a stack) live in the prompt that invokes the skill, never here.
- Name and link two sibling skills by their public share addresses, so an agent without them installed can still read them: subagent-spawn-book for choosing and spawning the critic, and anti-backrooms for the pass over what the change produces. Describe every other supporting tool by its function, such as an agent-skills bridge generator or a skill sync, and name no other sibling skill or product.
- Keep `SKILL.md` direct and short. This is a high-altitude methodology, not a tutorial. Prefer deleting a line over softening it.
- Bump `metadata.version` by the release-versioning skill's rules for skills.
- Quote every frontmatter string value. Keys stay unquoted.
- No em dashes, and no semicolons used to join what should be separate sentences. Use commas, periods, parentheses, or "to".
- Capitalized bullets, parallel phrasing.

## Before finishing

- No real repo, vendor, or project names snuck into `SKILL.md` or `README.md`.
- Manual-only stance still lives only in the `description` text, never as a frontmatter key.
- `metadata.version` bumped as the release-versioning skill requires.
- `README.md` matches the actual file layout.
