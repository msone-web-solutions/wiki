# Zusammenarbeit mit Claude

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

## Kommunikation
- Immer Deutsch. Code, Commits und Bezeichner dürfen dem Repo folgen.
- Nicht unnötig nachfragen, sinnvolle Standardentscheidungen selbst treffen und kurz nennen.

## Ergebnisse zeigen
- Marcel kann sich unter Standbildern wenig vorstellen: **bewegte Vorschauen mit Ton** schicken.
- Erst schnell und grob (z. B. 9:16 in niedriger Qualität, kapitelweise), dann verfeinern.
- Lange Renders gern nachts laufen lassen.

## Nutzungslimit
- Bei ca. 85–90 % des 5-Stunden-Limits laufende Workflows pausieren und nach dem Reset selbstständig fortsetzen.
- Bezahlte Extra-Nutzung nicht ausreizen.
- Nachts ohne Rückfrage durcharbeiten, wenn Marcel das vorher sagt.

## Git und Deploy
- Lokal iterieren. Fertige, geprüfte Stände dürfen ohne Rückfrage nach GitHub gepusht werden.
- **Prod-Deploy nur nach meiner Freigabe auf dem Agenten-Board** (msone ai dashboard, `/board`): Karte auf
  „Freigabe ausstehend“ setzen und warten, bis ich sie auf „Freigabe erteilt“ ziehe – erst dann deployen und auf „Live“.
  Gilt für alles, auch kleine technische Fixes und auch, wenn ich im Chat „deploy“ sage (seit 04.10.2026).
- Neue Seiten, Design- und Hero-Änderungen vorher lokal zeigen.
- Vor jedem Deploy prüfen: `npm run build` (enthält `npm run check`), `node -c` für Plain-JS wie `data.js`,
  JSON-LD-Blöcke validieren. Einmal ging eine leere Seite live, weil ein `"` in einem deutschen „…“-Zitat den String beendete.
- Referenzbilder, die Marcel ins Projekt legt (`PHOTO-*`, Screenshots, Plakate), nicht committen – sie gehören nach `docs/` (gitignored).
- Vor `git add -A` immer `git status` lesen.

## Werkzeuge
- Headless-Chrome immer mit eigenem `--user-data-dir`, sonst startet Marcels normales Chrome nicht.
- Arbeitet Marcel per Remote von einem anderen Gerät, kann er Browser-Freigaben nicht erteilen – dann über curl prüfen.
- Große PNGs als verkleinertes JPEG schicken (PNG > 3 MB bricht beim Senden ab).

## Fakten
- Keine Fakten erfinden: Preise, Zeiten, Einsatzorte, Zitate, Statistiken nur aus Quellen. Platzhalter sichtbar markieren.
- Bei Biografien gilt der offizielle Lebenslauf; Autorenschaft (z. B. Kleine Anfragen) nur über das Originaldokument bestätigen.
- Beim Klonen einer Vorlage alle `ld+json`-Blöcke durchgehen – dort bleiben Fremdinhalte unsichtbar stehen.
