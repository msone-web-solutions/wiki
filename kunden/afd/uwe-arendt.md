# Uwe Arendt (uwe-arendt.de)

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

Erste Seite dieser Reihe und Vorlage für alle weiteren. Live seit Mai 2026.

- vhost `/etc/nginx/sites-available/uwe-arendt.de` liegt nur auf dem Server. RAM-Cache `/dev/shm/nginx_cache`, Backend :8080.
- Deploy: `bash scripts/deploy.sh` (Aufruf aus dem Projektroot).
- Repo-Aufbau: Root nur ausgelieferte Dateien, `scripts/` für Deploy, `docs/` gitignored für Arbeitsdateien und Referenzbilder.
- PageSpeed (30.05.2026): Desktop 100, Mobil real 95, Mobil-Lab ~88 (Grenze der Lantern-Simulation beim Bild-Hero).
