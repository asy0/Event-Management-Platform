
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

Die Plattform muss mehrere gleichzeitige Anmeldungen zu Veranstaltungen verarbeiten können.

PostgreSQL unterstützt Transaktionen und geeignete Sperrmechanismen, mit denen die Kapazitätskontrolle zuverlässig umgesetzt werden kann.

Außerdem bietet PostgreSQL umfangreiche Möglichkeiten zur Sicherstellung der Datenintegrität.

Die Tabellen USERS, EVENTS und REGISTRATIONS können über Primär- und Fremdschlüssel miteinander verbunden werden.

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

## 7. Risiken und Gegenmaßnahmen

**Risiko: Überbuchung bei gleichzeitigen Anmeldungen**

Gegenmaßnahme: Kapazitätsprüfung und Anmeldung innerhalb einer Transaktion mit geeigneter Sperrstrategie.

**Risiko: Doppelanmeldungen**

Gegenmaßnahme: Eindeutige Datenbankregel für die Kombination aus Benutzer und Event.

**Risiko: Fehlerhafte Daten**

Gegenmaßnahme: Fremdschlüssel, Constraints und serverseitige Validierung.

**Risiko: Datenverlust**

Gegenmaßnahme: Regelmäßige Backups und dokumentierter Wiederherstellungsprozess.

## 8. AI-Unterstützung und kritische Reflexion

KI wurde zur Gegenüberstellung von PostgreSQL und SQLite eingesetzt.

Beide Datenbanken unterstützen Transaktionen und können für kleinere Anwendungen geeignet sein.

Die Entscheidung für PostgreSQL basiert insbesondere auf der geplanten gleichzeitigen Verarbeitung von Teilnehmeranmeldungen und der möglichen späteren Erweiterung der Plattform.

Die KI-Empfehlung wurde kritisch betrachtet, da PostgreSQL allein keine Überbuchungen verhindert. Dafür ist zusätzlich eine korrekte Implementierung der Geschäftslogik erforderlich.

## 9. Offene Punkte

- PostgreSQL-Kenntnisse im Team überprüfen
- Hostingkosten vergleichen
- Backup-Strategie festlegen
- Endgültige Entscheidung im Team bestätigen

