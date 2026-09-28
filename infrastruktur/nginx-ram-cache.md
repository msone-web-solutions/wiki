# nginx-Muster: RAM-Cache für statische Seiten

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

Standard-Aufbau für alle statischen Seiten (msone.cloud, pedisarah.de, AfD-Seiten):

- **Backend** auf 127.0.0.1:<port> liefert den Webroot mit Brotli + gzip aus.
- **Frontend** (:443) ist ein Reverse-Proxy mit Cache in `/dev/shm/<name>_nginx_cache` (tmpfs = RAM),
  Zone und `proxy_cache_path` in `/etc/nginx/conf.d/<name>-cache.conf`.
- **HTML wird nie gecacht** → Deploys sind sofort sichtbar.
- **Assets mit `?v=<hash>`** → RAM-Cache + `immutable`, 1 Jahr. Den Hash setzt der Build (`hash-assets.mjs`) bzw. `deploy.sh`.
- **Assets ohne `?v=`** → `no-cache`, `X-Cache-Status: BYPASS` (gewollt). Beim Prüfen daher immer die URL aus dem HTML nehmen.
- Cache-Purge ist fast nie nötig: neue Fassung = neuer Hash = neuer Cache-Key.
- Cache-Warmup nur mit URLs aus dem ausgelieferten HTML und mit `Accept-Encoding: gzip, deflate, br, zstd`
  (`Vary: Accept-Encoding` → eine Cache-Variante je Encoding).

## Fallen
- Cache-Zonen-Namen sind irreführend: `/dev/shm/nginx_cache` gehört **uwe-arendt.de**, nicht einer allgemeinen Seite.
  Vor jedem Purge den Pfad aus `/etc/nginx/conf.d` lesen, nie aus einem deploy.sh übernehmen.
- `scripts/nginx.conf.example` in den Repos ist nur Vorlage und hinkt dem echten vhost hinterher. Bei Fragen den vhost auf dem Server lesen.
- `noindex` kann doppelt gesetzt sein: im HTML **und** als `X-Robots-Tag`-Header im vhost. Prüfen mit `curl -sI <url> | grep -i x-robots`.
- Neue Asset-Typen (z. B. mp3, mp4) in `hash-assets.mjs` **und** in der Cache-Location des vhosts ergänzen.
- Strenge CSP auf msone.cloud und pedisarah.de: keine Inline-Styles, keine Inline-Scripts.
