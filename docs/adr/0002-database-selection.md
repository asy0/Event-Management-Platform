
# ADR-0002: Auswahl der Datenbank

**Status:** Vorgeschlagen  
**Datum:** 2026-11-16

## 1. Kontext

CatchUp benötigt eine Datenbank zur Speicherung und Verwaltung von Benutzern, Veranstaltungen und Teilnehmeranmeldungen.

Besonders wichtig sind die Datenintegrität, die zuverlässige Kontrolle der Teilnehmerkapazität und die Vermeidung von Doppelanmeldungen.

Da mehrere Benutzer gleichzeitig auf die Plattform zugreifen können, muss die Datenbank parallele Schreibvorgänge zuverlässig unterstützen.

## 2. Betrachtete Alternativen

### Option A: PostgreSQL

PostgreSQL ist ein relationales Open-Source-Datenbanksystem.

**Vorteile:**
- Unterstützung von ACID-Transaktionen
- Gute Unterstützung paralleler Datenbankzugriffe
- Fremdschlüssel und Integritätsbedingungen
- Geeignet für komplexere relationale Datenmodelle
- Gute Erweiterbarkeit

**Nachteile:**
- Zusätzlicher Einrichtungsaufwand
- Separater Datenbankdienst erforderlich
- Hosting kann zusätzliche Kosten verursachen

### Option B: SQLite

SQLite ist eine leichtgewichtige relationale Datenbank, die Daten in einer lokalen Datei speichert.

**Vorteile:**
- Sehr einfache Einrichtung
- Kein separater Datenbankserver notwendig
- Geringer Ressourcenverbrauch
- Gut geeignet für Prototypen und kleine Anwendungen

**Nachteile:**
- Gleichzeitige Schreibvorgänge sind stärker eingeschränkt
- Für verteilte Deployments weniger geeignet
- Skalierung bei hoher Schreiblast schwieriger

## 3. Vergleich

| Kriterium | PostgreSQL | SQLite |
|---|---|---|
| Einrichtung | Aufwendiger | Sehr einfach |
| Transaktionen | Unterstützt | Unterstützt |
| Gleichzeitige Schreibzugriffe | Gut geeignet | Eingeschränkt |
| Datenintegrität | Sehr gut | Gut |
| Hosting | Datenbankdienst nötig | Datei-basiert |
| Erweiterbarkeit | Hoch | Begrenzt |
| Semesterprojekt | Gut geeignet | Gut geeignet |

## 4. Vorgeschlagene Entscheidung

Für CatchUp wird PostgreSQL als primäre Datenbank vorgeschlagen.


## 5. Begründung

Die CatchUp-Plattform muss Veranstaltungen und mehrere gleichzeitige Teilnehmeranmeldungen zuverlässig verwalten können.

PostgreSQL unterstützt ACID-Transaktionen, Fremdschlüssel, Integritätsbedingungen und geeignete Sperrmechanismen.

Das Datenmodell des MVP besteht aus vier zentralen Tabellen:

- ORGANIZERS: Speichert Veranstalterkonten und Zugangsdaten.
- EVENTS: Speichert Veranstaltungen und deren Kapazitäten.
- PARTICIPANTS: Speichert Namen und E-Mail-Adressen der Teilnehmer.
- REGISTRATIONS: Verknüpft Teilnehmer mit Veranstaltungen und speichert den Anmeldestatus.

Teilnehmer benötigen im MVP kein Benutzerkonto. Sie können sich direkt mit ihrem Namen und ihrer E-Mail-Adresse für eine Veranstaltung anmelden.

Die Tabellen werden über Primär- und Fremdschlüssel miteinander verbunden.

Die Kombination aus event_id und participant_id wird als eindeutig definiert, um doppelte Anmeldungen zu verhindern.

Die Kapazitätsprüfung und Speicherung einer Anmeldung müssen innerhalb einer Datenbanktransaktion erfolgen. Dabei sind geeignete Sperrmechanismen erforderlich, damit gleichzeitige Anfragen nicht zu Überbuchungen führen.

PostgreSQL wird aufgrund dieser Anforderungen als geeignete Datenbank für CatchUp vorgeschlagen.

## 6. Konsequenzen

### Positive Konsequenzen

- Zuverlässige Verarbeitung paralleler Anmeldungen
- Gute Unterstützung relationaler Daten
- Erweiterbarkeit für zukünftige Funktionen
- Datenintegrität durch Constraints und Transaktionen

### Negative Konsequenzen

- Zusätzlicher Konfigurationsaufwand
- Datenbank-Hosting muss berücksichtigt werden
- Das Team benötigt grundlegende PostgreSQL-Kenntnisse


**Risiko: Doppelanmeldungen**

Gegenmaßnahme: Die E-Mail-Adresse eines Teilnehmers wird in der Tabelle PARTICIPANTS eindeutig gespeichert.

Zusätzlich wird in REGISTRATIONS eine UNIQUE-Constraint für die Kombination aus event_id und participant_id definiert.

Dadurch kann sich dieselbe E-Mail-Adresse nicht mehrfach für dieselbe Veranstaltung anmelden.

Die Prüfung erfolgt serverseitig und wird durch Datenbank-Constraints abgesichert.


## 8. AI-Unterstützung und kritische Reflexion

KI wurde zur Gegenüberstellung von PostgreSQL und SQLite eingesetzt.

Beide Datenbanken unterstützen Transaktionen und können für kleinere Anwendungen geeignet sein.

Die Entscheidung für PostgreSQL basiert insbesondere auf der geplanten gleichzeitigen Verarbeitung von Teilnehmeranmeldungen und der möglichen späteren Erweiterung der Plattform.

Die KI-Empfehlung wurde kritisch betrachtet, da PostgreSQL allein keine Überbuchungen verhindert. Dafür ist zusätzlich eine korrekte Implementierung der Geschäftslogik erforderlich.


## 9. Offene Punkte

- PostgreSQL-Kenntnisse im Team überprüfen
- Hostingkosten und Datenbankbetrieb bewerten
- Backup- und Wiederherstellungsstrategie festlegen
- Datenschutz und Aufbewahrung personenbezogener Daten prüfen
- Endgültige Datenbankentscheidung im Team bestätigen

Bis zur gemeinsamen Entscheidung bleibt der ADR-Status auf "Vorgeschlagen".


