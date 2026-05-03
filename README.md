# Prog2-blatt-01
Blatt 01: Git Basics und Gradle

1. Git Status

Aufgabe:
Analysiere die Ausgabe von git status und beschreibe den aktuellen Zustand des Repositories.

Lösung:

Aktueller Branch:
b03, d. h. auf diesem Entwicklungszweig wird gearbeitet
Geänderte Dateien (noch nicht gestaged):
CONTRIBUTING.md
homework/b03.md
→ Änderungen sind vorhanden, aber noch nicht für Commit vorbereitet
Neue Datei:
foo.java
→ wird von Git noch nicht verfolgt (untracked)
Aktuell:
keine Änderungen im Staging-Bereich
daher kein Commit direkt möglich

Nur foo.java committen:

Datei gezielt hinzufügen:
git add foo.java
Commit erstellen:
git commit -m "Add initial foo implementation"

2. Git-Quest (Analyse der Historie)

Aufgabe:
Untersuche die Historie mit git log, git show und git diff und finde bestimmte Informationen.

Lösung:

Beginn der Story:
bei tag 01 startet die Handlung rund um Markus
Erste Experience-Punkte:
bei tag 01.3 erhält er erstmals 4 Punkte
Erster Hungerwert:
bei tag 03.4 erreicht er erstmals den Wert 10
Inventar:
im Verlauf sind Heiltränke vorhanden → er sammelt Items
Shop-Interaktion:
Markus kauft einen Heiltrank für 10 Gold
Änderung zwischen tag 03 und tag 04:
Story wird erweitert (neuer Händler)
mehrere Werte ändern sich gleichzeitig:
Leben steigt
Hunger fällt auf 0
Gold wird verbraucht
Nahrung:
Brot wird konsumiert
erkennbar daran, dass es aus dem Inventar verschwindet und im Text eine Stärkung erwähnt wird

3. Weitere Git-Aufgaben

Aufgabe:
Fehlerhaften Commit korrigieren und weitere sinnvolle Commits erstellen.

Lösung:

Fehler in tag 04.5:
Experience-Wert war falsch eingetragen
Korrektur:
mit git commit --amend
neuer Wert: 42 Experience

Weitere Commits (leicht anders formuliert):

tag 04.6:
Questlog erweitert und zusätzliche Infos ergänzt
nur questlog.md betroffen
tag 04.7:
mehrere zusammenhängende Änderungen gleichzeitig committed
z. B. Anpassungen an Stats und Story
tag 04.8:
Refactoring:
Ausrüstung aus stats.md entfernt
neue Struktur durch eigene Datei gear.md

4. Commit-Messages

Aufgabe:
Bewerte und beschreibe gute Commit-Messages.

Lösung:

Gute Commit-Messages:
kurz, aber aussagekräftig
beschreiben konkret, was geändert wurde
Beispiel:
Refactor: move gear into separate file
Schlechte Commit-Messages:
zu allgemein und nicht hilfreich:
update
fix
changes
Problem:
man versteht später nicht mehr, was gemacht wurde

5. Gradle Grundlagen

Aufgabe:
Gradle installieren, Projekt erstellen und ausführen.

Lösung:

Installation prüfen:
gradle -v
zeigt Version und Umgebung
Projekt erstellen:
gradle init
Auswahl im Setup:
Application-Projekt
Sprache: Java
Build-Sprache: Groovy DSL
Testframework: JUnit Jupiter
Java-Version: 25

Projekt starten:

./gradlew :app:run
Ergebnis:
Programm läuft erfolgreich
Ausgabe:
Hello World
BUILD SUCCESSFUL

6. Gradle Tasks

Aufgabe:
Wichtige Tasks identifizieren und verstehen.

Lösung:

Übersicht aller Tasks:
./gradlew tasks
Wichtige Tasks:
run
startet die Anwendung direkt
build
kompiliert Code + führt Tests aus
test
führt ausschließlich Tests aus

7. Projektstruktur

Aufgabe:
Verstehen, wie das Projekt aufgebaut ist.

Lösung:

app/src/main/java
enthält den eigentlichen Java-Code
app/src/test/java
enthält Testklassen
app/build.gradle.kts
Build-Konfiguration des Moduls
settings.gradle.kts
globale Projekteinstellungen
gradlew
Wrapper, damit Gradle ohne Installation läuft

8. Buildskript verstehen

Aufgabe:
Die wichtigsten Bestandteile erklären.

Lösung:

plugins
bindet Funktionen ein (z. B. application)
repositories
legt fest, wo Libraries geladen werden (z. B. Maven Central)
dependencies
externe Bibliotheken wie JUnit für Tests
application
definiert die Main-Klasse zum Starten

9. Java-Version

Aufgabe:
Verwendete Java-Version prüfen.

Lösung:

Terminal:
java -version
Im Code:
System.getProperty("java.version")
Ergebnis:
Java 25 wird verwendet

10. IDE

Aufgabe:
Projekt in einer IDE nutzen.

Lösung:

Projekt in IntelliJ geöffnet
Gradle wurde automatisch erkannt
Tasks können:
über das Gradle-Fenster ausgeführt werden
oder direkt über Run/Play Button

11. Spotless

Aufgabe:
Automatische Code-Formatierung einrichten.

Lösung:

Spotless-Plugin integriert
Vorteile:
einheitlicher Code-Stil
weniger manuelle Formatierung nötig
Befehle:
./gradlew spotlessApply
formatiert den Code automatisch
./gradlew spotlessCheck
prüft, ob alles korrekt formatiert ist

Fazit

Git:
Umgang mit Status, Staging und Commits gelernt
Historie analysiert und Fehler korrigiert
Gradle:
Projekt erstellt und erfolgreich ausgeführt
wichtige Tasks verstanden
Zusatz:
automatisches Formatieren mit Spotless integriert
