
# ADR-0001: Modularer Monolith als Architektur

**Status:** Vorgeschlagen  
**Datum:** 2026-11-16

## Kontext

CatchUp ist eine webbasierte Event-Management-Plattform für die Verwaltung von Veranstaltungen, Benutzern und Teilnehmeranmeldungen.

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

### Option B: Getrennte Client-Server-Anwendungen

Frontend und Backend werden unabhängig entwickelt und bereitgestellt. Die Kommunikation erfolgt über eine REST-API.

**Vorteile:**
- Unabhängige Entwicklung und Bereitstellung
- Flexible Erweiterungsmöglichkeiten
- Klare API-Grenzen

**Nachteile:**
- Höherer Konfigurationsaufwand
- Komplexeres Deployment
- Zusätzliche Sicherheits- und Integrationsanforderungen

## Vorgeschlagene Entscheidung

Für CatchUp wird ein modularer Monolith vorgeschlagen.

Die Anwendung soll intern in folgende Bereiche gegliedert werden:

- Authentifizierung und Benutzerverwaltung
- Eventverwaltung
- Teilnehmeranmeldungen
- Kapazitätskontrolle
- Datenzugriff

## Begründung

Die Architektur reduziert die technische Komplexität und unterstützt die Umsetzung der Kernfunktionen innerhalb eines Semesters.

Eine REST-API kann innerhalb des Monolithen bereitgestellt werden, ohne Frontend und Backend separat betreiben zu müssen.

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

