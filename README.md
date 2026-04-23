# Chemie-Website · Anleitung

## Dateistruktur

```
chemie-website/
├── index.html          ← Startseite mit 4 Klassen-Karten
├── spf1.html           ← SPF 1. Klasse (Alles Dufte, Kernreaktionen, Juglon, Lumineszenz, Energieumwandlungen)
├── spf2.html           ← SPF 2. Klasse (Zucker, Indigo, Aspirin, Leitfähigkeit)
├── spf3.html           ← SPF 3. Klasse (Proteine, Pyrotechnik, Komplexe, Kosmetik, Analysemethoden)
├── spf4.html           ← SPF 4. Klasse (Energie, Elektrochemie, Katalyse)
│
└── [Unterordner pro Kapitel, z.B.:]
    └── juglon/
        └── ppm-berechnungen.html    ← hier Ihre bestehende Lerneinheit ablegen
```

## Wie ich neue Inhalte hinzufüge

### 1. Unterthema freischalten

Jedes Unterthema verweist auf eine HTML-Datei in einem Unterordner. Zum Beispiel
zeigt in `spf1.html` der Link für *ppm-Berechnungen* auf `juglon/ppm-berechnungen.html`.

**Sobald diese Datei existiert:**
- Das Unterthema wird automatisch klickbar (Schloss-Symbol verschwindet)
- Das übergeordnete Kapitel erhält automatisch den grünen Tag *Verfügbar*
- Das Kapitel erhält den Hover-Effekt

**Vorgehen für Juglon / ppm-Berechnungen:**
1. Im selben Ordner wie `spf1.html` einen Ordner `juglon/` erstellen
2. Ihre bestehende Lerneinheit als `ppm-berechnungen.html` dort hineinlegen
3. Fertig – beim nächsten Laden ist der Link aktiv.

### 2. Neue Unterthemen hinzufügen

In der entsprechenden `spf*.html`-Datei das gewünschte Kapitel suchen und
einen neuen `<a>`-Link in das `<div class="subtopics">` einfügen:

```html
<a href="juglon/mein-neues-thema.html" class="subtopic">
  <span class="subtopic-dot"></span>
  <span class="subtopic-name">Mein neues Thema</span>
  <span class="subtopic-lock">🔒</span>
  <span class="subtopic-arrow">→</span>
</a>
```

## Schullogo

Auf der Startseite links oben auf den gestrichelten Kasten mit der Beschriftung
*"Logo hochladen"* klicken und das Logo auswählen. Es wird im Browser gespeichert
(`localStorage`) und erscheint danach automatisch auch auf den Unterseiten.

> **Hinweis:** Das Logo wird pro Browser und Gerät gespeichert. Wenn Sie die
> Website später auf einem Webserver dauerhaft mit Logo zeigen möchten,
> können Sie das Logo-Bild direkt in den HTML-Dateien fest einbinden (statt
> des Platzhalters) – ich kann das gerne für Sie anpassen, sobald Sie mir
> das Logo geben.

## Lokales Testen

Damit das Auto-Freischalten (das Prüfen, welche Dateien existieren)
funktioniert, muss die Website über einen lokalen Webserver geöffnet werden,
nicht per Doppelklick auf die HTML-Datei.

Schnellstart in einem Terminal im Projekt-Ordner:

```
python3 -m http.server 8000
```

Dann im Browser öffnen: http://localhost:8000

## Hosting

Die Website funktioniert auf jedem statischen Webspace (Schul-Server, GitHub
Pages, Netlify, etc.). Einfach alle Dateien und Ordner hochladen.
