# Requirements – EventFlow

## 1. User Stories

### US-01: Veranstaltungen anzeigen

**Priorität:** Must-have

Als Teilnehmer möchte ich eine Liste aller verfügbaren Veranstaltungen sehen, damit ich interessante Events finden kann.

**Akzeptanzkriterien:**
- Alle veröffentlichten Veranstaltungen werden angezeigt.
- Jede Veranstaltung zeigt Titel, Datum, Ort und Beschreibung.
- Abgelaufene oder abgesagte Veranstaltungen werden nicht als buchbar angezeigt.

### US-02: Veranstaltung erstellen

**Priorität:** Must-have

Als Veranstalter möchte ich neue Veranstaltungen erstellen können, damit ich meine Events auf der Plattform veröffentlichen kann.

**Akzeptanzkriterien:**
- Ein Veranstalter kann Titel, Beschreibung, Datum, Uhrzeit und Ort eingeben.
- Eine maximale Teilnehmerzahl kann festgelegt werden.
- Pflichtfelder müssen ausgefüllt sein.
- Das Event wird nach erfolgreicher Speicherung angezeigt.

### US-03: Veranstaltung bearbeiten

**Priorität:** Must-have

Als Veranstalter möchte ich bestehende Veranstaltungen bearbeiten können, damit ich Änderungen aktualisieren kann.

**Akzeptanzkriterien:**
- Veranstalter können eigene Veranstaltungen bearbeiten.
- Änderungen werden gespeichert.
- Die aktualisierten Informationen werden anschließend angezeigt.

### US-04: Veranstaltung löschen

**Priorität:** Should-have

Als Veranstalter möchte ich meine Veranstaltungen löschen können, damit nicht mehr benötigte Events entfernt werden können.

**Akzeptanzkriterien:**
- Veranstalter können eigene Veranstaltungen löschen.
- Vor dem Löschen wird eine Bestätigung verlangt.
- Gelöschte Veranstaltungen sind nicht mehr öffentlich sichtbar.

### US-05: Für eine Veranstaltung anmelden

**Priorität:** Must-have

Als Teilnehmer möchte ich mich für eine Veranstaltung anmelden können, damit ich an dieser teilnehmen kann.

**Akzeptanzkriterien:**
- Teilnehmer können ihren Namen und ihre E-Mail-Adresse eingeben.
- Eine Anmeldung ist nur für verfügbare Veranstaltungen möglich.
- Nach erfolgreicher Anmeldung wird eine Bestätigung angezeigt.
- Dieselbe E-Mail-Adresse kann sich nicht mehrfach für dasselbe Event anmelden.

### US-06: Teilnehmer verwalten

**Priorität:** Must-have

Als Veranstalter möchte ich alle angemeldeten Teilnehmer sehen können, damit ich einen Überblick über meine Veranstaltungen habe.

**Akzeptanzkriterien:**
- Veranstalter können die Teilnehmerliste ihrer eigenen Events öffnen.
- Name und E-Mail-Adresse werden angezeigt.
- Die aktuelle Anzahl der Anmeldungen ist ersichtlich.

### US-07: Maximale Teilnehmerzahl kontrollieren

**Priorität:** Must-have

Als Veranstalter möchte ich eine maximale Teilnehmerzahl festlegen, damit nicht mehr Personen angemeldet werden, als Plätze verfügbar sind.

**Akzeptanzkriterien:**
- Jedes Event kann eine maximale Teilnehmerzahl besitzen.
- Die aktuelle Teilnehmerzahl wird berücksichtigt.
- Bei Erreichen der Kapazität sind keine weiteren Anmeldungen möglich.
- Das Event wird als ausgebucht gekennzeichnet.

### US-08: Teilnehmer abmelden

**Priorität:** Could-have

Als Teilnehmer möchte ich meine Anmeldung stornieren können, damit ich meinen reservierten Platz freigeben kann.

**Akzeptanzkriterien:**
- Eine bestehende Anmeldung kann storniert werden.
- Der freigegebene Platz wird wieder verfügbar.
- Die Teilnehmerzahl wird entsprechend aktualisiert.

### US-09: Veranstaltungen suchen und filtern

**Priorität:** Should-have

Als Teilnehmer möchte ich Veranstaltungen nach Titel oder Datum suchen und filtern können, damit ich passende Events schneller finde.

**Akzeptanzkriterien:**
- Veranstaltungen können nach Titel gesucht werden.
- Eine Filterung nach Datum ist möglich.
- Die Ergebnisliste wird entsprechend aktualisiert.

### US-10: Anmeldebestätigung per E-Mail

**Priorität:** Could-have

Als Teilnehmer möchte ich nach meiner Anmeldung eine Bestätigung per E-Mail erhalten, damit ich meine Teilnahme schriftlich bestätigt bekomme.

**Akzeptanzkriterien:**
- Nach erfolgreicher Anmeldung wird eine E-Mail versendet.
- Die E-Mail enthält den Veranstaltungstitel und das Veranstaltungsdatum.
- Bei fehlgeschlagenem E-Mail-Versand bleibt die erfolgreiche Anmeldung bestehen.

---

## 2. Funktionale Anforderungen

| ID | Anforderung | Priorität |
|---|---|---|
| FR-01 | Das System muss Veranstaltungen erstellen können. | Must |
| FR-02 | Das System muss Veranstaltungen bearbeiten können. | Must |
| FR-03 | Das System muss veröffentlichte Events anzeigen. | Must |
| FR-04 | Das System muss Teilnehmeranmeldungen ermöglichen. | Must |
| FR-05 | Das System muss doppelte Anmeldungen verhindern. | Must |
| FR-06 | Das System muss die Teilnehmerzahl kontrollieren. | Must |
| FR-07 | Das System muss Teilnehmerlisten anzeigen. | Must |
| FR-08 | Das System soll Veranstaltungen löschen können. | Should |
| FR-09 | Das System soll eine Suchfunktion anbieten. | Should |
| FR-10 | Das System könnte eine Abmeldung ermöglichen. | Could |
| FR-11 | Das System könnte E-Mail-Bestätigungen versenden. | Could |

## 3. Nichtfunktionale Anforderungen

### NFR-01: Benutzerfreundlichkeit

Die Benutzeroberfläche muss verständlich und intuitiv bedienbar sein.

**Messbares Kriterium:** Ein neuer Benutzer soll eine Anmeldung ohne zusätzliche Anleitung innerhalb von zwei Minuten durchführen können.

### NFR-02: Performance

Die Plattform soll schnell auf Benutzeraktionen reagieren.

**Messbares Kriterium:** Die wichtigsten Seiten sollen unter normalen Testbedingungen innerhalb von maximal zwei Sekunden geladen werden.

### NFR-03: Sicherheit und Datenschutz

Personenbezogene Daten müssen vor unberechtigtem Zugriff geschützt werden.

**Messbare Kriterien:**
- Passwörter dürfen nicht im Klartext gespeichert werden, falls Benutzerkonten implementiert werden.
- Teilnehmerdaten dürfen nur berechtigten Veranstaltern zugänglich sein.
- Eingaben müssen serverseitig validiert werden.
- Die Verarbeitung personenbezogener Daten muss datenschutzkonform erfolgen.

### NFR-04: Kompatibilität

Die Anwendung soll auf aktuellen Versionen von Chrome, Firefox und Edge funktionieren.

### NFR-05: Wartbarkeit

Der Quellcode soll modular aufgebaut und nachvollziehbar dokumentiert sein.

## 4. Priorisierung

### Must-have
- Events anzeigen und erstellen
- Events bearbeiten
- Teilnehmer anmelden
- Teilnehmerlisten anzeigen
- Maximale Teilnehmerzahl kontrollieren
- Doppelte Anmeldungen verhindern

### Should-have
- Events löschen
- Veranstaltungen suchen und filtern

### Could-have
- Teilnehmer können sich abmelden
- Automatische E-Mail-Bestätigungen

## 5. Geschäftsregeln

- Eine Veranstaltung muss ein gültiges Datum besitzen.
- Die maximale Teilnehmerzahl muss größer als null sein.
- Die Anzahl bestätigter Anmeldungen darf die maximale Teilnehmerzahl nicht überschreiten.
- Eine E-Mail-Adresse darf pro Veranstaltung nur einmal angemeldet sein.
- Nur berechtigte Veranstalter dürfen ihre Veranstaltungen verwalten.
- Vergangene Veranstaltungen können nicht mehr gebucht werden.
