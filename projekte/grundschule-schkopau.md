# Grundschule „Astrid Lindgren“ Schkopau – neue Website

> Von Claude zusammengetragen (09.10.2026) – bitte prüfen und korrigieren.

Ehrenamtliches Projekt von Marcel (Vater eines Kindes der Schule) für grundschule-schkopau.de. Ziel: die Schulseite
neu, kindgerecht und barrierefrei aufbauen und dauerhaft pflegen; Inhalte von der bisherigen Landesseite
(gs-lindgren-schkopau.bildung-lsa.de) übernommen. Agenten-Board: #93 (Website), #110 (Video), #111 (Logo),
#115 (Passwortseite), #116 (Clay-Look, Rollout), #119 (Saison-Looks).

## Stand (09.10.2026)
- **Vorschau online** unter https://grundschule-schkopau.de – hinter einer Passwortseite, für Suchmaschinen gesperrt (noindex,
  robots Disallow). Passwort im Schlüsselbund `msone-vorschau-grundschule`; Direkt-Link ohne Tippen: `/#zugang=<passwort>`
  (der Teil hinter # geht nie an den Server).
- **Angebot an die Schule** per Mail an Herrn Rauchfuß (o.rauchfuss@gs-schkopau.schule) am 09.10.2026 verschickt:
  ehrenamtliche Übernahme inkl. Pflege, Vorschau-Link, Angebot zum gemeinsamen Durchgehen der Inhalte.
- Review (forseti) und QA (tyr) bestanden, Karte #116 auf „Freigabe ausstehend“.

## Look
- **Claymorphism / 3D-Knete** – fest für diese Seite, auch für alle späteren Bilder (Events, Ostern …).
  Weiche, matte Knete-Formen, Pastell mit warmen Akzenten, Licht oben links.
- Hero: Knete-Szene mit rotem Schwedenhaus, Birken, Bach, Sonne mit Gesicht (ElevenLabs, gpt-image-2.5).
- **Tag/Nacht nach Uhrzeit** (7–19 Uhr Tag), Nacht mit Glühwürmchen, umschaltbar per Knopf (12 h gemerkt).
- **Saison-Looks automatisch nach Datum**: Halloween 1.–31.10., Weihnachten 1.11.–26.12. (eigene Hero-Bilder Tag/Nacht,
  Saison-Knopf). Weitere Anlässe als neue Zeile in `clay.js` (`SAISONS`) + Bilder im Clay-Stil.
- Logo: Haus auf offenem Buch, Sonne mit Gesicht, als Vektor. Keine Lindgren-Figuren (Rechte), keine Kinderfotos/-namen.
- Knete-Icons für AGs und Termine (auch generische: Ferien, Elternabend, Zeugnis, Schulfest, Feiertag, Projekt, Winter).
- Startseite: Video „Wer war Astrid Lindgren?“ (Remotion, Sprecherin ElevenLabs v4, Musik Suno, Untertitel),
  Slider mit 8 Karten zur Namensgeberin, Termine, AGs, Team, Kontakt. Fußzeile „Made with ♥ by msone“.

## Technik
- Projekt `~/Herd/grundschule-schkopau` (statisch, `site/`), Git: privates Repo msone-web-solutions/grundschule-schkopau (main), **nie öffentlich machen** (`inhalt/` enthält Namen).
- Strenge CSP (keine Inline-Styles/-Scripts), Knete-Rezepte in `assets/css/clay-basis.css`, Handoff `design-clay.md`,
  Musterseite `site/bausteine.html` (wird nicht deployt).
- Server: msone-Webserver 188.245.122.130, nginx mit Cookie-Gate, Ansible `~/MsOne/ansible/playbooks/grundschule-vorschau.yml`.
- **Deploy**: `tools/deploy-vorschau.sh` (git-Export → Musterseite raus → `tools/versionieren.py` hängt `?v=<hash>` an alle
  Dateien → Playbook). Cache-Busting ist Pflicht, sonst zeigt Safari alte Stände.
- Tests: `tests/*.test.mjs` (Chrome + WebKit/Playwright für iPhone/iPad), `tools/pruefen.mjs`.
- Medien-Originale: `~/MsOne/valhalla/medien/grundschule-schkopau/` (mit `medien.md`).

## Gelernt
- iOS Safari: Tippen auf einen Link fokussiert den Kopf statt den Link – Menü darf das nicht als „verlassen“ werten;
  Menü unter dem klebenden Kopf als `position: fixed`; Tippen neben das Menü braucht `pointerdown`.
- Die Safari-Leiste verschiebt beim Scrollen die Position – eigene Scroll-Animationen nicht deshalb abbrechen.
- Schul-Mails laufen über Microsoft 365 (gs-schkopau.schule ist reine Mail-Domain).

## Offen vor dem echten Livegang
- Mit der Schule klären: Schulleitung und Träger im Impressum (Gemeinde Schkopau?), DDG statt TMG, Sekretariatszeiten,
  Krankmeldungs-Adresse, Text auf Slider-Karte 8, wer Inhalte liefert.
- Datenschutztext ergänzen (localStorage für Tag/Nacht/Saison, Cookie der Vorschau).
- noindex/Passwortseite raus, robots.txt, sitemap.xml, llms.txt (SEO-Bericht bragi), Search Console.
- Verhältnis zur Landesseite (Weiterleitung oder Hinweis), Mail-MX für info@grundschule-schkopau.de.
- Hero-Ladezeit im Saison-Look auf dem Handy (~4 s): Schriften/Logos verschlanken.
