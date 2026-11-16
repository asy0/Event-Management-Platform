
# CatchUp – Hosting-Konzept und Vergleich

**Projekt:** CatchUp – Event Management Platform  
**Stand:** 16.11.2026  
**Status:** Vorschlag, noch nicht endgültig entschieden

## 1. Ziel

Für CatchUp soll eine geeignete Hosting-Lösung ausgewählt werden.

Die Plattform benötigt eine Laufzeitumgebung für die Webanwendung sowie eine PostgreSQL-Datenbank.

Die Hosting-Lösung soll kostengünstig, sicher, zuverlässig und innerhalb eines Semesters realistisch umsetzbar sein.

## 2. Hosting-Anforderungen

### Funktionale Anforderungen

- Bereitstellung einer Node.js-Anwendung
- Unterstützung einer PostgreSQL-Datenbank
- HTTPS-Unterstützung
- Verbindung mit GitHub
- Verwaltung von Umgebungsvariablen
- Speicherung von Veranstalterkonten, Teilnehmerdaten, Veranstaltungen und Anmeldungen


### Nichtfunktionale Anforderungen

- Niedrige monatliche Kosten
- Einfache Bereitstellung und Wartung
- Sichere Datenbankverbindungen
- Regelmäßige Datensicherung
- Zuverlässiger Betrieb während der Projektpräsentation
- Datenschutz gemäß DSGVO
- Möglichkeit zur späteren Erweiterung

## 3. Untersuchte Hosting-Anbieter

### 3.1 Render

Render ist eine Cloud-Plattform zur Bereitstellung von Webanwendungen und Datenbanken.

**Vorteile:**
- Einfache Integration mit GitHub
- Unterstützung von Node.js
- Verwaltete PostgreSQL-Datenbanken
- Automatische HTTPS-Unterstützung
- Geringer Administrationsaufwand

**Nachteile:**
- Einschränkungen bei kostenlosen Diensten
- Kosten für dauerhaft betriebene Dienste
- Weniger Kontrolle über die Serverumgebung

**Kostenbeispiel:**
- Kostenloser Web Service: 0 USD/Monat, mit Einschränkungen
- Starter Web Service: 7 USD/Monat
- Kleine kostenpflichtige PostgreSQL-Instanz: ab 6 USD/Monat
- Beispielsumme: ab 13 USD/Monat, ohne zusätzliche nutzungsabhängige Kosten

Die kostenlose PostgreSQL-Datenbank läuft nach 30 Tagen ab und bietet keine Backups.

### 3.2 Railway

Railway ist eine Cloud-Plattform zur Bereitstellung von Anwendungen und Datenbanken.

**Vorteile:**
- GitHub-Integration
- Unterstützung von Node.js und PostgreSQL
- Einfache Verwaltung von Umgebungsvariablen
- Ressourcenbasierte Abrechnung
- Relativ einfacher Deployment-Prozess

**Nachteile:**
- Kosten abhängig vom Ressourcenverbrauch
- Laufende Kosten müssen überwacht werden
- Ressourcenlimits abhängig vom Tarif

**Kostenbeispiel:**
- Free: 0 USD/Monat mit begrenztem Nutzungsguthaben
- Hobby: 5 USD Mindestbetrag pro Monat, inklusive 5 USD Nutzungsguthaben
- Zusätzlicher Verbrauch wird berechnet

Die tatsächlichen Gesamtkosten hängen von CPU, RAM, Speicher und Netzwerkverkehr ab.

### 3.3 Hetzner Cloud

Hetzner stellt virtuelle Cloud-Server bereit, auf denen die Anwendung und PostgreSQL selbst betrieben werden können.

**Vorteile:**
- Gute Kontrolle über die Serverumgebung
- Attraktive Serverpreise
- Rechenzentren in Deutschland und Finnland
- Flexible Konfiguration
- Node.js und PostgreSQL können installiert werden

**Nachteile:**
- Linux- und Serverkenntnisse erforderlich
- Sicherheitsupdates müssen selbst verwaltet werden
- Einrichtung von HTTPS, Firewall und Backups
- Höherer Administrationsaufwand

**Kostenbeispiel:**
- CX23: 5,49 EUR/Monat ohne Mehrwertsteuer und IPv4
- Weitere Kosten für IPv4, Backups oder zusätzliche Ressourcen möglich

## 4. Vergleich der Hosting-Lösungen

| Kriterium | Render | Railway | Hetzner |
|---|---|---|---|
| Node.js | Ja | Ja | Ja |
| PostgreSQL | Managed verfügbar | Bereitstellbar | Selbst verwaltbar |
| GitHub-Integration | Einfach | Einfach | Zusätzliche Einrichtung |
| HTTPS | Integriert | Integriert | Selbst konfigurieren |
| Einrichtung | Einfach | Einfach | Aufwendiger |
| Wartungsaufwand | Niedrig | Niedrig bis mittel | Höher |
| Kostenmodell | Instanzbasiert | Verbrauchsbasiert | Serverbasiert |
| Semesterprojekt | Sehr geeignet | Sehr geeignet | Bei Serverkenntnissen geeignet |

## 5. Vorläufige Hosting-Empfehlung

Für CatchUp wird zunächst Render empfohlen.

### Begründung

Render bietet eine einfache Bereitstellung der geplanten Node.js-Anwendung und unterstützt PostgreSQL.

Die GitHub-Integration erleichtert die Zusammenarbeit im Team.

Der geringe Administrationsaufwand ermöglicht es, mehr Zeit in die Entwicklung und Qualitätssicherung der Kernfunktionen zu investieren.

### Geplante Bereitstellung

- Webanwendung: Render Web Service
- Backend: Node.js mit Express
- Datenbank: Render PostgreSQL
- Versionsverwaltung: GitHub
- Kommunikation: HTTPS
- Zugangsdaten: Umgebungsvariablen

Diese Konfiguration ist ein Entwurf und keine bereits implementierte Infrastruktur.

## 6. Sicherheits- und Datenschutzkonzept

Für den späteren Betrieb sind folgende Maßnahmen vorgesehen:

- HTTPS für alle externen Verbindungen
- Sichere Speicherung von Passwörtern als Hashwerte
- Datenbank-Zugangsdaten nicht im GitHub-Repository speichern
- Authentifizierung für Veranstalter und Zugriffsschutz für Teilnehmerdaten; Teilnehmer benötigen im MVP kein Benutzerkonto.
- Regelmäßige Backups und Wiederherstellungstests
- Minimierung personenbezogener Daten
- Festlegung von Lösch- und Aufbewahrungsfristen
- Prüfung der Datenverarbeitungsvereinbarung und des Serverstandorts
- Dokumentation der Verantwortlichkeiten für Datenschutz und Sicherheit

Die Wahl eines europäischen Serverstandorts allein garantiert noch keine vollständige DSGVO-Konformität.

## 7. Risiken und Gegenmaßnahmen

| Risiko | Gegenmaßnahme |
|---|---|
| Unerwartete Hostingkosten | Budget und Nutzung überwachen |
| Datenverlust | Backups und Wiederherstellung testen |
| Ausfall des Dienstes | Statusüberwachung und Notfallplan |
| Fehlerhafte Konfiguration | Deployment-Checkliste |
| Unberechtigter Zugriff | Authentifizierung und Berechtigungsprüfung |
| Ablauf kostenloser Dienste | Kostenpflichtige Alternative vorbereiten |

## 8. AI-Unterstützung und kritische Reflexion

KI wurde zur Strukturierung der Hosting-Anforderungen und zum Vergleich möglicher Anbieter eingesetzt.

Die Preisangaben wurden anhand offizieller Anbieterinformationen überprüft.

KI-generierte Empfehlungen sind nicht automatisch korrekt, da sich Preise, Tarifbedingungen und technische Einschränkungen ändern können.

Insbesondere wurden kostenlose Angebote kritisch betrachtet, da diese nicht unbedingt für einen dauerhaften Betrieb geeignet sind.

Die endgültige Entscheidung muss vom Projektteam unter Berücksichtigung des Budgets, der Teamkenntnisse und der tatsächlichen Anforderungen getroffen werden.

## 9. Offene Entscheidungen

- Hostingbudget des Teams bestätigen
- Endgültigen Technologie-Stack bestätigen
- Geeignete Hostingregion festlegen
- Backup- und Wiederherstellungskonzept konkretisieren
- Kostenpflichtige oder kostenlose Umgebung auswählen
- Hosting-Anbieter gemeinsam bestätigen

## 10. Quellen

Preisstand: 16.11.2026

- Render Pricing: https://render.com/pricing
- Render Free Tier: https://render.com/docs/free
- Railway Pricing: https://railway.com/pricing
- Railway Pricing Docs: https://docs.railway.com/pricing/plans
- Hetzner Cloud: https://www.hetzner.com/cloud/
- Hetzner Price Adjustment: https://docs.hetzner.com/general/infrastructure-and-availability/price-adjustment/

Alle Preise und Tarifbedingungen müssen vor einer tatsächlichen Bereitstellung erneut überprüft werden.

