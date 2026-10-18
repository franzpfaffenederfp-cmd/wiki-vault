---
title: Passwort und Gerätesperre in BlackBerry UEM (Beispielseite)
layer: umsetzung
scope: [uem]
source: beispiel
verbindlich: false
hinweis: Beispielseite für den Test des Scope-Filters. Inhalt nicht fachlich geprüft, Menüpfade gegen die eigene UEM-Konsole prüfen.
owner: franz
last_review: 2026-10-18
audience: [admins]
---
# Passwort und Gerätesperre in BlackBerry UEM

Diese Seite beschreibt, wo Passwort- und Sperrvorgaben in **BlackBerry UEM**
umgesetzt werden. Für Microsoft Intune gilt sie nicht.

## Wo die Vorgaben eingestellt werden

In BlackBerry UEM werden Passwort- und Sperrvorgaben über eine
**IT-Richtlinie** (IT policy) festgelegt. Die IT-Richtlinie wird Benutzern
oder Benutzergruppen zugewiesen und gilt dann für deren aktivierte Geräte.

- Pro Plattform (Android, iOS/iPadOS) gibt es eigene Einstellungen in der
  IT-Richtlinie.
- Hat ein Benutzer mehrere Richtlinien über verschiedene Gruppen, entscheidet
  die Rangfolge der Richtlinien, welche gilt.

## Abhängigkeit vom Aktivierungstyp

Welche Einstellungen auf dem Gerät greifen, hängt vom **Aktivierungstyp** ab,
zum Beispiel ob das ganze Gerät verwaltet wird oder nur ein Arbeitsbereich.
Bei BYOD mit getrenntem Arbeitsbereich betreffen Passwortvorgaben in der Regel
den Arbeitsbereich, nicht das private Gerät.

## Prüfen

1. In der UEM-Konsole beim Benutzer nachsehen, welche IT-Richtlinie
   tatsächlich zugewiesen ist.
2. Auf einem Testgerät prüfen, ob die Passwortvorgabe nach dem Aktualisieren
   der Richtlinie erzwungen wird.
