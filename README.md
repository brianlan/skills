# brianlan/skills

A personal collection of [Agent Skills](https://agentskills.io/specification) — reusable, cross-agent capability packages.

Skills follow the open **Agent Skills** specification: each skill is a directory containing a `SKILL.md` file with YAML frontmatter (`name` + `description`) plus optional `scripts/`, `references/`, and `assets/`. Because they follow the standard, skills here work across **Claude Code, Codex, Gemini CLI, OpenCode, Cursor, pi-agent**, and many other compatible agents.

## Directory layout

Skills are organized by **category** under `skills/`, which keeps the repo discoverable at scale while preserving the standard `skills/*/SKILL.md` convention.

```text
skills/
├── refactoring/
│   └── reveal-core-logic/
│       ├── SKILL.md              # required: frontmatter + instructions
│       ├── scripts/              # optional: executable code
│       ├── references/           # optional: docs loaded on demand
│       └── assets/               # optional: templates / static files
├── <another-category>/
│   └── <skill-name>/
│       └── SKILL.md
└── ...
```

## Install

Any of these installers can pull skills straight from this repo (no build/publish step needed):

```bash
# Vercel skills CLI (auto-detects your installed agents)
npx skills add brianlan/skills

# Only a specific category or skill
npx skills add brianlan/skills --skill reveal-core-logic

# GitHub CLI
gh skill install brianlan/skills
```

> Install only from trusted sources and audit a skill's files before using it — skills can include executable code.

## Available skills

### refactoring

- **reveal-core-logic** — Refactor existing code so its core workflow is immediately visible and implementation details unfold through coherent semantic layers.

## Adding a new skill

1. Create `skills/<category>/<skill-name>/`.
2. Add a `SKILL.md` with valid frontmatter:
   - `name` — lowercase letters/numbers/hyphens, must match the folder name.
   - `description` — what the skill does **and when to use it** (≤1024 chars). This is what agents match against to trigger the skill.
3. Keep `SKILL.md` lean (<500 lines). Move dense detail into `references/`, deterministic logic into `scripts/`, and templates into `assets/` (progressive disclosure).
4. Validate before committing:
   ```bash
   npx skills add brianlan/skills --list   # confirm the skill is discovered
   ```

## Conventions

- **Category** = a broad theme (`refactoring`, `documentation`, `testing`, …).
- **Skill name** = kebab-case, matches its folder and frontmatter `name`.
- **No `README.md` inside a skill folder** — keep instructions in `SKILL.md` / `references/`. Only this repo-level README exists for human visitors.

## License

[MIT](LICENSE). You are free to use and modify these skills; when you redistribute them (in whole or in part), you must retain the original copyright and license notice, preserving attribution to this repository.
