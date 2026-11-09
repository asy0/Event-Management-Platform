# MVP – CatchUp
## 1. Ziel des MVP

Das MVP soll eine funktionsfähige Webanwendung bereitstellen, mit der Veranstalter Events verwalten und Teilnehmer sich für Veranstaltungen anmelden können.

Der wichtigste demonstrierbare Anwendungsfall ist:

Ein Veranstalter erstellt eine Veranstaltung. Ein Teilnehmer sieht diese Veranstaltung, meldet sich an und wird anschließend in der Teilnehmerliste des Veranstalters angezeigt.

## 2. Enthaltene Funktionen

### 2.1 Veranstalterbereich

- Veranstalter können sich anmelden.
- Veranstalter können neue Veranstaltungen erstellen.
- Veranstalter können eigene Veranstaltungen bearbeiten.
- Veranstalter können ihre Veranstaltungen auflisten.
- Veranstalter können Teilnehmerlisten einsehen.

### 2.2 Teilnehmerbereich

- Teilnehmer können veröffentlichte Veranstaltungen ansehen.
- Teilnehmer können die Details einer Veranstaltung öffnen.
- Teilnehmer können sich mit Name und E-Mail-Adresse anmelden.
- Teilnehmer erhalten eine Bestätigung auf der Webseite.

### 2.3 Anmeldungsverwaltung

- Das System speichert jede Anmeldung.
- Doppelte Anmeldungen werden verhindert.
- Die maximale Teilnehmerzahl wird berücksichtigt.
- Ausgebuchte Veranstaltungen werden entsprechend gekennzeichnet.

## 3. Nicht im MVP enthalten

Folgende Funktionen werden bewusst auf spätere Versionen verschoben:

- Online-Zahlungen und Ticketverkauf
- QR-Code-Tickets
- Check-in-System für Veranstaltungen
- Automatische E-Mail-Bestätigungen
- Teilnehmer können ihre Anmeldung selbst stornieren
- Erweiterte Such- und Filterfunktionen
- Statistiken und Diagramme
- Mehrsprachigkeit
- Mobile App
- Mehrere Rollen und komplexe Berechtigungssysteme

## 4. Priorisierung

| Funktion | Priorität | MVP |
|---|---|---|
| Veranstalter-Login | Must | Ja |
| Event erstellen | Must | Ja |
| Event bearbeiten | Must | Ja |
| Events anzeigen | Must | Ja |
| Teilnehmer anmelden | Must | Ja |
| Teilnehmerliste | Must | Ja |
| Kapazitätskontrolle | Must | Ja |
| Doppelte Anmeldungen verhindern | Must | Ja |
| Event löschen | Should | Nein |
| Events suchen und filtern | Should | Nein |
| Teilnehmer abmelden | Could | Nein |
| E-Mail-Bestätigung | Could | Nein |

## 5. Vollständiger MVP-Anwendungsfall

### Szenario: Anmeldung zu einem Workshop

1. Der Veranstalter meldet sich in der Plattform an.
2. Der Veranstalter erstellt einen Workshop.
3. Er gibt Titel, Beschreibung, Datum, Uhrzeit, Ort und maximale Teilnehmerzahl ein.
4. Das Event wird veröffentlicht.
5. Ein Teilnehmer öffnet die öffentliche Eventübersicht.
6. Der Teilnehmer wählt den Workshop aus.
7. Er gibt seinen Namen und seine E-Mail-Adresse ein.
8. Das System überprüft die Angaben und die verfügbaren Plätze.
9. Die Anmeldung wird gespeichert.
10. Der Veranstalter kann den Teilnehmer in seiner Teilnehmerliste sehen.

**Ergebnis:** Der gesamte Anmeldeprozess funktioniert ohne manuelle Verwaltung über Excel oder E-Mail.

## 6. Technische Abgrenzung

Für das MVP wird eine einfache Webanwendung mit einer zentralen Datenbank entwickelt.

Die Anwendung benötigt mindestens folgende Datenbereiche:

### Event
- ID
- Titel
- Beschreibung
- Datum
- Uhrzeit
- Ort
- Maximale Teilnehmerzahl
- Veranstalter-ID

### Teilnehmer
- ID
- Name
- E-Mail-Adresse

### Anmeldung
- ID
- Event-ID
- Teilnehmer-ID
- Anmeldedatum
- Status

### Veranstalter
- ID
- Name
- E-Mail-Adresse
- Passwort-Hash

## 7. Erfolgskriterien

Das MVP gilt als erfolgreich umgesetzt, wenn:

- Ein Veranstalter sich anmelden kann.
- Ein Veranstalter ein Event erstellen kann.
- Ein Teilnehmer das Event sehen kann.
- Ein Teilnehmer sich erfolgreich anmelden kann.
- Die Anmeldung in der Datenbank gespeichert wird.
- Der Veranstalter die Anmeldung sehen kann.
- Keine Anmeldung über die maximale Teilnehmerzahl hinaus möglich ist.
- Doppelte Anmeldungen verhindert werden.

## 8. Mögliche Erweiterungen nach dem MVP

In späteren Entwicklungsphasen können E-Mail-Benachrichtigungen, Suchfunktionen, QR-Code-Tickets und Statistiken ergänzt werden.
