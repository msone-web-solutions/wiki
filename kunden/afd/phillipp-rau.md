# Phillipp Rau (phillipp-rau.de)

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

AfD Kreisverband Jerichower Land, live und öffentlich. Repo `msone-web-solutions/afd-phillipp-rau`.

- Webroot `/var/www/rau.msone.cloud` ist ein **Git-Checkout**; `scripts/deploy.sh` funktioniert, vorher `git push origin main`.
- RAM-Cache `/dev/shm/rau_nginx_cache`. vhost wird von `scripts/go-live.sh` erzeugt (einmalig, nicht von Hand ändern).
- Gebrandete 404-Seite.
- Kleine technische Fixes dürfen direkt live; optische Änderungen (z. B. Scrollytelling „Von der Mauer zur Kandidatur“) erst lokal zeigen.
- Dient als Engine-Basis für paul-backmund und tillschneider.
