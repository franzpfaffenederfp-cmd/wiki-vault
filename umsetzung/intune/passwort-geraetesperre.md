---
title: Passwort und Gerätesperre in Microsoft Intune (Beispielseite)
layer: umsetzung
scope: [intune]
source: beispiel
verbindlich: false
hinweis: Beispielseite für den Test des Scope-Filters. Inhalt nicht fachlich geprüft, Menüpfade gegen das eigene Intune Admin Center prüfen.
owner: franz
last_review: 2026-10-18
audience: [admins]
---
# Passwort und Gerätesperre in Microsoft Intune

Diese Seite beschreibt, wo Passwort- und Sperrvorgaben in **Microsoft Intune**
umgesetzt werden. Für BlackBerry UEM gilt sie nicht.

## Wo die Vorgaben eingestellt werden

In Intune gibt es dafür zwei Arten von Richtlinien, die oft zusammen
eingesetzt werden:

- **Konfigurationsprofil** (Gerätebeschränkungen): setzt die Passwortvorgabe
  auf dem Gerät durch.
- **Konformitätsrichtlinie** (Compliance): prüft, ob das Gerät die Vorgabe
  erfüllt. Ein nicht konformes Gerät kann über bedingten Zugriff von
  Firmendaten ausgeschlossen werden.

Beide werden Gruppen in Microsoft Entra ID zugewiesen. Pro Plattform
(Android, iOS/iPadOS) gibt es eigene Richtlinien.

## Abhängigkeit von der Registrierungsart

Welche Einstellungen greifen, hängt davon ab, wie das Gerät registriert ist,
zum Beispiel vollständig verwaltetes Firmengerät oder privates Gerät mit
Arbeitsprofil. Bei Geräten ohne Registrierung können
**App-Schutzrichtlinien** stattdessen eine PIN für die Firmen-Apps verlangen.

## Prüfen

1. Im Intune Admin Center beim Gerät nachsehen, welche Richtlinien zugewiesen
   sind und ob sie erfolgreich angewendet wurden.
2. Den Konformitätsstatus des Testgeräts prüfen, nachdem die Richtlinie
   synchronisiert wurde.
