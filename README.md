# Lexikon — Vokabeltrainer (PWA)

Persönliches Vokabelinventar Englisch–Deutsch: Übersetzung, Wortart, mehrere Bedeutungen,
Beispielsätze und Kontext pro Vokabel – plus Excel-Vorlage und Bulk-Import.
Läuft als installierbare Web-App (PWA) auf dem Smartphone.

## Inhalt des Ordners
```
index.html                 → die App
manifest.webmanifest       → App-Manifest (Name, Icon, Farben)
sw.js                      → Service Worker (Offline-Betrieb)
icon-192.png / icon-512.png / icon-maskable-512.png / apple-touch-icon.png / favicon.png
```
**Alle Dateien müssen im selben Ordner / unter derselben URL liegen.** Die Pfade sind
relativ – die App funktioniert daher auch in einem Unterordner (z. B. GitHub Pages).

---

## Schritt 1 — Online stellen (eine Option wählen)

### Option A · Netlify Drop (am schnellsten, ~2 Min, vom Rechner)
1. Auf **app.netlify.com/drop** gehen.
2. Den **gesamten Ordner** (alle Dateien) ins Fenster ziehen.
3. Du bekämst sofort eine URL wie `https://zufallsname.netlify.app`.
   (Kostenloser Account macht die URL dauerhaft + erlaubt Updates.)

### Option B · GitHub Pages (dauerhafte, stabile URL)
1. Neues Repository anlegen (z. B. `lexikon`).
2. Alle Dateien hochladen (Add file → Upload files → committen).
3. **Settings → Pages →** Branch `main`, Ordner `/ (root)` → Save.
4. Nach ~1 Min ist die App unter `https://DEINNAME.github.io/lexikon/` erreichbar.

### Option C · Cloudflare Pages
Ähnlich wie Netlify: Projekt erstellen, Ordner hochladen, fertig.

> Wichtig: Es muss **https** sein (alle drei Optionen liefern das automatisch).
> Ein Service Worker und „echte" PWA-Persistenz funktionieren nur über https.

---

## Schritt 2 — Auf dem Smartphone installieren

**iPhone (Safari):**
URL öffnen → unten auf **Teilen** (Quadrat mit Pfeil) → **„Zum Home-Bildschirm"** → Hinzufügen.

**Android (Chrome):**
URL öffnen → es erscheint „App installieren" (oder Menü ⋮ → **App installieren / Zum Startbildschirm**).

Danach hast du ein App-Icon, Vollbild und dauerhaften Speicher.

---

## Bedienung in Kürze
- **Vokabel + Übersetzen + Speichern:** Wort eintippen, „Übersetzen" (Vorschlag, editierbar), „Speichern".
- **Details auf Abruf:** Eintrag antippen → „Wörterbuch-Details laden" holt Wortart, Bedeutungen,
  Beispielsätze und Synonyme (englisches Wörterbuch).
- **Excel-Vorlage:** „Vorlage" lädt eine `.xlsx` mit den Spalten
  *English · Deutsch · Wortart · Bedeutungen · Beispielsätze · Kontext*.
  Mehrere Bedeutungen/Beispiele in einer Zelle mit **Semikolon `;`** trennen.
- **Import:** „Import" → ausgefüllte Datei wählen → Vorschau → Importieren.
  Spalten werden über die Überschriften erkannt; Duplikate (gleiches englisches Wort) werden übersprungen.
- **Export / Leeren:** „Export" sichert das ganze Inventar als Excel (gleiches Format wie die Vorlage → reimportierbar).

## Daten & Speicher
Die Vokabeln liegen lokal im Browser/der App auf deinem Gerät (kein Server, kein Konto).
Als installierte https-PWA ist das deutlich beständiger als eine lose HTML-Datei.
Für ein Backup oder Gerätewechsel einfach **exportieren**.

## Grenzen
- Übersetzung über MyMemory (Gratis-Limit ~5.000 Wörter/Tag, mit hinterlegter E-Mail ~50.000).
- Wörterbuch-Details stammen aus einem **englischen** Wörterbuch (Definitionen/Beispiele auf Englisch –
  fürs Englischlernen meist sogar ein Vorteil). Nicht jede seltene Form oder Wortgruppe ist enthalten.
- Offline funktioniert das Anschauen des Inventars; Übersetzen, Details und Excel brauchen Internet.
