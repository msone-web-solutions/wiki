# Server

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

## 188.245.122.130 – Hetzner, Hostname `campusy-web` (msone-Server)
- SSH nur auf **Port 58022** (Port 22 seit 20.09.2026 zu): `ssh -p 58022 -i ~/.ssh/ms_one root@188.245.122.130`.
  Nur Schlüssel-Login, fail2ban sperrt nach 4 Fehlversuchen. Port steht in
  `/etc/systemd/system/ssh.socket.d/10-port.conf` (ein `Port` in `sshd_config` wirkt bei aktivem ssh.socket nicht).
- Hostet:
  - **msone.cloud** – statisch, Webroot `/var/www/msone-static`, Backend :8083
  - **pedisarah.de** – statisch, Backend :8082
  - Laravel-Projekt `~/Herd/msone` (Domain-Weiche): campusy.de, TSV, Preview-Subdomains
  - krone-geruestbau.de läuft inzwischen als statisches HTML (siehe kunden/krone-geruestbau.md)
- DNS aller msone-Projektdomains zeigt hierher.

## 195.201.37.69 – Hetzner (AfD-Kandidatenseiten)
- Ubuntu 24.04, nginx 1.24, Let's-Encrypt-Zertifikate mit Auto-Renew.
- Hostet: uwe-arendt.de, wald-daniel.de, phillipp-rau.de, afd-saalekreis.de, backmund.msone.cloud, tillschneider.msone.cloud.
- Server-Zugang und GitHub-Deploy-Keys: siehe kunden/afd/uebersicht.md.

## 188.245.187.123
- Hostet nur **malermeister-merseburg.de** (nginx). Kein SSH auf Port 22, Zugang unklar. Nicht mit dem msone-Server verwechseln.

## 49.13.218.218
- QuestLab School (Laravel), Webroot `/var/www/school.msone.cloud`.
- Login per Passwort (nicht per Schlüssel). **Offen:** auf Schlüssel-Login umstellen.
