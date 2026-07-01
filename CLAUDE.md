# CLAUDE.md — awesome-nano-banana-pro

Kuratierte Sammlung von **Nano-Banana-Pro** (Gemini 3 Pro Image) Bild-Fällen
(Prompt + Ergebnis, 180+ Cases). Dient als Quelle für den Skill `nano-banana-pro`
im Ökosystem. **README.md wird per GitHub-Action auto-generiert** — nicht von Hand
editieren (Änderungen dort gehen verloren); diese CLAUDE.md ist die stabile Ablage.

Dieses Repo gehört zum **dbt94 / Bizzplug Claude-Code-Ökosystem**. Die verbindlichen
Regeln stehen zentral in [`AgentsandSkills`](https://github.com/dbt94/AgentsandSkills)
(`rules/GLOBAL-RULES.md`) und gelten für **jedes** Repo.

## Automatische Installation — nie manuell

**Alle Claude-Code-Installationen laufen automatisch; der User installiert nie von Hand.**
Ein zentraler SessionStart-Hook `~/.claude/hooks/auto-install.sh` (aus `AgentsandSkills`)
stellt bei jedem Session-Start idempotent sicher:

1. Skills/Agenten/Regeln in `~/.claude` (via `install.sh` der Ökosystem-Repos),
2. globale CLI-Tools aus der Registry `config/auto-install.tools` (eine Zeile pro CLI, z. B. `agent-browser`),
2b. automatisch entdeckte skill-eigene `auto-install.sh` (leichtes Setup); schwer/On-Demand → `install-deps.sh`,
3. den Browser-Executable-Pfad (vorinstalliertes Chromium → `AGENT_BROWSER_EXECUTABLE_PATH`).

Bringt ein neuer Skill CLI-/Setup-Bedarf mit → Schritt in `auto-install.sh`
(in `AgentsandSkills` + `bizzplug`) ergänzen. Vollständig:
`AgentsandSkills/rules/GLOBAL-RULES.md` → „AUTOMATISCHE INSTALLATION".

> Hinweis: App-eigene Abhängigkeiten dieses Repos (npm/pnpm/uv/pip) sind davon
> getrennt und gehören zum jeweiligen App-Setup (siehe README).

## Kernregeln (zentral — gelten hier ebenso)

- **Nie hart löschen** → Soft-Delete ins Archiv-Repo (`safe-archive`), echtes Löschen nur auf Anweisung.
- **Secrets** ausschließlich via Env-Variablen / `.env` — niemals committen.
- **Vor dem Überschreiben** einer Datei zuerst `git log --oneline -5 -- <datei>` lesen.

Vollständige Regeln: `AgentsandSkills/rules/GLOBAL-RULES.md`.
