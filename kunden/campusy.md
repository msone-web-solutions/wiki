# Campusy und QuestLab School

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

## Campusy (campusy.de, school.campusy.de)
- Lernplattform. Code `~/Herd/campusy`; campusy.de läuft über das Laravel-Projekt `~/Herd/msone` auf dem msone-Server.
- **school.campusy.de** ist live im Schulbetrieb, Alexa arbeitet täglich damit.
- Seit 16.09.2026: Änderungen nur **lokal committen**, kein Push und kein `./deploy.sh` ohne ausdrückliche Freigabe.
- Nie an Schultagen (Mo–Fr) zwischen 8:00 und 13:30 Uhr deployen – am 15.09.2026 hat ein Deploy um 08:45 einen laufenden Test zurückgesetzt.
- Sprechtexte für Lernvideos liegen in `~/Herd/campusy/database/content/**/*.sprechtext.txt` (z. B. Mathe Klasse 2).
- Farben/Schriften: Plus Jakarta Sans, Manrope. Campusy darf auf msone.cloud nirgends auftauchen.

## QuestLab School (school.msone.cloud)
- Laravel 11 + Livewire 4 (klassenbasierte Komponenten, keine Volt-SFCs), SQLite. Code `~/Herd/school` (lokal school.test).
- Login per Klassencode + Spitzname (kein E-Mail/Passwort). Echter Code u. a. für die Grundschule Schkopau, Klasse 2a.
- Server 49.13.218.218, Webroot `/var/www/school.msone.cloud`.
- Deploy per rsync **immer ohne** `database/database.sqlite` (die Daten leben nur auf dem Server), danach Rechte von `database/` auf www-data zurücksetzen.
- Git-Autor in diesem Projekt: `msone <kontakt@msone.cloud>`.

Offen: Wie hängen school.campusy.de und QuestLab School zusammen (Nachfolger, parallel)?
