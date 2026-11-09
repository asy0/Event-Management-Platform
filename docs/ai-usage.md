# AI Usage – CatchUp
## 1. Ziel des AI-Einsatzes

Während der Requirements-Engineering-Phase wurde künstliche Intelligenz als Unterstützung bei der Analyse, Strukturierung und Überprüfung der Projektanforderungen eingesetzt.

Das Ziel war es, aus einer groben Projektidee eine nachvollziehbare und überprüfbare Produktspezifikation zu entwickeln.

Die endgültige Entscheidung über die Anforderungen und deren Priorisierung liegt beim Projektteam.

## 2. Verwendete AI-Anwendungen

### AI-Anwendung 1: Generierung und Strukturierung von User Stories

**Ziel:**

Aus der ursprünglichen Projektidee sollten mögliche Benutzergruppen, Anwendungsfälle und User Stories abgeleitet werden.

**Verwendeter Prompt:**

"Ich plane eine Event Management Platform, mit der Veranstalter Veranstaltungen erstellen und verwalten können. Teilnehmer sollen Events ansehen und sich anmelden können.

Identifiziere die wichtigsten Benutzergruppen und erstelle mindestens zehn konkrete User Stories im Format:

Als [Benutzer] möchte ich [Funktion], damit [Nutzen].

Ergänze für jede User Story eine Priorität und überprüfbare Akzeptanzkriterien.

Achte darauf, dass die Anforderungen für ein Softwareprojekt innerhalb eines Semesters realistisch umsetzbar sind."

**Ergebnis:**

Die AI lieferte verschiedene User Stories für Veranstalter und Teilnehmer.

Dazu gehörten unter anderem:
- Veranstaltungen erstellen und bearbeiten
- Veranstaltungen anzeigen
- Teilnehmer anmelden
- Teilnehmerlisten verwalten
- Maximale Teilnehmerzahlen kontrollieren
- Veranstaltungen suchen

**Kritische Bewertung:**

Die generierten User Stories waren eine hilfreiche Ausgangsbasis. Allerdings waren einige Vorschläge für das MVP zu umfangreich.

Beispielsweise wurden zusätzliche Funktionen wie E-Mail-Benachrichtigungen und Teilnehmerabmeldungen vorgeschlagen.

Diese wurden deshalb nicht als Must-have-Funktionen übernommen.

### AI-Anwendung 2: Prüfung auf Widersprüche und Unklarheiten

**Ziel:**

Die bereits erstellten Anforderungen sollten auf fehlende Informationen, mögliche Widersprüche und technische Probleme überprüft werden.

**Verwendeter Prompt:**

"Überprüfe die folgenden Anforderungen einer Event Management Platform kritisch.

Untersuche insbesondere:

1. Gibt es widersprüchliche Anforderungen?
2. Sind die Akzeptanzkriterien eindeutig und testbar?
3. Fehlen wichtige Geschäftsregeln?
4. Gibt es Sicherheits- oder Datenschutzprobleme?
5. Sind die Must-have-Anforderungen für ein Semesterprojekt realistisch?
6. Gibt es Abhängigkeiten zwischen den User Stories?

Gib konkrete Verbesserungsvorschläge und begründe diese."

**Ergebnis und erkannte Probleme:**

Bei der Überprüfung wurden folgende Punkte als besonders wichtig identifiziert:

- Es muss verhindert werden, dass sich Teilnehmer mehrfach für dasselbe Event anmelden.
- Das System muss verhindern, dass die maximale Teilnehmerzahl überschritten wird.
- Es muss geklärt werden, wer Veranstaltungen bearbeiten darf.
- Teilnehmerdaten dürfen nicht für unberechtigte Personen zugänglich sein.
- Für jede Veranstaltung muss ein gültiges Datum definiert sein.

**Vorgenommene Anpassungen:**

Die Anforderungen wurden um entsprechende Geschäftsregeln und Akzeptanzkriterien ergänzt.

Außerdem wurde der MVP-Scope reduziert, um die Umsetzung innerhalb eines Semesters realistisch zu halten.

## 3. Kritische Reflexion

Die Verwendung von AI hat den Requirements-Engineering-Prozess unterstützt und beschleunigt.

Besonders hilfreich war die Generierung erster User Stories sowie die strukturierte Überprüfung der Anforderungen.

Allerdings wurden nicht alle AI-Vorschläge unverändert übernommen.

Einige Funktionen waren für die erste Produktversion nicht notwendig oder hätten den Projektumfang unnötig vergrößert.

Außerdem müssen AI-generierte Anforderungen immer auf Verständlichkeit, Umsetzbarkeit und Testbarkeit geprüft werden.

Die AI kann Vorschläge liefern und mögliche Probleme erkennen. Die Verantwortung für die endgültigen Anforderungen und Produktentscheidungen bleibt jedoch beim Projektteam.

## 4. Fazit

AI war ein hilfreiches Werkzeug bei der Analyse und Strukturierung der Projektidee.

Die wichtigsten Erkenntnisse waren:

- AI kann bei der Erstellung von User Stories unterstützen.
- AI kann Anforderungen auf mögliche Lücken und Widersprüche untersuchen.
- AI-generierte Ergebnisse müssen kritisch überprüft werden.
- Eine klare MVP-Abgrenzung ist entscheidend für ein realistisches Softwareprojekt.

**Key Takeaway:**

AI can generate requirements, but it cannot decide what your product should be.
