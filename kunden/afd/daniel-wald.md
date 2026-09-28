# Daniel Wald (wald-daniel.de)

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

Wahlkampfseite von Daniel Wald, AfD-Landtagsabgeordneter seit 2018, Wahlkreis 33 Merseburg, **Wiederwahl** am 06.09.2026.
Repo `msone-web-solutions/afd-daniel-wald`, Code `~/WebstormProjects/afd/daniel-wald`.

## Server
- Domain **wald-daniel.de** (nicht daniel-wald.de); wald.msone.cloud leitet per 301 dorthin.
- Webroot `/var/www/wald.msone.cloud` (kein Git), RAM-Cache `/dev/shm/wald_nginx_cache`, Backend 127.0.0.1:8081.
- Deploy: `npm run build`, rsync mit Ausschlüssen (`.git .env docs node_modules .idea scripts .babelrc .DS_Store .claude package*.json *.md *.jsx .gitignore`,
  **nicht** `design-system/`) plus `--delete-excluded`, dann `chown -R www-data`.
- Cookie-Gate war der letzte Staging-Schutz; Inhaltsseiten stehen auf `index, follow`.

## Fakten (vom Auftraggeber bestätigt)
- Jahrgang 1982, Merseburg; Koch und **Kaufmann im Gesundheitswesen** (immer voll ausschreiben).
- **Freiwilliger Wehrdienst** Luftwaffe, Jagdbombergeschwader 32 (2002–2004) – nicht „Soldat auf Zeit“.
- Drei Mandate: Landtag (seit 2018), **Kreistag Saalekreis** und Stadtrat Merseburg (seit 2019). Nicht „Landrat“.
- Verheiratet, eine Tochter (die Fraktionsbiografie „ledig“ ist veraltet).
- Kontakt: Landtagsbüro Domplatz 6-9, 39104 Magdeburg, Tel. 0391 560 6112, daniel.wald@afd-lsa.de.
- Social-Reihenfolge: TikTok, Facebook, Rest. WhatsApp-Kanal „WaldKulturErbe“ als eigener grüner Button.

## Inhalte
- Hero-Claim „Ihre Anliegen. / Meine Mission.“ (von den Flyern). „Vision 2026“ gehört der Fraktion und hat eine eigene Seite `vision.html`.
- **Genau 5 Themen:** Familie, Medien (Rundfunkstaatsvertrag kündigen), Industrie, Gesundheit, Energie. Nicht erweitern.
- Seite „Meine Arbeit im Landtag“ mit Ausschüssen, Kleinen Anfragen (nur per PADOKA-Original belegt) und allen 21 Reden.
- Wahlkampf-Single **„Für Herz und Region“** (Suno, VÖ 10.08.2026 über DistroKid, 3:24), Sektion `#song`, Kurz-URL wald-daniel.de/song.
  Keine Urheberrechts-Behauptung, Zeile „Musik KI-gestützt produziert“ ist freigegeben.
- Wahlkreisprognose WK 33 (Szenariorechnung von wahlkreisprognose-sachsenanhalt.de – **keine Umfrage**).
- Termine neu → alt sortiert, Flyer als WebP.

## Offen
- Kontrast des Markenblaus #009EE0 (3,01:1) – Markenentscheidung, `#0079AE` wäre die Lösung.
