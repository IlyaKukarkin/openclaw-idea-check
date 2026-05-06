# 🚀 BOOT.md — Startup Checklist

Runs automatically on gateway restart (when `hooks.internal.enabled` is on).

## Checklist

1. **Verify workspace** — ensure `DATABASE.md` exists (create with headers if missing).
2. **Check `npx` availability** — quick test: `npx --version`. If missing, log error (user action required).
3. **Ready state** — reply `NO_REPLY`. This agent does not send startup messages.
