# brianlan/skills

A curated collection of **Agent Skills** for code refactoring and quality. Each skill follows the open [Agent Skills](https://agentskills.io/specification) standard, so it works across Claude Code, Codex, Gemini CLI, OpenCode, Cursor, pi-agent, and other compatible agents.

## refactoring

### reveal-core-logic
Refactors existing code so its **core workflow is immediately visible** at the top, with implementation details unfolding through coherent semantic layers. It helps you read and understand complex code quickly by exposing the narrative before the mechanics, so the code's real purpose is never buried.

### reduce-defensive-validation
Reviews a code scope and **surgically removes low-value defensive checks** while preserving behavior, interfaces, and regression tests. It makes the happy path readable and trustworthy, keeping only the guards that genuinely protect semantics and contracts instead of checks that merely obscure the real logic.

---

These skills are installable directly from this repository:

```bash
# Recommended: install globally for the agents you use
npx skills add brianlan/skills -g -a claude-code codex opencode pi
```

> `-g` installs globally (available in all your projects). `-a` targets specific agents — `pi` is the identifier for pi-agent. Adjust the `-a` list to match the agents you actually use.

## License

[MIT](LICENSE).
