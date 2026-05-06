# 🛠 TOOLS.md — Tool Notes & Conventions

> **Maintained by:** Idea Challenger
> **Purpose:** Document the tools and conventions used by this agent and the skills it invokes.

---

## Tool Index

### `exec` — Shell Command Execution
- **What it does:** Runs shell commands and captures output.
- **Typical use:** File operations, git, environment checks.
- **Convention:** Always use reasonable timeouts. Cap yield at `10000` ms for long-running commands.
- **Notes:** Not used for skill invocation — the Codex framework is applied directly, not via CLI.

### `write` — File Write
- **What it does:** Creates or overwrites files at the given path.
- **Typical use:** Saving skill output as `{idea-name}.md`, updating `DATABASE.md`.
- **Convention:** Use `exec` to build complex file content when `write` cannot handle it easily. Prefer `write` for simple/short updates.

### `edit` — Targeted File Edit
- **What it does:** Replaces exact text in an existing file.
- **Typical use:** Adding a new row to the `DATABASE.md` table without rewriting the whole file.
- **Notes:** Only use when the edit target is unique and non-overlapping. For table re-sorts, a full `write` is safer.

---

## Codex Startup Pressure Test Skill

- **Type:** Reasoning framework (SKILL.md + playbooks), not a CLI tool
- **Location:** `skills/codex-startup-pressure-test-skill/` (relative to workspace root)
- **Source files:**
  - `skills/codex-startup-pressure-test-skill/SKILL.md` — modes, output shape, scoring rules, constraints
  - `skills/codex-startup-pressure-test-skill/references/playbooks.md` — mode-specific checklists (pressure-test, problem-validation, competition-map, first-10-customers, mvp-plan)
- **Usage:** Read and apply the framework directly in your response. No external command invocation needed.

### Default Output Shape

```markdown
**Verdict**
Strong / Weak / Pivot required — 2-3 direct sentences.

**Scorecard**
| Area | Score | Read |
|---|---:|---|
| Pain intensity | 1-5 | ... |
| Buyer clarity | 1-5 | ... |
| Urgency | 1-5 | ... |
| Differentiation | 1-5 | ... |
| Speed to validate | 1-5 | ... |
| Founder advantage | 1-5 | ... |

**Core Assumption**
One sentence.

**Fatal Flaws**
| Risk | Severity | Why It Matters | Fast Test |
|---|---|---|---|

**Problem Reality**
- Pain: ...
- Early adopter: ...
- Vitamin or painkiller: ...

**Competition**
- Current behavior: ...
- Real enemy: ...
- Differentiation needed: ...

**First 10 Customers**
1. ...

**MVP**
- Build:
- Cut:
- 2-week test:
```

### Parsing targets (for DATABASE.md)
- **Verdict:** "Strong" / "Weak" / "Pivot required"
- **Scorecard:** Average of 6 area scores (1-5 each), e.g. "3.2/5"
- **Summary:** One-liner takeaway

### Version
- Installed from npm: `codex-startup-pressure-test-skill@latest`. Source files cached at `skills/codex-startup-pressure-test-skill/` (relative to workspace root). Re-run `npx ...@latest` to check for framework updates.

---

## General Conventions

### File Naming
- Idea output files: {sanitised-idea-name}.md (lowercase, hyphens, no special chars).
- Database: DATABASE.md (uppercase, no suffix beyond .md).
- All files live in the workspace root unless otherwise specified.

### DATABASE.md Format
- Single Markdown table.
- Columns: Idea | Tested | Verdict | Scorecard | Summary.
- Sorted by Verdict group (alphabetically), then Scorecard (descending).
- Each idea name linked to its output file: [Name](name.md).

### Git Integration — Post-Update Workflow

After every update to `DATABASE.md` (adding a new idea, re-sorting, or editing an existing row), the following git steps **must** be run immediately:

1. **`git add`** any changed files (the new `{idea-name}.md` output file and `DATABASE.md`).
2. **`git commit`** with a descriptive message summarising the change (e.g. `"Tested idea: Left-Handed Artist Box"`).
3. **`git push origin main`** — always push to `main`, no branching.

Conventions:
- Commit message format: `"Tested idea: {Display Name}"` for new ideas, `"Update database: {change summary}"` for revisions.
- Do not batch multiple unrelated ideas into one commit — each idea run gets its own atomic commit.
- If a push fails (network issue, auth), report the failure to the user but do not block — the local commit is already saved.

This workflow is also codified in `AGENTS.md` as a mandatory post-Step-5 step.

### Error Handling
- Framework evaluation failure → report error to user, do not create partial entry.
- Parsing failure → save the evaluation output as {idea-name}.md anyway, flag as "unparseable" in database.

---

## Adding New Tools

If the Codex skill changes its CLI interface or a new tool is added, update this file accordingly. Keep the convention descriptions precise enough to avoid trial-and-error.
