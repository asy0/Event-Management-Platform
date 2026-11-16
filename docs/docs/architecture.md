# CatchUp – Softwarearchitektur

## 1. Ziel der Architektur

Ziel ist die Entwicklung einer nachvollziehbaren, wartbaren und realistisch umsetzbaren Softwarearchitektur für die Event-Management-Plattform CatchUp.

Die Plattform soll Veranstaltern ermöglichen, Veranstaltungen zu erstellen, zu bearbeiten und abzusagen sowie Teilnehmeranmeldungen und verfügbare Plätze zu verwalten.

Teilnehmer sollen Veranstaltungen suchen, Details ansehen und sich anmelden können.

Die Architektur soll die Anforderungen eines Semesterprojekts erfüllen und spätere Erweiterungen ermöglichen.

## 2. Anforderungen an die Architektur

Die Architektur muss folgende Funktionen unterstützen:

- Benutzerregistrierung sowie Login und Logout
- Veranstaltungen anzeigen, suchen und filtern
- Veranstaltungsdetails anzeigen
- Veranstaltungen erstellen, bearbeiten und absagen
- Teilnehmer für Veranstaltungen anmelden
- Anmeldungen verwalten und stornieren
- Maximale Teilnehmerzahl kontrollieren
- Doppelanmeldungen und Überbuchungen verhindern
- Rollen und Zugriffsrechte berücksichtigen

Wichtige Qualitätsanforderungen sind:

- Sicherheit und Datenschutz
- Wartbarkeit und Erweiterbarkeit
- Zuverlässige Datenverarbeitung
- Benutzerfreundlichkeit
- Angemessene Entwicklungs- und Hostingkosten

## 3. Architekturvariante A – Monolithische Webanwendung

### Beschreibung

Bei einer monolithischen Architektur werden Benutzeroberfläche, Geschäftslogik und Datenzugriff innerhalb einer gemeinsamen Anwendung entwickelt und bereitgestellt.

Die Anwendung greift auf eine zentrale Datenbank zu.

### Vorteile

- Einfachere Entwicklung und Bereitstellung
- Geringerer Konfigurationsaufwand
- Weniger Kommunikationsschnittstellen
- Gut geeignet für kleine Entwicklungsteams
- Häufig geringere Betriebskomplexität

### Nachteile

- Stärkere Kopplung der Anwendungskomponenten
- Frontend und Backend können nicht unabhängig bereitgestellt werden
- Änderungen können die gesamte Anwendung betreffen
- Bei wachsendem Projektumfang schwieriger zu skalieren

### Bewertung

Diese Variante eignet sich besonders für ein Semesterprojekt mit begrenzter Entwicklungszeit. Durch eine modulare Struktur kann die Wartbarkeit verbessert werden.

## 4. Architekturvariante B – Getrennte Client-Server-Architektur

### Beschreibung

Bei dieser Variante werden Frontend und Backend als getrennte Anwendungen entwickelt.

Das Frontend kommuniziert über eine REST-API mit dem Backend. Das Backend verarbeitet die Geschäftslogik und verwaltet den Datenbankzugriff.

### Vorteile

- Klare Trennung zwischen Benutzeroberfläche und Geschäftslogik
- Frontend und Backend können unabhängig entwickelt werden
- Gute Erweiterbarkeit durch definierte API-Schnittstellen
- Möglichkeit zur späteren Integration weiterer Clients
- Unabhängige Bereitstellung der Anwendungen möglich

### Nachteile

- Höherer Entwicklungs- und Konfigurationsaufwand
- API-Kommunikation muss sorgfältig gestaltet werden
- Zusätzliche Anforderungen an Authentifizierung und CORS
- Mehr Aufwand bei Tests und Deployment
- Potenziell höhere Hostingkomplexität

### Bewertung

Diese Variante bietet eine klare technische Trennung und ist für eine moderne Webplattform gut geeignet. Für ein kleines Semesterprojekt muss jedoch der zusätzliche Aufwand berücksichtigt werden.

## 5. Vergleich der Architekturvarianten

| Kriterium | Monolith | Client-Server |
|---|---|---|
| Implementierungsaufwand | Niedriger | Höher |
| Deployment | Einfacher | Aufwendiger |
| Wartbarkeit | Gut bei modularer Struktur | Gut bei klaren Schnittstellen |
| Erweiterbarkeit | Möglich | Flexibel |
| API-Integration | Optional | Zentraler Bestandteil |
| Betriebskosten | Tendenziell niedriger | Abhängig vom Hosting |
| Eignung für Semesterprojekt | Sehr gut | Gut bei ausreichender Erfahrung |

Die Bewertung ist qualitativ und basiert auf den angenommenen Anforderungen. Konkrete Kosten und Technologien werden in den nächsten Schritten untersucht.

## 6. Vorläufige Empfehlung

Für CatchUp wird zunächst eine **modulare monolithische Architektur** empfohlen.

Die Anwendung soll intern in klar getrennte Bereiche strukturiert werden:

- Benutzerverwaltung und Authentifizierung
- Eventverwaltung
- Teilnehmeranmeldungen
- Kapazitätskontrolle
- Datenzugriff

### Begründung

Die modulare monolithische Architektur bietet einen guten Kompromiss zwischen einfacher Umsetzung, Wartbarkeit und Erweiterbarkeit.

Sie reduziert den technischen Aufwand und ermöglicht es dem Team, sich auf die Kernfunktionen der Plattform zu konzentrieren.

### Kritische Bewertung

Eine getrennte Client-Server-Architektur könnte sinnvoller sein, wenn das Team bereits Erfahrung mit REST-APIs, unabhängigen Frontends und Deployment besitzt.

Die endgültige Entscheidung erfolgt nach der Technologieauswahl und der Bewertung der Teamkompetenzen.

## 7. AI-Unterstützung und Reflexion

KI wurde zur Erstellung und Gegenüberstellung möglicher Architekturvarianten eingesetzt.

Die Vorschläge wurden anhand der Projektanforderungen, des Semesterumfangs, der Komplexität und der Wartbarkeit kritisch verglichen.

Die KI kann die technischen Möglichkeiten erläutern, kennt jedoch nicht automatisch die tatsächlichen Fähigkeiten des Entwicklungsteams oder alle Rahmenbedingungen des Projekts.

Daher ist die Empfehlung vorläufig und muss vom Projektteam geprüft und bestätigt werden.
