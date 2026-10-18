---
title: Home – MDM-Wiki
layer: betrieb
source: intern
verbindlich: false
hinweis: Startseite und Autorenhilfe, keine fachlichen Vorgaben.
owner: franz
last_review: 2026-10-18
audience: [autoren]
---
# MDM-Wiki

Wiki für den MDM-Betrieb mit **BlackBerry UEM** und **Microsoft Intune** sowie
für österreichische Vorgaben zu IT-Sicherheit und Datenschutz. Das Wiki ist
über die Wiki-RAG-Suche abfragbar und soll später Grundlage für Schulungen
sein.

## Aufbau nach Ebenen

Jede Seite gehört zu genau einer Ebene (Feld `layer` im Frontmatter). Jede
Aussage steht an genau einer Stelle, andere Seiten verlinken darauf.

| Ebene | Inhalt | Ordner |
|---|---|---|
| `richtlinien` | Was gilt, werkzeugneutral (z. B. Passwortlänge, Sperrzeit) | `richtlinien/` |
| `plattform` | Besonderheiten von Android und Apple | `plattform/` |
| `umsetzung` | Wie es im jeweiligen System eingestellt wird | `umsetzung/uem/`, `umsetzung/intune/` |
| `extern` | Gespiegelte Behördenquellen, nicht bearbeiten | `extern/` |
| `betrieb` | Recherchen, Arbeitsdokumente, diese Startseite. In normalen Suchen ausgeblendet | `betrieb/` |

## Seiten

### Umsetzung
- [[umsetzung/uem/it-richtlinie-passwort|Passwort und Gerätesperre in BlackBerry UEM]] (Beispielseite)
- [[umsetzung/intune/passwort-geraetesperre|Passwort und Gerätesperre in Microsoft Intune]] (Beispielseite)

### Betrieb
- [[betrieb/quellenregister-behoerden|Quellenregister österreichische Behördenvorgaben]] (KI-Recherche, nicht verbindlich)

### Noch leer
- Richtlinien
- Plattform
- Extern

## Neue Seite anlegen

Die erste Zeile muss genau `---` sein. Vorlage:

```yaml
---
title: Seitentitel
layer: umsetzung
scope: [uem]
source: intern
verbindlich: true
hinweis:
owner: franz
last_review: 2026-10-18
audience: [admins]
---
```

- `scope`: `[uem]`, `[intune]` oder `[uem, intune]`. Fehlt das Feld, gilt die
  Seite für alle Systeme.
- `verbindlich: false` für alles, was nicht freigegeben ist (Recherchen,
  Entwürfe, Beispiele). `hinweis` erklärt dann, warum.
- `last_review` beim Überarbeiten aktualisieren. Seiten älter als 6 Monate
  gelten als zu prüfen.
- Auf GitHub: "Add file" in der obersten Ebene des Repos klicken, sonst
  landet die Datei im gerade geöffneten Ordner.

Nach dem Speichern auf GitHub muss die Seite auf dem Server neu indexiert
werden, erst dann ist sie in der Suche.
