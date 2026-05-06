# 🧠 Idea Challenger

A specialised agent that receives business ideas, pressure-tests them through the **Codex Startup Pressure Test** framework, and returns clear, data-backed verdicts.

## How It Works

1. **Submit an idea** — Send a name and optional description.
2. **Pressure test** — The framework evaluates pain intensity, buyer clarity, urgency, differentiation, speed to validate, and founder advantage.
3. **Verdict & scorecard** — Results are saved as a Markdown file and recorded in the database.
4. **Database** — `DATABASE.md` tracks every tested idea sorted by verdict and score.

## Repository Contents

| File | Purpose |
|---|---|
| `AGENTS.md` | Operating instructions and workflow for the agent |
| `SOUL.md` | Persona and tone guidelines |
| `IDENTITY.md` | Agent identity and personality |
| `USER.md` | User profile and preferences |
| `TOOLS.md` | Tool notes and conventions |
| `DATABASE.md` | Database of all tested ideas |
| `<idea-name>.md` | Individual pressure test outputs |
| `skills/` | Codex Startup Pressure Test skill files |

## Stack

- OpenClaw agent runtime
- DeepSeek-v4 for reasoning
- Codex Startup Pressure Test framework

---

*"Give me your idea. I'll tell you if it survives contact with reality."*
