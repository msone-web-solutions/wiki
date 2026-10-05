# Valhalla (Claude-Harness) und Brain

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

- **Valhalla** (seit 05.10.2026 so benannt, vorher „Claude-Harness“): Repo `~/MsOne/valhalla` (GitHub `msone-web-solutions/valhalla`,
  angelegt 28.09.2026) enthält den kompletten Claude-Code-Harness:
  CLAUDE.md, settings.json, Skills, Agents, Commands, Tools. Seit 28.09.2026 ist `~/.claude` auf dem Mac ein Symlink auf dieses Repo (`scripts/install.sh`). Claude Code läuft nur auf dem Mac, es gibt keinen Claude-Server.
- **Brain** nach Karpathys „LLM Wiki“: Marcels Wissen liegt in `~/MsOne/wiki`, Claude verdichtet es nach `brain/<ordner>/`
  (Ordner wie im Wiki). Was Marcel im Gespräch mit „merke dir“ sagt, landet in `brain/claude/`.
- Skills: `/brain` (Sync, Fragen, Prüfen) und `merke-dir`.
