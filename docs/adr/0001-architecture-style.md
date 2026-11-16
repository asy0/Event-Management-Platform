
# ADR-0001: Modularer Monolith als Architektur

**Status:** Vorgeschlagen  
**Datum:** 2026-11-16


## Kontext

CatchUp ist eine webbasierte Event-Management-Plattform zur Verwaltung von Veranstaltungen und Teilnehmeranmeldungen.

Veranstalter melden sich mit einem Benutzerkonto an, um eigene Veranstaltungen zu erstellen, zu bearbeiten und Teilnehmerlisten einzusehen.

Teilnehmer benötigen im MVP kein Benutzerkonto. Sie können veröffentlichte Veranstaltungen ansehen und sich mit Name und E-Mail-Adresse anmelden.

Das Projekt wird von einem kleinen Team innerhalb eines Semesters entwickelt. Die Architektur muss wartbar, sicher und mit begrenztem Aufwand umsetzbar sein.


## Betrachtete Alternativen

### Option A: Modularer Monolith

Frontend, Backend und Geschäftslogik werden als eine gemeinsam bereitgestellte Anwendung organisiert. Die internen Funktionen werden in klar getrennte Module aufgeteilt.

**Vorteile:**
- Einfacheres Deployment
- Geringerer Betriebsaufwand
- Klare interne Modulstruktur
- Geeignet für kleine Teams

**Nachteile:**
- Gemeinsame Bereitstellung der Komponenten
- Keine unabhängige Skalierung einzelner Module


### Option B: Separat bereitgestelltes Frontend und Backend

Frontend und Backend werden als getrennte Anwendungen entwickelt und unabhängig bereitgestellt. Die Kommunikation erfolgt über eine REST-API.

**Vorteile:**

- Unabhängige Bereitstellung von Frontend und Backend
- Flexible Auswahl von Frontend-Technologien
- Unabhängige Skalierung der beiden Anwendungen möglich
- Klare API-Grenzen

**Nachteile:**

- Höherer Konfigurationsaufwand
- Komplexeres Deployment
- Zusätzlicher Aufwand für die Kommunikation zwischen Frontend und Backend
- Zusätzliche Sicherheits- und Integrationsanforderungen


## Vorgeschlagene Entscheidung

Für CatchUp wird ein modularer Monolith vorgeschlagen.

Das Backend wird als eine Anwendung mit klar getrennten internen Modulen umgesetzt. Eine REST-API stellt die benötigten Funktionen für das Web-Frontend bereit.

Die Anwendung soll intern in folgende Bereiche gegliedert werden:

- Authentifizierung und Veranstalterverwaltung
- Eventverwaltung
- Teilnehmerverwaltung
- Teilnehmeranmeldungen
- Kapazitätskontrolle
- Datenzugriff

Für das MVP ist keine Registrierung oder Anmeldung von Teilnehmern mit einem Benutzerkonto vorgesehen.

Die konkrete Bereitstellung des Frontends und die endgültige Technologieauswahl werden vom Projektteam bestätigt.


## Begründung

Ein modularer Monolith reduziert die technische und organisatorische Komplexität und unterstützt die Umsetzung der MVP-Kernfunktionen innerhalb eines Semesters.

Die einzelnen Fachbereiche können intern modular aufgebaut werden, ohne dass mehrere unabhängige Backend-Dienste betrieben werden müssen.

Die REST-API ermöglicht eine klare Trennung zwischen Benutzeroberfläche und Geschäftslogik.

Für die Kernfunktionen wie Teilnehmeranmeldung, Vermeidung von Doppelanmeldungen und Kapazitätskontrolle ist eine zentrale Geschäftslogik besonders hilfreich.

Die vorgeschlagene Architektur kann später erweitert werden, ohne bereits im MVP eine komplexe verteilte Systemarchitektur einzuführen.



## Konsequenzen

**Positiv:**
- Einfachere Entwicklung und Bereitstellung
- Geringerer Hostingaufwand
- Überschaubare Systemarchitektur

**Negativ:**
- Änderungen können einen gemeinsamen Deployment-Prozess erfordern.
- Die Modulgrenzen müssen konsequent eingehalten werden.

## Offene Punkte

- Teamkenntnisse und Entwicklungsaufwand überprüfen
- Technologie-Stack gemeinsam bestätigen
- Hosting-Anforderungen evaluieren

## AI-Reflexion

KI wurde zur Gegenüberstellung der Architekturvarianten eingesetzt.

Die Empfehlung wurde anhand von Komplexität, Wartbarkeit und Projektumfang bewertet. Die tatsächlichen Teamkenntnisse und der Zeitplan müssen noch durch die Projektgruppe überprüft werden.

