---
title: Richtlinie Passwort und Gerätesperre für Mobilgeräte (Entwurf)
layer: richtlinien
source: entwurf
verbindlich: false
hinweis: Entwurf, nicht freigegeben. Die Zahlenwerte sind Vorschläge und müssen noch festgelegt werden.
owner: franz
last_review: 2026-10-18
audience: [admins, it-sicherheit]
---
# Richtlinie Passwort und Gerätesperre für Mobilgeräte

Diese Richtlinie legt fest, **was** für dienstlich genutzte Mobilgeräte gilt.
Sie ist werkzeugneutral und gilt für alle Systeme. **Wie** die Vorgaben
eingestellt werden, steht auf den Umsetzungsseiten:

- BlackBerry UEM: [[umsetzung/uem/it-richtlinie-passwort]]
- Microsoft Intune: [[umsetzung/intune/passwort-geraetesperre]]

Status: **Entwurf.** Werte mit dem Vermerk "Vorschlag" sind noch nicht
entschieden.

## Geltungsbereich

Gilt für alle Smartphones und Tablets (Android, iOS/iPadOS), auf denen
dienstliche Daten verarbeitet werden, sowohl Firmengeräte als auch private
Geräte (BYOD). Bei BYOD gelten die Vorgaben für den dienstlichen Bereich
(Arbeitsprofil bzw. geschützte Firmen-Apps), nicht für den privaten Bereich.

## Vorgaben

| Vorgabe | Wert | Status |
|---|---|---|
| Gerätesperre mit Code | Pflicht | durch Quellen gestützt |
| Mindestlänge Geräte-Code | 6 Zeichen | Vorschlag |
| Einfache Codes (z. B. 1111, 1234) | nicht erlaubt | Vorschlag |
| Automatische Sperre bei Inaktivität | spätestens nach 5 Minuten | Vorschlag |
| Fehlversuche bis zum Löschen der Firmendaten | 10 | Vorschlag |
| Regelmäßiger Zwangswechsel des Codes | **kein** periodischer Wechsel | durch Quellen gestützt |
| Wechsel bei Verdacht auf Kompromittierung | Pflicht | durch Quellen gestützt |
| Entsperren per Fingerabdruck oder Gesichtserkennung | erlaubt, Code bleibt Pflicht | Vorschlag |
| Geräteverschlüsselung | Pflicht | durch Quellen gestützt |

Bei Fehlversuchen werden auf privaten Geräten (BYOD) nur die Firmendaten
gelöscht (selektives Löschen), niemals das ganze Gerät.

## Begründung

- **Kein Zwangswechsel:** Österreichische Empfehlungen (A-SIT,
  onlinesicherheit.gv.at) raten vom periodischen Passwortwechsel ab und
  verlangen einen Wechsel nur bei Verdacht auf Kompromittierung. Das deckt
  sich mit NIST SP 800-63B.
- **Verschlüsselung und Bildschirmsperre** werden von A-SIT und im
  BSI-Grundschutz empfohlen.
- **Sperrzeit:** Eine konkrete Minutenzahl ist in den österreichischen
  Quellen nicht eindeutig belegt. Der Wert von 5 Minuten ist ein Vorschlag.
- **Selektives Löschen bei BYOD:** Der private Bereich darf nicht überwacht
  oder gelöscht werden.

Details und Fundstellen: [[betrieb/quellenregister-behoerden]]
(KI-Recherche, vor Verwendung gegen die Originalquellen prüfen).

## Offene Entscheidungen

- Die Zahlenwerte mit Status "Vorschlag" festlegen.
- Klären, ob für Geräte mit besonders schützenswerten Daten strengere Werte
  gelten sollen.
- Abstimmung mit dem Betriebsrat (Betriebsvereinbarung nach ArbVG), bevor
  die Richtlinie verbindlich wird.
