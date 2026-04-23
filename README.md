# Chemie-Website für das Schwerpunktfach · Anleitung

## Dateien hochladen bei GitHub

### Einmaliges Setup (beim ersten Mal)

Sie laden alle Dateien, die ich Ihnen gegeben habe, ins Hauptverzeichnis Ihres
GitHub-Repositorys:

```
index.html
spf1.html
spf2.html
spf3.html
spf4.html
GKG_Chemie_LOGO.png
```

**Wichtig:** Das Logo (`GKG_Chemie_LOGO.png`) muss **exakt diesen Dateinamen**
haben und **direkt neben** den HTML-Dateien liegen (nicht in einem Unterordner).

Nach dem Hochladen und wenn GitHub Pages aktiviert ist, sehen Sie die Startseite
unter Ihrer GitHub-Pages-URL. Die Kapitel erscheinen zunächst alle als
"Kommt bald" — das ist korrekt, weil die Inhalte noch fehlen.

---

## Inhalte hinzufügen — am Beispiel Juglon / ppm-Berechnungen

Nehmen wir an, Sie haben eine Lerneinheit zum Thema **ppm-Berechnungen** als
HTML-Datei fertig. Die soll unter *SPF 1. Klasse → Juglon → ppm-Berechnungen*
erscheinen.

### Schritt für Schritt bei GitHub (im Browser)

1. Öffnen Sie Ihr Repository auf github.com
2. Klicken Sie auf den Button **"Add file"** → **"Upload files"**
3. Ziehen Sie Ihre Lerneinheit-Datei ins Upload-Feld
4. **Bevor Sie auf "Commit" klicken**, benennen Sie die Datei so um, dass sie
   im richtigen Ordner landet: Oben im Pfad tippen Sie z.B.
   `juglon/ppm-berechnungen.html` — GitHub erstellt den Ordner automatisch.
5. Unten auf "Commit changes" klicken — fertig.

Beim nächsten Besuch Ihrer Website wird die Kachel *ppm-Berechnungen* automatisch
klickbar und das Kapitel *Juglon* erhält den grünen "Verfügbar"-Tag.

### Welche Datei gehört wohin? (Übersicht SPF 1)

Die HTML-Dateien `spf1.html` bis `spf4.html` verlinken bereits auf festgelegte
Pfade. Sie müssen also nur Dateien mit den **richtigen Namen** in die
**richtigen Ordner** legen. Hier die Liste für die 1. Klasse:

| Kapitel | Unterthema | Ordner/Datei |
|---|---|---|
| Alles Dufte | Einführung Duftstoffe | `alles-dufte/einfuehrung.html` |
| Alles Dufte | Funktionelle Gruppen | `alles-dufte/funktionelle-gruppen.html` |
| Alles Dufte | Ester & Estersynthese | `alles-dufte/ester.html` |
| Alles Dufte | Analyse mit GC-MS | `alles-dufte/gc-ms.html` |
| Kernreaktionen | Radioaktivität | `kernreaktionen/radioaktivitaet.html` |
| Kernreaktionen | Zerfallsarten | `kernreaktionen/zerfallsarten.html` |
| Kernreaktionen | Halbwertszeit | `kernreaktionen/halbwertszeit.html` |
| Kernreaktionen | Kernspaltung & Fusion | `kernreaktionen/kernspaltung-fusion.html` |
| **Juglon** | Einführung Juglon | `juglon/einfuehrung.html` |
| **Juglon** | **ppm-Berechnungen** | **`juglon/ppm-berechnungen.html`** |
| Juglon | Chinone & Redoxchemie | `juglon/chinone.html` |
| Juglon | Extraktion & Nachweis | `juglon/extraktion.html` |
| Lumineszenz | Grundlagen | `lumineszenz/grundlagen.html` |
| Lumineszenz | Fluoreszenz & Phosphoreszenz | `lumineszenz/fluoreszenz-phosphoreszenz.html` |
| Lumineszenz | Chemolumineszenz | `lumineszenz/chemolumineszenz.html` |
| Lumineszenz | Anwendungen | `lumineszenz/anwendungen.html` |
| Energieumwandlungen | Exotherm & Endotherm | `energieumwandlungen/exotherm-endotherm.html` |
| Energieumwandlungen | Reaktionsenthalpie | `energieumwandlungen/enthalpie.html` |
| Energieumwandlungen | Satz von Hess | `energieumwandlungen/hess.html` |
| Energieumwandlungen | Kalorimetrie | `energieumwandlungen/kalorimetrie.html` |

Die Pfade für SPF 2, 3 und 4 stehen jeweils im Quelltext der `spf*.html`-Dateien
(suchen Sie nach `href="..."` in den `<a class="subtopic">`-Zeilen).

---

## Häufige Stolpersteine

### "Mein Kapitel ist nach dem Hochladen immer noch gesperrt"

- **Dateiname prüfen:** `ppm-berechnungen.html` ist etwas anderes als
  `ppm_berechnungen.html` (Bindestrich statt Unterstrich) oder
  `PPM-Berechnungen.html` (Groß-/Kleinschreibung).
  Die Namen müssen **exakt** wie in der Tabelle oben sein.
- **Browser-Cache leeren:** Drücken Sie `Ctrl+F5` (oder `Cmd+Shift+R` am Mac).
- **GitHub Pages braucht 1–2 Minuten**, bis neue Dateien live sind.

### "Das Logo wird nicht angezeigt"

Stellen Sie sicher, dass die Datei `GKG_Chemie_LOGO.png` im selben Ordner wie
`index.html` liegt und der Dateiname **exakt** so geschrieben ist (mit
Großbuchstaben GKG und LOGO).

### "Wie mache ich selbst neue Unterthemen dazu, die noch nicht in der Liste sind?"

In der passenden `spf*.html` öffnen, das gewünschte Kapitel suchen und im
`<div class="subtopics">` einen neuen Link einfügen:

```html
<a href="juglon/mein-neues-thema.html" class="subtopic">
  <span class="subtopic-dot"></span>
  <span class="subtopic-name">Mein neues Thema</span>
  <span class="subtopic-lock">🔒</span>
  <span class="subtopic-arrow">→</span>
</a>
```

Dann die entsprechende HTML-Datei an den angegebenen Pfad hochladen.

---

## Lokales Testen (optional)

Wenn Sie vor dem Hochladen testen möchten, ob alles funktioniert:

- Am einfachsten: Alles hochladen auf einen Test-Branch bei GitHub, dort prüfen.
- Lokal über einen kleinen Webserver — im Projektordner ein Terminal öffnen und
  `python3 -m http.server 8000` eingeben, dann im Browser `http://localhost:8000`
  öffnen. (Doppelklick auf `index.html` reicht **nicht**, weil das automatische
  Freischalten dann nicht funktioniert.)
