# AfD-Kandidatenseiten – Überblick

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

msone baut Websites für AfD-Kandidaten und -Verbände in Sachsen-Anhalt (Landtagswahl 06.09.2026).
Code in `~/WebstormProjects/afd/`, alle auf dem Server 195.201.37.69.

| Projekt | Domain | Stand |
|---|---|---|
| uwe-arendt | uwe-arendt.de | live, Vorlage aller Seiten |
| daniel-wald | wald-daniel.de | live |
| phillipp-rau | phillipp-rau.de | live |
| paul-backmund | backmund.msone.cloud → paul-backmund.de | Staging hinter Cookie-Gate |
| saalekreis | afd-saalekreis.de | hinter Cookie-Gate |
| tillschneider / tillschneider2 | tillschneider.msone.cloud | Entwurf hinter Cookie-Gate |
| vision | – | Kampagne „Vision 2026“ |

## Gemeinsame Architektur („technisch wie daniel-wald“)
- Komplett selbst gehostet, keine CDNs: React-UMD, Babel, woff2-Schriften unter `libs/`.
- Quellen: `src/*.jsx` + `src/data.js` (`window.SITE`, alle Inhalte) + CSS in `src/` und `design-system/`.
- `npm run build`: check → Babel → Bundle → Seiten erzeugen → hash-assets (`?v=`) → Prerender (SSR, `hydrateRoot`) → Inline-CSS → hash-assets.
- Die HTML-Dateien im Root sind Auslieferung **und** Quelle, der Build verändert sie.
- Häufige Aufgabe: einen Claude-Design-Entwurf (claude.ai/design) in diese Architektur übertragen.
- nginx: RAM-Cache-Muster (infrastruktur/nginx-ram-cache.md). Staging per Cookie-Gate + `noindex`; Go-Live = Gate raus + `noindex` an **beiden** Stellen (HTML und Header) entfernen.

## Deploy – je Seite anders, vorher prüfen
- **phillipp-rau, paul-backmund, saalekreis:** Webroot ist ein Git-Checkout → vorher `git push`, dann `scripts/deploy.sh` bzw. `git pull` auf dem Server.
- **daniel-wald:** `scripts/deploy.sh` ist **veraltet** („NICHT AUSFUEHREN“). Deploy per rsync nach `/var/www/wald.msone.cloud` mit Pflicht-Ausschlüssen, immer erst `--dry-run`.
- **tillschneider:** rsync, kein Git-Webroot.
- Je Repo eigener read-only Deploy-Key auf dem Server.

## Sonntagsfrage
Liegt als `window.SITE.umfrage` in `src/data.js` von daniel-wald, phillipp-rau und tillschneider2.
Stand 10.08.2026 (INSA/BILD): AfD 42, CDU 22, Linke 13, SPD 6, BSW 5, Grüne 4, FDP 4, Sonstige 4.
