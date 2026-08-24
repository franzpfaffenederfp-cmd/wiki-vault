---
title: Quellenregister österreichische Behördenvorgaben
layer: betrieb
source: recherche
verbindlich: false
hinweis: KI-Recherche, nicht rechtsverbindlich. Vor Verwendung gegen Originalquelle prüfen.
scope: [uem, intune]
owner: franz
last_review: 2026-08-24
---
# Österreichische Behörden- und Offizialquellen zu IT-Sicherheit & Datenschutz für ein MDM-Firmenwiki (Stand 2026)

## TL;DR
- Die praktisch wichtigsten, automatisiert spiegelbaren Quellen sind: das **RIS** (Rechtsinformationssystem, mit echter REST/SOAP-**OGD-API v2.6**, tagesaktuell, maschinenlesbar, Rechtstexte urheberrechtlich frei nach § 7 UrhG), das **Österreichische Informationssicherheitshandbuch** (A-SIT/BKA, Version 4.4.0 vom 06.11.2023, XML/HTML/PDF), **onlinesicherheit.gv.at** und **sicherheitshandbuch.gv.at** (A-SIT), die **Datenschutzbehörde (dsb.gv.at)** mit Leitfäden/Newslettern sowie **CERT.at/GovCERT** (RSS/Atom-Feeds).
- Rechtlich sauber automatisiert spiegeln lassen sich vor allem **Gesetzestexte** (DSG, TKG, NISG, UrhG) über die RIS-API – diese sind gemeinfrei; bei **Handbüchern, Leitfäden und Broschüren** (A-SIT, WKO, DSB, BSI) ist die Lizenz meist *nicht* offen deklariert, weshalb für ein **rein internes** Wiki das Zitatrecht bzw. eine restriktive Nutzung anzuwenden ist und keine öffentliche Weiterverbreitung erfolgen darf.
- Inhaltlich gilt 2026 der Konsens: **Passwortlänge > erzwungener Wechsel** (Abkehr vom periodischen Zwangswechsel, Wechsel nur bei Kompromittierung), **Vollverschlüsselung** der Geräte, **Bildschirmsperre**, **Fernlöschung** (bei BYOD nur des Firmencontainers) und – österreichspezifisch – zwingende **Betriebsvereinbarung** nach § 96/§ 96a ArbVG, weil MDM ein die Menschenwürde berührendes Kontrollsystem sein kann.

## Key Findings

1. **RIS ist das Herzstück für Rechtstexte** und bietet als einzige Quelle eine vollwertige, dokumentierte API (OGD-RIS v2.6, REST + SOAP, Antwortformat XML/JSON), inklusive History-Abfrage zur Änderungserkennung – ideal für automatisierte Versionierung. Gesetze/Verordnungen sind nach § 7 UrhG gemeinfrei.
2. **Das Österreichische Informationssicherheitshandbuch** (A-SIT/BKA) ist die maßgebliche nationale ISMS-Referenz (ISO/IEC-27001-orientiert, >700 Seiten), aktuell Version 4.4.0 (06.11.2023); es enthält konkrete Kapitel zu Passwortgebrauch (9.3.1), Bildschirmsperre (9.3.2) und Verschlüsselung. Es liegt als XML-Datenbasis, HTML-Online-Viewer und PDF vor – aber die Lizenz ist nicht öffentlich deklariert und die Domain blockiert automatisiertes Crawlen (robots.txt).
3. **Für MDM-spezifische Detailtiefe** ist das deutsche **BSI IT-Grundschutz-Kompendium** (Bausteine SYS.3.2.1, SYS.3.2.2, betriebssystemspezifische Bausteine) und der **BSI-Mindeststandard MDM** faktischer Maßstab; in Österreich nicht rechtsverbindlich, aber als „Stand der Technik" (Art. 32 DSGVO) breit anerkannt. Ebenso **BSI TR-02102-1** (Krypto, Version 2026-01, Stand 23. Januar 2026) als Verschlüsselungsmaßstab.
4. **Datenschutz-rechtlich** ist in Österreich neben DSGVO das **DSG** einschlägig; für MDM zentral der **Arbeitnehmerdatenschutz** und die **Betriebsvereinbarungspflicht** (§ 96 Abs. 1 Z 3 bzw. § 96a ArbVG). Praxisleitfäden liefern DSB, WKO und EDSA.
5. **NIS2** ist in Österreich erst spät umgesetzt: Das **NISG 2026** wurde am 12. Dezember 2025 im Nationalrat beschlossen, am 23. Dezember 2025 als **BGBl I 94/2025** kundgemacht und tritt gemäß § 51 NISG 2026 am **1. Oktober 2026** in Kraft. Betroffen sind wesentliche und wichtige Einrichtungen ab 50 Beschäftigten bzw. 10 Mio. € Umsatz in 18 Sektoren (§ 24/§ 25 NISG 2026), rund 5.000 direkt betroffene Organisationen; Strafen bis 10 Mio. € bzw. 2 % des weltweiten Jahresumsatzes (§ 45).

## Details – Quellen im Einzelnen

### 1. RIS – Rechtsinformationssystem des Bundes (Bundeskanzleramt)
- **Rolle:** Amtliche, rechtsverbindliche Kundmachung und konsolidierte Fassungen von Bundes-/Landesrecht sowie Judikatur.
- **Relevante Dokumente:** DSG (Datenschutzgesetz, Gesetzesnummer 10001597), TKG 2021, NISG/NISG 2026, UrhG, ArbVG (§§ 96, 96a).
- **URLs:**
  - Portal: `https://www.ris.bka.gv.at/`
  - DSG konsolidiert (Geltende Fassung): `https://www.ris.bka.gv.at/GeltendeFassung.wxe?Abfrage=bundesnormen&Gesetzesnummer=10001597`
  - OGD-API-Basis: `https://data.bka.gv.at/ris/api/v2.6/` bzw. Service `https://data.bka.gv.at/ris/ogd/v2.6`
  - API-Handbuch (PDF, Mai 2024): `https://data.bka.gv.at/ris/ogd/v2.6/Documents/Dokumentation_OGD-RIS_API.pdf`
  - OGD-FAQ (PDF): `https://ris.bka.gv.at/RisInfo/OGD-FAQ.pdf`
- **Format/Schnittstelle:** HTML (Web), **REST- und SOAP-API**, Antwort im XML/JSON. Der API-Endpunkt akzeptiert GET/POST. Es gibt eine **„History-Abfrage"**, mit der man gezielt feststellt, ob ein Dokument neu eingebracht, geändert oder gelöscht wurde – man muss also nicht den ganzen Datenbestand neu laden. Das ist genau der Änderungs-Feed, den man für inkrementelle Synchronisierung braucht.
- **Aktualisierung:** tagesaktuell.
- **Versionierung:** Jede konsolidierte Norm hat eine „Fassung vom [Datum]" und Bezug zu BGBl-Nummern; Änderungen sind über die History-Abfrage/Fassungsdaten erkennbar.
- **Lizenz:** Rechtstexte (Gesetze, Verordnungen, Erlässe, Entscheidungen) sind nach **§ 7 UrhG gemeinfrei** (freie Werke). Die API-Inhalte selbst wurden in einer Untersuchung als unter „CC BY-NC 4.0" stehend beschrieben, soweit nicht ohnehin von § 7 UrhG umfasst – für Gesetzestexte gilt also die Gemeinfreiheit. **Registrierung nicht erforderlich.**
- **Empfehlung:** Erste Wahl für automatisiertes Spiegeln. Zugriff über die OGD-API, Speicherung der Fassungsdaten als Version, Markdown-Konvertierung des XML.

### 2. Österreichisches Informationssicherheitshandbuch (A-SIT / Bundeskanzleramt)
- **Herausgeber:** A-SIT (Zentrum für sichere Informationstechnologie – Austria) gemeinsam mit dem Bundeskanzleramt.
- **Aktuelle Version:** **4.4.0, datiert 06.11.2023** (im PDF ausgewiesen). Hinweis: Die Katalogseite auf onlinesicherheit.gv.at nennt abweichend noch eine ältere Version (4.3.x) – die Angaben sind nicht synchron. Eine 2026er-Neuversion ist **nicht belegbar**; laut Herausgeber erfolgt die inhaltliche Wartung der Online-Version fortlaufend.
- **Struktur:** orientiert an ISO/IEC 27001; >700 Seiten; behandelt ISMS-Aufbau, Risiken und Maßnahmen. Relevante Kapitel: **9.3.1 Regelungen des Passwortgebrauches** (S. 294), **9.3.2 Bildschirmsperre** (S. 297), Kryptographie-Kapitel, Fernzugriff/VPN.
- **URLs:**
  - Online-Viewer: `https://www.sicherheitshandbuch.gv.at/`
  - Gesamt-PDF: `https://www.sicherheitshandbuch.gv.at/downloads/sicherheitshandbuch.pdf`
  - Passwort-Checkliste (PDF): `https://www.sicherheitshandbuch.gv.at/downloads/Passwort-Checkliste.pdf`
  - XML-Content-Ansicht: `https://www.sicherheitshandbuch.gv.at/data/sihacontent.html`
  - A-SIT-Info: `https://www.a-sit.at/en/collaborations/information-security-handbook/`
- **Format/Schnittstelle:** **XML-Datenbasis** (Transformation nach HTML/RTF/PDF), HTML-Online-Viewer (JavaScript), PDF-Download. Keine dokumentierte Abfrage-API/RSS-Feed.
- **Aktualisierung:** kontinuierlich (Online), PDF versioniert.
- **Versionierung:** feste Versionsnummer + Datum in der PDF-Kopfzeile (aktuell 4.4.0 / 06.11.2023).
- **Wichtiger technischer Hinweis für die Automatisierung:** **sicherheitshandbuch.gv.at blockiert automatisierten Zugriff (robots.txt)** – ein direkter Scripting-Abruf von PDF/HTML/help.html schlägt fehl. Für die Spiegelung ist ein manueller Download oder eine explizite Genehmigung durch A-SIT (siha@a-sit.at) nötig.
- **Lizenz:** **Nicht öffentlich deklariert** (weder CC noch „alle Rechte vorbehalten" belegbar). Verantwortlich: A-SIT/BKA. Für interne Nutzung ist Rücksprache mit A-SIT empfehlenswert.

### 3. onlinesicherheit.gv.at (IKT-Sicherheitsportal, A-SIT + Ministerien)
- **Rolle:** Zentrales interministerielles Awareness-Portal (seit Feb. 2013); Zielgruppe Laien und Experten. Redaktion: Content Agentur Austria; inhaltlich verantwortlich meist A-SIT.
- **Relevante Inhalte:** Passwort-Umgang, Kennwortsicherheit, mobile IT-Sicherheit, Smartphone-Sicherheitsfunktionen, Handbuch-Übersichten, Checklisten.
- **URLs (Beispiele):**
  - Portal: `https://www.onlinesicherheit.gv.at/`
  - Kennwortsicherheit (letzte Aktualisierung 23. Jänner 2026): `https://www.onlinesicherheit.gv.at/Services/News/Kennwortsicherheit--Der-richtige-Umgang-mit-Passwoertern.html`
  - Mobile Arbeitsgeräte: `https://www.onlinesicherheit.gv.at/Services/News/IT-Sicherheit-fuer-mobile-Arbeitsgeraete.html`
  - Smartphone-Plattform-Sicherheit: `https://onlinesicherheit.gv.at/service/technologie-trends/smartphone-sicherheit/134455.html`
- **Format:** HTML (Artikel mit „Letzte Aktualisierung"-Datum), PDF-Checklisten. Ein offizieller RSS/Atom-Feed ist nicht eindeutig dokumentiert.
- **Aktualisierung:** monatliche Themenstrecken, laufend neue News.
- **Versionierung:** jeder Artikel trägt „Letzte Aktualisierung: [Datum]" – gut als Change-Indikator scriptbar.
- **Lizenz:** nicht als offene Lizenz deklariert – für internes Wiki Zitat/Verweis, keine öffentliche Weiterverbreitung.

### 4. Datenschutzbehörde (DSB, dsb.gv.at)
- **Rolle:** nationale Aufsichtsbehörde nach DSGVO/DSG.
- **Publikationen:** DSGVO-Leitfaden (aktuellste bekannte Fassung 2022, PDF), Newsletter DSB (seit 2015, quartalsweise als PDF; 2026 bereits Newsletter 01/2026 erschienen), Tätigkeitsberichte, Musterformulare, DSFA-Ausnahmeliste (Verordnung DSFA-AV).
- **URLs:**
  - Portal: `https://dsb.gv.at/`
  - Newsletter-Übersicht: `https://dsb.gv.at/ueber-die-datenschutzbehoerde/newsletter`
  - DSGVO-Leitfaden (PDF 2022): `https://dsb.gv.at/sites/site0344/media/downloads/dsgvo_leitfaden_2022.pdf`
- **Format:** HTML + PDF. Kein RSS/API; Newsletter per E-Mail-Abo.
- **Aktualisierung:** Newsletter quartalsweise (2024 reduziert wegen Website-Relaunch); Entscheidungen laufend (auch über RIS-Judikaturdokumentation Datenschutzbehörde abrufbar).
- **Versionierung:** Newsletter durchnummeriert (z. B. 01/2026); Leitfäden mit Jahr.
- **Lizenz:** nicht offen deklariert; Entscheidungen im RIS sind als amtliche Werke frei.
- **Automatisierungstipp:** Entscheidungen der DSB besser über die **RIS-Judikatur-Applikation** (API) als über die DSB-Website spiegeln.

### 5. CERT.at / GovCERT Austria
- **Rolle:** nationales bzw. Regierungs-CERT; Warnungen, Tagesberichte, Jahresberichte.
- **URLs & Feeds (maschinenlesbar!):**
  - Feed-Übersicht: `https://www.cert.at/de/services/feeds/`
  - Warnungen RSS 2.0: `https://www.cert.at/cert-at.de.warnings.rss_2.0.xml` / Atom: `https://www.cert.at/cert-at.de.warnings.atom_1.0.xml`
  - Blog RSS: `https://www.cert.at/cert-at.de.blog.rss_2.0.xml`
  - Tagesberichte RSS: `https://www.cert.at/cert-at.de.daily.rss_2.0.xml`
  - Aktuelles RSS: `https://www.cert.at/cert-at.de.current.rss_2.0.xml`
  - GovCERT: `https://www.govcert.gv.at/`
- **Format:** HTML + **RSS/Atom** (ideal für automatisierte Synchronisation), PDF-Jahresberichte.
- **Aktualisierung:** laufend/täglich.
- **Versionierung:** über Feed-Zeitstempel.
- **Lizenz:** nicht offen deklariert; für internes Monitoring geeignet.
- **Empfehlung:** Sehr gut automatisierbar; erste Wahl für die „aktuelle Bedrohungslage"-Sektion des Wikis.

### 6. A-SIT (Zentrum für sichere Informationstechnologie – Austria)
- **Rolle:** technische Kompetenzstelle; betreibt Handbuch und (mit) onlinesicherheit.gv.at.
- **Publikationen:** Sicherheitsanalyse mobiler Plattformen (iOS/Android/etc.), Sicherheitsempfehlungen für Behörden (kryptografische Methoden), Security Guide.
- **URLs:** `https://www.a-sit.at/`; Studien meist über onlinesicherheit.gv.at verlinkt.
- **Format:** überwiegend PDF/HTML. Kein API/RSS.
- **Lizenz:** nicht offen deklariert.

### 7. WKO – Wirtschaftskammer Österreich
- **Rolle:** Praxisleitfäden für Unternehmen.
- **Publikationen:** **IT-Sicherheitshandbuch für KMU** (frei auf `www.it-safe.at`), IT-Sicherheitshandbuch für Geschäftsführer, DSGVO-Leitfäden.
- **URLs:** `https://www.wko.at/`, `https://www.it-safe.at/`
- **Format:** PDF/HTML. Kein API/RSS.
- **Aktualisierung:** unregelmäßig (Neuauflagen).
- **Lizenz:** nicht offen deklariert; WKO-Inhalte urheberrechtlich geschützt.

### 8. EU-Quellen mit Österreich-Bezug
- **EDSA/EDPB** (`https://www.edpb.europa.eu/documents_de`): Leitlinien (deutsch verfügbar), z. B. zu Verantwortlicher/Auftragsverarbeiter (07/2020), KMU-Datenschutzleitfaden. Für MDM/Arbeitgeberkontext einschlägig.
- **ENISA** (`https://www.enisa.europa.eu/`): BYOD-/Teleworking-Empfehlungen, „Consumerization of IT".
- **NIS2 in Österreich:** NISG 2026 (BGBl I 94/2025), in Kraft ab 1. Oktober 2026 (siehe RIS/Parlament).
- **Format:** HTML/PDF; EDSA-Dokumente teils mehrsprachig.
- **Lizenz:** EU-Dokumente meist unter CC BY 4.0 bzw. mit großzügiger Weiterverwendung (EU-Reuse-Politik) – hier ist automatisiertes Spiegeln rechtlich am unproblematischsten neben RIS.

### 9. Deutsche Referenzwerke (in Österreich faktischer Maßstab, nicht rechtsverbindlich)
- **BSI IT-Grundschutz-Kompendium** – Bausteine **SYS.3.2.1** (Allgemeine Smartphones und Tablets), **SYS.3.2.2** (Mobile Device Management), betriebssystemspezifische Bausteine. Konkrete MUSS/SOLL-Anforderungen zu Verschlüsselung, Grundkonfiguration, Nutzungsrichtlinie, Berechtigungskonzept.
- **BSI-Mindeststandard MDM** (Version 2.0).
- **BSI TR-02102-1** „Kryptographische Verfahren: Empfehlungen und Schlüssellängen", **Version 2026-01, Stand 23. Januar 2026** (jährliche Aktualisierung, meist Januar): AES-128 Mindestlänge, AES-256 für Langzeitschutz, RSA ≥ 3000 Bit, Post-Quanten-Empfehlungen.
- **URLs:**
  - Grundschutz SYS.3.2.2: `https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Grundschutz/...`
  - TR-02102-1: `https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Publikationen/TechnischeRichtlinien/TR02102/BSI-TR-02102.html`
- **Anwendbarkeit in Österreich:** Nicht rechtsverbindlich, aber als „Stand der Technik" nach Art. 32 DSGVO breit anerkannt und in österreichischen Prüfungen/Audits herangezogen. Urheberrechtlich sind BSI-Inhalte geschützt (deutsches Recht) – für interne Referenz nutzbar, keine öffentliche Weiterverbreitung.

## Details – Inhaltliche Vorgaben für MDM/Mobilgeräte

### Passwörter (Stand 2026)
- **Österreichisches Handbuch / A-SIT-Checkliste:** Mindestlänge angemessen zum Einsatzzweck, **mindestens neun Zeichen** für Online-Dienste, mehr für sensible Dienste; vier Zeichenarten (Groß-/Kleinbuchstaben, Ziffern, Sonderzeichen); keine Trivialpasswörter/persönliche Details; **Wechsel nur bei (Verdacht auf) Kompromittierung**, kein starrer Zeitwechsel; Passwort-Manager + Zwei-Faktor-Authentifizierung.
- **onlinesicherheit.gv.at (23.01.2026):** „Aktuelle Ansätze empfehlen längere Passphrasen … anstelle von komplexen Kennwörtern. Auch sind Kennwortänderungen bei Verdacht auf eine Kompromittierung erforderlich." → **klare Abkehr vom periodischen Zwangswechsel.**
- **NIST SP 800-63B Revision 4** (veröffentlicht August 2025, als internationaler Vergleichsmaßstab): Mindestlänge 8 Zeichen, für Single-Factor-Authentifizierung 15 Zeichen; Systeme müssen ≥ 64 Zeichen unterstützen; keine erzwungenen Komplexitätsregeln; kein Zwangswechsel (Section 5.1.1.2: „Verifiers SHOULD NOT require memorized secrets to be changed arbitrarily (e.g., periodically)."). Dies ist keine österreichische Vorgabe, deckt sich aber inhaltlich mit dem A-SIT-Kurs.
- **Praktische MDM-Umsetzung:** In BlackBerry UEM und Intune Passcode-Policies entsprechend konfigurieren: Mindestlänge, Komplexität, Sperre bei Inaktivität, kein erzwungener Ablauf (bzw. langer Ablauf), Sperre nach Fehlversuchen (mit Wipe-Schwelle).

### Geräteverschlüsselung, Bildschirmsperre, Fernlöschung
- **Verschlüsselung:** Vollverschlüsselung (Dateisystem-/Geräteverschlüsselung) wird von A-SIT ausdrücklich empfohlen; iOS und moderne Android-Geräte nutzen Hardware-gestützte Verschlüsselung. BSI SYS.3.2.1: nichtflüchtiger Speicher SOLLTE verschlüsselt werden, ebenso SD-Karten. Krypto-Maßstab: BSI TR-02102-1 (2026-01, Stand 23.01.2026), AES-256 für Langzeitschutz.
- **Bildschirmsperre:** Handbuch-Kapitel 9.3.2 behandelt Bildschirmsperre; eine konkrete Minutenangabe ist im österreichischen Handbuch **nicht eindeutig belegbar**. BSI-Grundschutz nennt als Orientierung typischerweise kurze Inaktivitäts-Timeouts.
- **Fernlöschung:** Kernfunktion jedes MDM; bei BYOD datenschutzkonform nur **selektiver Wipe** des Firmencontainers, nicht des privaten Bereichs.

### BYOD und Trennung dienstlich/privat
- **Container-Konzept:** BlackBerry UEM (BlackBerry Dynamics/Work Space) und Intune (App Protection Policies / Android Work Profile / iOS „User Enrollment") trennen dienstliche und private Daten. Innerhalb des Firmencontainers volle Kontrolle; privater Bereich bleibt „Black Box".
- **BSI:** SYS.3.2.2 klammert BYOD explizit aus; ergänzend BSI-Überblickspapier „Consumerisation und BYOD"; NIST SP 800-114 Rev.1 (Telework/BYOD).
- **Österreich-Spezifikum:** Ist Privatnutzung erlaubt, ist Überwachung des privaten Bereichs strikt untersagt.

### DSGVO/Arbeitnehmerdatenschutz-Anforderungen an MDM (Österreich)
- **Rechtsgrundlage:** Jede Form der Überwachung braucht in Österreich eine Rechtsgrundlage oder **Betriebsvereinbarung**. MDM-Systeme können „Kontrollmaßnahmen, welche die Menschenwürde berühren" sein → **zustimmungspflichtige Betriebsvereinbarung** nach **§ 96 Abs. 1 Z 3 ArbVG** (bei menschenwürdeberührenden Kontrollsystemen) bzw. **§ 96a ArbVG** (Personaldatensysteme). Ohne Betriebsrat: individuelle Zustimmung/vertragliche Regelung.
- **Datenminimierung:** Es dürfen nur die für das Arbeitsverhältnis erforderlichen Daten erhoben werden; der Kreis der Zugriffsberechtigten ist eng zu fassen.
- **Transparenz:** Mitarbeiter müssen vorab lückenlos über Art und Umfang der Kontrollmaßnahmen informiert werden (Art. 13 DSGVO).
- **DSFA:** MDM kann eine Datenschutz-Folgenabschätzung erfordern; die DSB-DSFA-Ausnahmeverordnung (DSFA-AV, BGBl II 2018/108) listet ausgenommene Standard-Verarbeitungen (z. B. Personalverwaltung DSFA-A02, Zutrittskontrolle DSFA-A08).
- **Praxisquellen:** DSB-Leitfaden, WKO-Leitfäden, EDSA-Leitlinien; einschlägige österreichische Fachliteratur zum Arbeitnehmer-Datenschutz.

### Protokollierung und Aufbewahrungsfristen
- **Grundsatz:** Protokolldaten (Logs) sind personenbezogene Daten und unterliegen Zweckbindung, Datenminimierung und Löschfristen.
- **DSG/DSGVO:** keine pauschale gesetzliche MDM-Log-Frist; die Aufbewahrung ist am Zweck (Sicherheit, Nachvollziehbarkeit) auszurichten und in der Betriebsvereinbarung/Verarbeitungsverzeichnis festzulegen. (Konkrete Fristen sind fallabhängig – im Wiki als „organisationsintern festzulegen" kennzeichnen.)

## Rechtliche Einordnung der Weiterverwendung (Zusammenfassung)
- **Frei/gemeinfrei (§ 7 UrhG):** Gesetze, Verordnungen, amtliche Erlässe, Bekanntmachungen und (Gerichts-/Behörden-)Entscheidungen. → DSG, TKG, NISG, UrhG, ArbVG, DSB-/Gerichtsentscheidungen im RIS sind ohne Lizenzbeschränkung spiegel- und bearbeitbar. Berücksichtigter Stand § 7 UrhG: 23.08.2026.
- **RIS-OGD-API:** öffentlich, keine Registrierung; Rechtstexte gemeinfrei.
- **Vorsicht bei Handbüchern/Leitfäden/Broschüren:** Das Informationssicherheitshandbuch (A-SIT/BKA), onlinesicherheit.gv.at-Artikel, DSB-Leitfäden, WKO-Handbücher und BSI-Werke sind **keine „amtlichen Werke" i.S.d. § 7 UrhG** und daher grundsätzlich **urheberrechtlich geschützt**; eine offene Lizenz (CC) ist bei diesen meist **nicht** deklariert.
- **EU-Dokumente (EDSA, ENISA):** überwiegend CC BY 4.0 / großzügige EU-Reuse-Politik – gut spiegelbar (Namensnennung).
- **Interne Nutzung im Firmenwiki:** Rein interne Speicherung, Konvertierung und Nutzung geschützter Leitfäden ist im Rahmen des betrieblichen Eigengebrauchs und des Zitatrechts weitgehend zulässig; **öffentliche Weiterverbreitung** (auch intern für einen unbestimmten Personenkreis) sowie das Erstellen abgeleiteter Schulungsunterlagen zur Weitergabe kann eine **Werknutzungsbewilligung** erfordern. Für A-SIT-Handbuch: Rücksprache mit A-SIT (siha@a-sit.at) empfohlen; für BSI: Nutzungsbedingungen des BSI beachten.
- **Technische Sperre:** sicherheitshandbuch.gv.at blockiert automatisiertes Crawlen (robots.txt) – automatisiertes Spiegeln ist ohne Genehmigung nicht nur rechtlich, sondern auch technisch problematisch.

## Recommendations (priorisierte Einbindung)

**Stufe 1 – sofort einbinden (hoher Nutzen, rechtlich sauber, gut automatisierbar):**
1. **RIS-OGD-API** für DSG, TKG 2021, NISG 2026, UrhG, ArbVG §§ 96/96a – über REST-API, XML→Markdown, History-Abfrage für Versionierung. Gemeinfrei.
2. **CERT.at/GovCERT RSS/Atom-Feeds** – für laufende Bedrohungslage/Warnungen; trivial automatisierbar.
3. **EDSA/EDPB-Leitlinien (deutsch)** und **ENISA BYOD/Telework** – CC/EU-Reuse, für Datenschutz-/BYOD-Kapitel.

**Stufe 2 – manuell/halbautomatisch einbinden (hoher Nutzen, Lizenz klären):**
4. **Österreichisches Informationssicherheitshandbuch 4.4.0** – manueller Download der PDF/XML (robots.txt-Sperre!), Lizenz mit A-SIT klären; Kern für Passwort-/Krypto-/Zugriffskapitel.
5. **onlinesicherheit.gv.at**-Artikel (Kennwortsicherheit 2026, mobile Sicherheit) – als Referenz/Zitat, „Letzte Aktualisierung"-Datum als Change-Indikator.
6. **BSI IT-Grundschutz SYS.3.2.1/.2** und **BSI-Mindeststandard MDM** – als „Stand der Technik"-Maßstab für die konkrete MDM-Konfiguration.
7. **BSI TR-02102-1 (2026-01)** – Verschlüsselungs-/Schlüssellängen-Maßstab.

**Stufe 3 – ergänzend:**
8. **DSB-Newsletter/-Leitfäden** – für Datenschutz-Updates (E-Mail-Abo, PDF).
9. **WKO IT-Sicherheitshandbuch für KMU** (it-safe.at) – praxisnahe Ergänzung.

**Benchmarks/Trigger, die die Empfehlung ändern:**
- Wird die Organisation als NIS2-**wesentliche/wichtige Einrichtung** eingestuft (ab 50 Beschäftigten bzw. 10 Mio. € Umsatz in einem der 18 Sektoren nach § 24/§ 25 NISG 2026), gelten ab 1. Oktober 2026 konkrete NISG-Pflichten: Governance-/Schulungspflicht der Leitungsorgane (§ 31), Risikomanagement (§ 32), Wirksamkeitsnachweis (§ 33), Vorfallsmeldung binnen 24/72 Stunden bzw. Abschlussbericht binnen 1 Monat (§ 34), Registrierung binnen 3 Monaten (§ 29 Abs. 3, bis ~Jänner 2027). Aufsicht durch das neu errichtete Bundesamt für Cybersicherheit (dem BMI unterstellt); Strafen bis 10 Mio. € bzw. 2 % des Weltjahresumsatzes (§ 45). → NISG 2026 + zugehörige Verordnungen priorisiert einbinden.
- Erscheint eine neue Handbuch-Version (>4.4.0) oder eine neue TR-02102 (jährlich Januar), Re-Sync auslösen.

## Caveats
- **Handbuch-Version:** 4.4.0 (06.11.2023) ist die belegte aktuellste PDF-Version; die Portal-Katalogseite nennt abweichend eine ältere Version – die offiziellen Angaben sind nicht synchron. Eine 2026er-Version ist nicht nachweisbar.
- **Lizenzlage** bei A-SIT-Handbuch, onlinesicherheit.gv.at, DSB- und WKO-Leitfäden ist **nicht öffentlich/eindeutig deklariert** – im Zweifel keine offene Weiterverbreitung; Rücksprache mit dem Herausgeber.
- **Bildschirmsperre-Minutenwert** und **konkrete MDM-Log-Aufbewahrungsfristen** sind aus den österreichischen Offizialquellen nicht eindeutig ableitbar und organisationsintern (Betriebsvereinbarung) festzulegen.
- **robots.txt-Sperre** auf sicherheitshandbuch.gv.at verhindert vollautomatisches Crawlen.
- **NISG 2026:** Kundgemacht (BGBl I 94/2025), Inkrafttreten 1. Oktober 2026 – konkrete Detailpflichten können sich mit den Durchführungsverordnungen noch konkretisieren.
- Einige zitierte Passwort-Kennzahlen (NIST SP 800-63B Rev.4: 15 Zeichen) stammen aus internationalen, nicht österreichischen Quellen und sind entsprechend gekennzeichnet.
