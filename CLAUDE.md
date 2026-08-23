# Minimalist

Eine App fürs Handy zum bewussten Verwalten von Besitz ("Minimalismus / Ausmisten").

## Idee
- Man legt **Räume** an und benennt sie.
- Pro Raum trägt man die **Artikel** ein, die dort untergebracht sind.
- Jeder Artikel bekommt eine **Nutzen-Gewichtung** und einen **Nutzungsstatus**
  (wird oft / selten / nie genutzt).
- Man sieht so, was in einem Raum ist und was wirklich genutzt wird und was nicht.
- Optional kann pro Raum ein **Ziel** definiert werden: wie viele Artikel man
  maximal im Raum haben möchte.
- **JSON-Export/Import**: Die komplette Liste (Räume + Artikel) kann als
  JSON-Datei exportiert und auf einem anderen Handy wieder importiert werden.

## Harte Projektregeln (WICHTIG — nie brechen)
- **Alles läuft strikt lokal auf dem Gerät.**
- **Keine Daten im Internet**, kein Backend, **kein Server**, keine Cloud,
  keine Analytics, keine externen Netzwerk-Requests.
- Datenspeicherung nur lokal (localStorage / Datei auf dem Gerät).
- Der einzige Weg, Daten zwischen Geräten zu bewegen, ist die manuelle
  JSON-Export/Import-Funktion.

## Technik
- Erste Version: **PWA** (installierbare Web-App), ein einzelnes `index.html`
  mit Inline-CSS/JS. Läuft offline, installierbar auf dem Homescreen.
- Keine externen Libraries/CDNs (passt zur "kein Internet"-Regel und macht
  Offline-Betrieb trivial).
- Sprache der Oberfläche: **Deutsch**.

## Struktur
- `index.html` — die komplette App (UI + Logik)
- `manifest.webmanifest` — PWA-Manifest
- `sw.js` — Service Worker für Offline-Betrieb
- `icon.svg` — App-Icon
