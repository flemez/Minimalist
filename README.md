# Minimalist

Eine kleine App fürs Handy, um bewusst zu verwalten, was man besitzt.

Du legst **Räume** an, trägst pro Raum die **Artikel** ein, die dort untergebracht
sind, bewertest ihren **Nutzen** und hältst fest, ob sie **oft, selten oder nie**
genutzt werden. So siehst du auf einen Blick, was in einem Raum steht und was
davon eigentlich weg kann. Optional legst du pro Raum ein **Ziel** fest (wie viele
Artikel maximal drin sein sollen).

## Grundprinzip: alles bleibt lokal

- **Keine Daten im Internet, kein Server, keine Cloud.**
- Alle Räume und Artikel werden ausschließlich lokal auf dem Gerät gespeichert
  (im Browser-Speicher des Handys).
- Zum Übertragen auf ein anderes Handy gibt es **JSON-Export/Import** – eine
  Datei, die du selbst weitergibst (z. B. per Messenger, Mail oder Kabel).

## Funktionen (erste Version)

- Räume anlegen, umbenennen, löschen
- Artikel pro Raum mit **Nutzen (1–5 Sterne)**, **Nutzung (oft/selten/nie)** und Notiz
- Übersicht pro Raum: Anzahl, wie viele oft bzw. nie genutzt werden
- **Ziel pro Raum** mit Fortschrittsanzeige
- Filter nach Nutzung
- **JSON-Export** (Backup / Umzug) und **JSON-Import** (hinzufügen oder ersetzen)
- Funktioniert **offline** und ist als App auf dem Homescreen installierbar (PWA)

## Ausprobieren

Es ist eine PWA (Web-App), es muss nichts kompiliert werden.

**Am Handy (empfohlen, mit Installation & Offline):**
1. Die Dateien auf einen einfachen Webserver legen (z. B. GitHub Pages) und die
   Seite im Handy-Browser öffnen.
2. Im Browser-Menü „Zum Startbildschirm hinzufügen“ wählen – danach läuft sie
   wie eine normale App, offline.

**Schnell am Computer testen:**
```bash
# im Projektordner
python3 -m http.server 8000
# dann http://localhost:8000 im Browser öffnen
```

> Hinweis: Der Service Worker (Offline-Modus) braucht `http(s)://` oder
> `localhost`. Öffnet man `index.html` direkt per Doppelklick (`file://`),
> funktioniert die App trotzdem – nur ohne Offline-Cache.

## Dateien

- `index.html` – die komplette App (Oberfläche + Logik, keine externen Libraries)
- `manifest.webmanifest` – PWA-Manifest
- `sw.js` – Service Worker (Offline-Cache, sendet nichts nach außen)
- `icon.svg` – App-Icon

## Status

Erste Version. Die **Nutzen-Gewichtung** ist aktuell als 1–5-Sterne-Bewertung
umgesetzt – das Modell dafür ist noch nicht final und kann angepasst werden.
