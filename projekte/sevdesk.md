# sevDesk-Buchhaltung PediSarah

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

Rechnungen und Belege für PediSarah (Kleinunternehmerin §19, 0 % USt) per API-Skript.

- Rechnungen: `~/Claude/sevdesk/sevdesk_invoice.py --kunde … --artikel … --betrag … --datum TT.MM.JJJJ`, Log `angelegt.csv`.
  API-Token liegt in `~/.sevdesk_token`.
- Eingabe meist als **Quittungsfoto** oder diktiert (Name, Betrag, Datum).
- Regeln:
  - Immer als **Entwurf** anlegen.
  - Artikel aus dem Preis erschließen: 29,80 → 1017, 25,80 → 1019, 21 → 2021, 27,80 → 1005, 24 → 1021, 28 → 1020.
    Fahrtkosten (Artikel 1003) als Zusatzposition, wenn die Kundenhistorie das so hat. Nur Artikel aus Kategorie „Dienstleistung“.
  - Zahlungsart **Bargeld** (Quittungsblock), nicht SEPA.
  - Nummernkreis: RE-2025-308 bis 347 voll, weiter ab **RE-2025-351**; bei Kreisende stoppen und Bescheid sagen.
  - Doppelte Kontakte: den nehmen, auf den die **letzte Rechnung** lief, nicht nachfragen.
- Umsatz = Summe aller Rechnungen inkl. Stornorechnungen, **eine** Zahl nennen, Stornos nicht extra ausweisen.
- Belege (Ausgaben): `sevdesk_beleg.py` (z. B. HP Instant Ink, Konto Bürobedarf), Betrag negativ buchen, PDFs in `~/Sevdesk/<Lieferant>/`.
