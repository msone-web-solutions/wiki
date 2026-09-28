# msone-Marke: Logo, Farben, Drucksachen

> Von Claude aus früheren Sessions zusammengetragen (28.09.2026) – bitte prüfen und korrigieren.

## Logo (neu seit 27.09.2026)
- Gefaltetes Band auf 45°-Raster (Cyan → Blau → Violett) mit violetter Kugel, darunter „msone“ und „WEB SOLUTIONS“ mit Linien.
  Von Marcel selbst gewählt; der „Figur“-Effekt (Kugel wirkt wie Kopf) ist bekannt und akzeptiert.
- Vektor-Nachbau `~/Claude/msone-logo-neu/build.py` erzeugt SVG/PNG in dunkel/hell, gestapelt/quer, Zeichen und Favicon.
  Schrift Quicksand (700 Wortmarke, 600 Unterzeile). Geometrie nur in build.py ändern, nicht in den SVGs.
- Auf msone.cloud seit 27.09.2026 live (SVG-Sprite, Favicon, OG-Bild). Das Signal-Blau der Website blieb.
- Altes Logo: M-Zickzack + Punkt, Verlauf #60a5fa → #2563eb, Kachel #0b0e13 – fand Marcel hässlich.

## Logo-Animation (Blender)
- `~/Claude/msone-logo-3d`: `logo.py` (altes Logo, 9 s) und `logo2.py` (neues Logo, Band faltet sich, Kugel fällt, 8 s).
- Ausgabe `out/msone-logo-neu-3d.mp4`. Nächster Schritt: Formate 1:1 / 9:16, Musik, Einbau in Spots.

## Interaktiver Mac-Hintergrund
- `~/Claude/msone-wallpaper` → App „msone Hintergrund“ in /Applications. three.js-Logo auf der Schreibtischebene,
  neigt sich zur Maus, Kugel folgt, Licht folgt. Rendert nur bei Bewegung.

## Drucksachen und Social
- Visitenkarte „Signal“, Instagram-Karussell, Profilbild (per Headless-Chrome gerendert).
- **Offen:** „EST. 2000“ auf der Signal-Visitenkarte entfernen (siehe arbeitsweise/texte-und-gestaltung.md).
