# msone.cloud

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

Seit 16.09.2026 statisch (vorher Laravel `~/Herd/msone`). Code `~/Herd/msone-next` (lokal https://msone-next.test, Unterseiten mit `.html`).

- Live auf dem msone-Server 188.245.122.130, Webroot `/var/www/msone-static`, Backend :8083, RAM-Cache + Brotli.
- Deploy nur über `./deploy/deploy.sh` (konvertiert Unterseiten, stempelt Hashes; SSH-Port über `HETZNER_SSH_PORT`).
- Nur lokale Git-Commits, **kein Remote**.
- Unterseiten erzeugt `tools/convert.py` aus den alten Blade-Views – Inhalte dort ändern, nicht im erzeugten HTML. 404-Seite ist Pflicht.
- Strenge CSP: keine Inline-Styles/-Scripts.

## Konzept „Beweis statt Behauptung“
Der „Betriebsraum“ im Hero misst live aus dem Browser des Besuchers die Antwortzeiten der Kundenseiten
(siehe kunden/weitere-referenzen.md), dazu die Web Vitals des Aufrufs und echte Screenshots.
Design: Newsreader + Instrument Sans + JetBrains Mono, oklch-Farben, `light-dark()`. Seit 27.09.2026 mit neuem Logo.

## Vorgaben
- Campusy nirgends zeigen, Calendly raus, alle alten Unterseiten übernehmen (nicht umleiten).

## Offen
- Datenschutz gegenlesen lassen, Testimonial-Platzhalter, Search Console.
- Phase 2: serverseitiger Website-Check, Uptime Kuma.
