# GitHub

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

- Organisation **msone-web-solutions** (Konto Marcel Schneider). `gh` ist auf dem Mac nicht installiert; Push läuft über den osxkeychain-Helper.
- Bekannte Repos: `claude` (Claude-Harness), `wiki` (dieses Wiki), `afd-phillipp-rau`, `afd-daniel-wald`, `afd-paul-backmund`, `afd-saalekreis`,
  `afd-hans-thomas-tillschneider`, krone (Laravel).
- **Ohne Remote:** `~/Herd/msone-next` (msone.cloud) hat nur lokale Commits.
- Deploy-Keys: Ein SSH-Key kann nur bei **einem** Repo Deploy-Key sein. Deshalb je Seite ein eigener, read-only Key auf dem Server
  (z. B. `/root/.ssh/github_deploy_saalekreis` mit `Host github-saalekreis` in `/root/.ssh/config`).
