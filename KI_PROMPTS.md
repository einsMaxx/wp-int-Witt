\# KI-Prompts



Für die Erstellung der lokalen WordPress-Entwicklungsumgebung wurde ChatGPT als Unterstützung verwendet.



\## Docker Compose



Prompt:

Erstelle eine Docker-Compose-Konfiguration für eine lokale WordPress-Entwicklungsumgebung mit WordPress, MariaDB und phpMyAdmin.



Ergebnis:

\- WordPress als eigener Container

\- MariaDB als Datenbank

\- phpMyAdmin zur Verwaltung der Datenbank

\- WordPress auf Port 8080

\- phpMyAdmin auf Port 8081



\## Healthcheck und Abhängigkeiten



Prompt:

Wie kann sichergestellt werden, dass WordPress erst startet, wenn MariaDB bereit ist?



Ergebnis:

\- Healthcheck für MariaDB eingerichtet

\- depends\_on mit service\_healthy verwendet

\- WordPress startet erst, wenn MariaDB healthy ist

\- phpMyAdmin hängt ebenfalls von MariaDB ab



\## Volumes



Prompt:

Welche Volumes sind für die WordPress-Entwicklungsumgebung sinnvoll?



Ergebnis:

\- Named Volume db\_data für die MariaDB-Daten

\- Bind-Mount für wordpress/wp-content

\- Datenbankdaten bleiben dauerhaft erhalten

\- WordPress-Inhalte können lokal bearbeitet werden



\## Sicherheit



Prompt:

Wie können die Datenbank-Zugangsdaten verwendet werden, ohne Passwörter in Git zu speichern?



Ergebnis:

\- Zugangsdaten werden in einer lokalen .env gespeichert

\- .env wird über .gitignore ausgeschlossen

\- .env.example wird als Vorlage in Git gespeichert

\- Keine echten Passwörter werden committed



\## Prüfung und Start



Prompt:

Wie kann die Docker-Compose-Konfiguration geprüft und gestartet werden?



Ergebnis:

\- docker compose config prüft die Konfiguration

\- docker compose up -d startet die Umgebung

\- docker compose ps zeigt den Status der Container

\- docker compose down beendet die Umgebung

