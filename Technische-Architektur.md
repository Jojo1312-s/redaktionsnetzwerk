Technische Architektur

Version: 1.0
Stand: 04.11.2026
Status: Erstfassung
Dateiname: Technische-Architektur.md

⸻

1. Zweck dieses Handbuchs

Dieses Handbuch beschreibt die technische Architektur des Redaktionsnetzwerks.

Es dient als eigenständige technische Übergabe- und Arbeitsgrundlage und dokumentiert:

* den grundsätzlichen Systemaufbau,
* die gemeinsame Infrastruktur,
* die technische Organisation der sieben Agenten,
* die zentrale Datenhaltung,
* die Medienproduktion,
* die Plattformanbindungen,
* die Kommunikation zwischen den Systemkomponenten,
* die technischen Anforderungen an Zuverlässigkeit und Skalierbarkeit,
* die offenen technischen Entscheidungen.

Das Handbuch beschreibt die geplante Architektur. Es ist keine Bestätigung, dass die beschriebenen Komponenten bereits implementiert oder produktiv in Betrieb sind.

2. Abhängigkeiten zu anderen Handbüchern

Handbuch	Relevanz
Projektgrundlage.md	Grundstruktur, Ziele und verbindliche Projektprinzipien
Redaktionshandbuch.md	Agentenstruktur und redaktionelle Aufgaben
Plattformhandbuch.md	Gemeinsame Plattformregeln und Veröffentlichungsstrategie
Betriebs-und-Sicherheitskonzept.md	Berechtigungen, Sicherheit, Überwachung und Not-Aus
Plattformmodule	Konkrete Schnittstellen und technische Anforderungen einzelner Plattformen
Entwicklungsstatus.md	Implementierungsstand und offene technische Aufgaben

Dieses Handbuch ist für die technische Gesamtarchitektur zuständig. Die Plattformmodule beschreiben die jeweiligen Plattformadapter und ihre spezifischen Schnittstellen.

3. Grundarchitektur

Das Netzwerk verwendet eine gemeinsame technische Infrastruktur für sechs eigenständige Redaktionsagenten und einen zentralen Koordinationsagenten.

Die Agenten werden nicht als sieben voneinander unabhängige Server betrieben.

Stattdessen sollen sie auf einer gemeinsamen Infrastruktur laufen und auf gemeinsame technische Dienste zugreifen können.

Die Architektur besteht konzeptionell aus folgenden Bereichen:

1. Agenten- und Koordinationssystem
2. Zentrale Anwendungslogik
3. Datenbank und Wissenshaltung
4. Medienarchiv
5. Medienproduktionssystem
6. Plattformadapter
7. Aufgaben- und Nachrichtenverarbeitung
8. Überwachung und Protokollierung
9. Benutzeroberfläche und administrative Steuerung

Die technische Trennung dieser Bereiche soll ermöglichen, einzelne Komponenten unabhängig weiterzuentwickeln und bei Bedarf auszutauschen.

4. Agentenarchitektur

4.1 Sechs Redaktionsagenten

Jede der sechs redaktionellen Identitäten erhält einen eigenen KI-Redaktionsagenten.

Jeder Agent besitzt:

* ein eigenes redaktionelles Profil,
* eigene thematische Schwerpunkte,
* individuelle Arbeitskontexte,
* eigene redaktionelle Aufgaben,
* Zugriff auf die für seine Arbeit freigegebenen gemeinsamen Wissensbestände,
* Zugriff auf die benötigten Produktions- und Plattformfunktionen.

Die Agenten teilen sich die technische Infrastruktur, bleiben aber redaktionell eigenständig.

4.2 Koordinationsagent

Der Koordinationsagent übernimmt die zentrale Koordination.

Er benötigt insbesondere Zugriff auf:

* relevante Informationen aller Redaktionen,
* den gemeinsamen Redaktionskalender,
* die zentralen Aufgaben und Veröffentlichungsinformationen,
* die gemeinsamen Wissensbestände,
* netzwerkweite Leistungsdaten,
* technische Status- und Fehlermeldungen.

Der Koordinationsagent erhält nicht automatisch uneingeschränkte administrative Rechte.

Seine Berechtigungen bleiben durch die vom Projektbetreiber festgelegten Grenzen beschränkt.

4.3 Gemeinsame technische Dienste

Die Agenten greifen auf gemeinsame Dienste zurück, beispielsweise:

* KI-API,
* Datenbank,
* Medienarchiv,
* Produktionswerkzeuge,
* Aufgabenverwaltung,
* Plattformadapter,
* Protokollierung.

Dadurch werden doppelte Infrastruktur und unnötige Betriebskosten vermieden.

5. Geplante technische Werkzeuge

Für den technischen Aufbau sind folgende Werkzeuge vorgesehen:

Werkzeug	Vorgesehener Zweck	Status
Python	Anwendungslogik, Automatisierung und Verarbeitung	Vorgesehen
PostgreSQL	Zentrale relationale Datenbank	Vorgesehen
n8n	Workflow-Automatisierung und Prozesssteuerung	Vorgesehen
Docker	Containerisierung und Bereitstellung	Vorgesehen
FFmpeg	Video- und Audioverarbeitung	Vorgesehen
Whisper	Transkription und Audioverarbeitung	Vorgesehen
Pillow	Bildbearbeitung und Grafikerstellung	Vorgesehen
SVG	Vektorbasierte Grafiken	Vorgesehen
ImageMagick	Bildverarbeitung	Vorgesehen
OpenAI API	KI-gestützte Recherche, Text- und Inhaltsproduktion	Vorgesehen

Die konkrete Auswahl, Versionierung und technische Integration dieser Werkzeuge ist im weiteren Entwicklungsverlauf zu prüfen.

Die Tabelle beschreibt die bisherige Planung und keine bereits vollständig bestätigte Implementierungsentscheidung.

6. Hosting und Serverinfrastruktur

6.1 Hosting-Anbieter

Als Hosting-Anbieter wurde DigitalOcean ausgewählt.

Die konkrete Serverregion ist noch nicht abschließend festgelegt.

Frankfurt und Amsterdam wurden als mögliche Standorte betrachtet.

6.2 Serverdimensionierung

In der bisherigen Planung wurden folgende Größenordnungen betrachtet:

Servergröße	Ungefährer monatlicher Preis	Einordnung
2 GB RAM	12 USD	Für einen eingeschränkten Prototyp denkbar
4 GB RAM	24 USD	Leistungsfähiger, aber budgetkritisch
8 GB RAM	48 USD	Überschreitet bereits allein das geplante Gesamtbudget

Diese Preise sind Planungswerte aus der bisherigen Betrachtung und müssen vor einer tatsächlichen Buchung erneut geprüft werden.

Ein Server mit 2 GB RAM ist für das vollständige geplante Netzwerk voraussichtlich stark eingeschränkt.

Die vollständige Produktionsarchitektur kann mit dem derzeit vorgesehenen Budget möglicherweise nicht betrieben werden.

6.3 Grundanforderungen

Die Infrastruktur muss langfristig folgende Aufgaben unterstützen:

* Betrieb der sieben Agenten,
* zentrale Aufgabenverarbeitung,
* Datenbankbetrieb,
* Medienarchiv,
* Medienproduktion,
* Plattformkommunikation,
* Protokollierung,
* Überwachung,
* Datensicherung.

Die konkrete Aufteilung auf einzelne Server oder Dienste ist noch zu entwickeln.

7. Datenbank und zentrale Datenhaltung

7.1 PostgreSQL

PostgreSQL ist als zentrale relationale Datenbank vorgesehen.

Sie soll die strukturierten Daten des Netzwerks verwalten.

Dazu gehören insbesondere:

* Agenten und ihre Konfigurationen,
* redaktionelle Aufgaben,
* Themen und Recherchen,
* Veröffentlichungen,
* Plattformzuordnungen,
* Quelleninformationen,
* Rechteinformationen,
* Korrekturen und Versionshistorien,
* Kalenderdaten,
* Leistungsdaten,
* Experimente,
* Protokolle und Statusinformationen.

Die endgültige Datenbankstruktur ist noch zu entwerfen.

7.2 Gemeinsame Wissensbasis

Das Netzwerk benötigt eine gemeinsame Wissensbasis.

Sie enthält insbesondere:

* politische Grundlagen,
* theoretische Referenzen,
* gemeinsame redaktionelle Prinzipien,
* die sechs redaktionellen Profile,
* plattformübergreifende Regeln,
* technische Handbücher und relevante Dokumentation.

Die Wissensbasis muss so strukturiert sein, dass die Agenten auf die für ihre Aufgaben relevanten Informationen zugreifen können.

7.3 Gemeinsames Recherchearchiv

Zusätzlich ist ein gemeinsames Recherchearchiv vorgesehen.

Es enthält beispielsweise:

* geprüfte Quellen,
* Studien,
* Nachrichten und Hintergrundberichte,
* Dokumente,
* Medienmaterial,
* Herkunfts- und Rechteinformationen,
* relevante Rechercheergebnisse.

Die Informationen müssen mit nachvollziehbaren Quellenangaben gespeichert werden.

7.4 Redaktionell private Bereiche

Nicht sämtliche Informationen sollen für alle Agenten zugänglich sein.

Jede Redaktion benötigt einen eigenen privaten Arbeitsbereich.

Dort können beispielsweise gespeichert werden:

* interne Notizen,
* redaktionelle Planungen,
* unveröffentlichte Entwürfe,
* interne Diskussionen.

Veröffentlichte Inhalte werden dagegen netzwerkweit zugänglich gemacht.

8. Datenzugriff und Berechtigungsmodell

Für den gemeinsamen Datenzugriff ist das Modell shared_selective vorgesehen.

Es bedeutet:

* Gemeinsame Wissensbestände sind für alle berechtigten Agenten zugänglich.
* Gemeinsame Recherchebestände werden entsprechend ihrer Relevanz und Berechtigung geteilt.
* Private redaktionelle Arbeitsbereiche bleiben auf die jeweilige Redaktion beschränkt.
* Veröffentlichte Inhalte werden innerhalb des Netzwerks geteilt.
* Der Koordinationsagent erhält die für seine Aufgaben erforderlichen übergreifenden Informationen.

Die Berechtigungen müssen technisch durchgesetzt werden.

Es reicht nicht aus, den Agenten lediglich durch eine Prompt-Anweisung mitzuteilen, dass sie bestimmte Daten nicht verwenden sollen.

Die tatsächliche Datenbank- und Anwendungsschicht muss Zugriffe entsprechend beschränken.

9. Zentrale Medienproduktion

9.1 Grundprinzip

Die Medienproduktion soll zentral organisiert werden.

Alle sechs Redaktionsagenten greifen auf gemeinsame Produktionsdienste zurück.

Dadurch können Werkzeuge, Rechenressourcen und technische Prozesse gemeinsam genutzt werden.

9.2 Textproduktion

Die Textproduktion erfolgt über die OpenAI API.

Sie soll unter anderem ermöglichen:

* Rechercheunterstützung,
* Textentwürfe,
* redaktionelle Bearbeitung,
* Zusammenfassungen,
* Plattformadaptionen,
* Untertitel und Transkriptionen,
* sprachliche und inhaltliche Überprüfungen.

9.3 Bild- und Grafikproduktion

Für die Bild- und Grafikbearbeitung sind folgende Werkzeuge vorgesehen:

* Python Pillow,
* SVG,
* ImageMagick.

Sie sollen die Erstellung und Bearbeitung von Grafiken, Infografiken und weiteren visuellen Inhalten ermöglichen.

9.4 Videoproduktion

Für die Videoproduktion sind insbesondere vorgesehen:

* FFmpeg,
* Python,
* Whisper.

Damit sollen unter anderem folgende Aufgaben möglich sein:

* Videos schneiden,
* Formate und Seitenverhältnisse anpassen,
* Audio verarbeiten,
* Untertitel erzeugen,
* Transkriptionen erstellen,
* vorhandenes Videomaterial bearbeiten.

Vollständig KI-generierte Videos sind in der ersten Entwicklungsphase nicht vorgesehen.

Der Schwerpunkt liegt zunächst auf der Bearbeitung und Adaption vorhandenen Materials.

9.5 Audioproduktion

Audioinhalte sollen verarbeitet und für die redaktionelle Nutzung aufbereitet werden können.

Dazu gehören insbesondere Transkriptionen und Untertitel.

Die konkrete Audioproduktionsarchitektur ist noch festzulegen.

10. Medienarchiv und Inhaltsverwaltung

Das Netzwerk benötigt ein gemeinsames Medienarchiv.

Es soll Medienmaterial und veröffentlichte Inhalte nachvollziehbar verwalten.

Für veröffentlichte Inhalte sollen insbesondere gespeichert werden:

* Inhalt und Medien,
* zugehörige redaktionelle Identität,
* Plattform,
* Veröffentlichungszeitpunkt,
* Quellen,
* Urheber- und Rechteinformationen,
* ursprüngliche Veröffentlichung,
* spätere Korrekturen,
* verfügbare Leistungsdaten.

Das Archiv muss die Wiederverwendung bereits veröffentlichter Inhalte ermöglichen.

Dabei müssen Quellen und ursprüngliche Urheberschaft erhalten bleiben.

Unveröffentlichte Entwürfe werden nicht automatisch zentral gespeichert. Sie verbleiben grundsätzlich in den privaten redaktionellen Arbeitsbereichen.

Die konkrete technische Trennung zwischen Datenbank, Dateispeicher und Medienarchiv ist noch auszuarbeiten.

11. Plattformadapter

Jede Plattform wird über einen eigenen technischen Adapter angebunden.

Der Adapter übersetzt die zentralen Veröffentlichungs- und Interaktionsaufträge in die jeweils offiziell unterstützten Plattformfunktionen.

Die Adapter müssen insbesondere berücksichtigen:

* Authentifizierung,
* API-Berechtigungen,
* Veröffentlichungsfunktionen,
* Medienformate,
* Interaktionsmöglichkeiten,
* Leistungsdaten,
* Fehlerbehandlung,
* Plattformbeschränkungen.

Die Plattformadapter dürfen keine inoffiziellen Schnittstellen oder nicht autorisierten Workarounds verwenden.

Die technischen Details werden in den jeweiligen Plattformmodulen dokumentiert.

12. Aufgaben- und Nachrichtenverarbeitung

12.1 Zentrale Aufgabenverarbeitung

Das Netzwerk benötigt eine zentrale Aufgabenverarbeitung.

Sie soll Aufgaben zwischen Agenten, Produktionsdiensten und Plattformadaptern koordinieren.

Mögliche Aufgaben sind:

* Rechercheaufträge,
* Produktionsaufträge,
* Veröffentlichungsaufträge,
* Korrekturen,
* Medienverarbeitung,
* Benachrichtigungen,
* Statusmeldungen.

12.2 Dauerhafte Warteschlange

Für wichtige Aufgaben ist eine dauerhafte Warteschlange vorgesehen.

Sie soll verhindern, dass Aufträge bei einem vorübergehenden Ausfall verloren gehen.

Nach einer Wiederherstellung müssen offene Aufgaben kontrolliert weiterverarbeitet werden können.

12.3 Wiederholungsversuche

Fehlgeschlagene Aufgaben sollen nach definierten Regeln erneut versucht werden können.

Bei wiederholtem Scheitern wird der Koordinationsagent informiert.

Fehler und Wiederholungsversuche müssen protokolliert werden.

12.4 Schutz vor doppelter Ausführung

Die Aufgabenverarbeitung muss Idempotenz berücksichtigen.

Das bedeutet: Wird derselbe Auftrag erneut verarbeitet, darf dadurch nicht unkontrolliert eine doppelte Veröffentlichung oder eine andere doppelte Aktion entstehen.

Die konkrete technische Umsetzung ist noch festzulegen.

13. Schnittstellen und Kommunikation

Die Systemkomponenten kommunizieren über klar definierte Schnittstellen.

Die Architektur soll insbesondere eine Trennung ermöglichen zwischen:

* Agentenlogik,
* zentraler Anwendungslogik,
* Datenbank,
* Medienproduktion,
* Plattformadaptern,
* Aufgabenverarbeitung,
* administrativer Steuerung.

Die Schnittstellen müssen nachvollziehbar dokumentiert und gegen unberechtigte Zugriffe geschützt werden.

Konkrete API-Endpunkte, Datenformate und Kommunikationsprotokolle sind noch nicht abschließend festgelegt.

14. Überwachung und Protokollierung

Die technische Infrastruktur benötigt eine zentrale Überwachung.

Sie soll insbesondere folgende Zustände erfassen:

* Erreichbarkeit der Dienste,
* Agentenstatus,
* Aufgabenstatus,
* fehlgeschlagene Veröffentlichungen,
* API-Ausfälle,
* Datenbankprobleme,
* Warteschlangen,
* Ressourcenverbrauch,
* Budgetverbrauch,
* Sicherheitsereignisse.

Wichtige Systemaktionen müssen nachvollziehbar protokolliert werden.

Die vollständigen Anforderungen an Audit-Logs, Benachrichtigungen und administrative Überwachung werden im Betriebs-und-Sicherheitskonzept.md festgelegt.

15. Datensicherung und Wiederherstellung

Die Infrastruktur muss regelmäßige Datensicherungen unterstützen.

Dabei sind insbesondere zu berücksichtigen:

* Datenbank,
* Konfigurationen,
* Medienarchiv,
* relevante Protokolle,
* redaktionelle Inhalte,
* Systemdokumentation.

Die Sicherungen müssen gegen unbeabsichtigte Änderungen und unberechtigten Zugriff geschützt werden.

Die konkrete Backup-Strategie, Aufbewahrungsdauer und Wiederherstellungsziele sind noch festzulegen.

Eine Datensicherung gilt erst dann als verlässlich, wenn die Wiederherstellung praktisch getestet wurde.

16. Sicherheit technischer Zugangsdaten

Zugangsdaten und API-Tokens dürfen nicht öffentlich gespeichert werden.

Insbesondere gehören geheime Zugangsdaten nicht in:

* Git-Repositories,
* öffentliche Konfigurationsdateien,
* Handbücher,
* öffentlich zugängliche Logs.

Sie müssen sicher auf dem Server beziehungsweise in einem geeigneten Secret-Management-System gespeichert werden.

Zugriff erhalten nur die dafür vorgesehenen technischen Dienste.

Die Sicherheitsarchitektur und die Verfahren zur Erneuerung und Sperrung kompromittierter Zugangsdaten werden im Betriebs- und Sicherheitskonzept konkretisiert.

17. Budget und Ressourcen

Das geplante monatliche Gesamtbudget beträgt zunächst 40 Euro.

Die bisherige vorläufige Aufteilung lautet:

Bereich	Monatliches Budget
Cloudhosting und Backups	15 €
OpenAI API	20 €
Reserve	5 €
Gesamt	40 €

Diese Aufteilung ist ein Planungsansatz und keine Garantie, dass die vollständige Architektur damit betrieben werden kann.

Das Budget ist für das geplante Gesamtsystem sehr knapp.

Insbesondere Medienproduktion, parallele Agentenprozesse und umfangreiche KI-Recherche können die verfügbaren Ressourcen überschreiten.

17.1 Budgetgrenzen

Für den Betrieb sind folgende Schwellenwerte vorgesehen:

Verbrauch	Vorgesehene Reaktion
70 %	Warnung
90 %	Kritische Warnung und Einschränkung kostenintensiver Prozesse
100 %	Stopp neuer kostenintensiver Produktionsaufträge

Wartung, Datensicherung und sicherheitsrelevante Grundfunktionen sollen nach Möglichkeit weiterlaufen.

Die technische Umsetzung der Budgetüberwachung wird im Betriebs- und Sicherheitskonzept festgelegt.

18. Skalierbarkeit und Entwicklungsphasen

Die Architektur soll schrittweise umgesetzt werden.

Ein eingeschränkter Prototyp ist von einem vollständigen produktiven Netzwerk zu unterscheiden.

Die erste Entwicklungsphase sollte die zentralen technischen Grundlagen schaffen, bevor alle sieben Agenten und sämtliche Plattformen gleichzeitig produktiv betrieben werden.

Die genaue Reihenfolge der Implementierung muss im Entwicklungsstatus dokumentiert werden.

Eine Erweiterung des Systems darf nicht dazu führen, dass Sicherheits-, Rechte- oder Datenzugriffsregeln umgangen werden.

19. Offene technische Entscheidungen

Folgende Punkte sind noch nicht abschließend festgelegt:

* endgültige Serverregion,
* endgültige Serverdimensionierung,
* konkrete Aufteilung der Dienste,
* endgültige Auswahl und Konfiguration der Automatisierungswerkzeuge,
* Datenbankschema,
* Aufbau und Speicherort des Medienarchivs,
* konkrete Aufgabenwarteschlange,
* API- und Schnittstellendesign,
* Secret-Management,
* Backup- und Wiederherstellungsstrategie,
* technische Umsetzung der Agentenisolierung,
* Ressourcenplanung für parallele Prozesse,
* konkrete Implementierungsreihenfolge.

Diese Punkte müssen vor beziehungsweise während der Implementierung technisch geprüft und dokumentiert werden.

20. Aktueller Stand

Status: Technische Zielarchitektur konzeptionell beschrieben.

Bereits in der bisherigen Planung vorgesehen beziehungsweise festgelegt sind:

* gemeinsame Infrastruktur für sieben Agenten,
* sechs eigenständige Redaktionsagenten,
* ein zentraler Koordinationsagent,
* DigitalOcean als Hosting-Anbieter,
* ein monatliches Gesamtbudget von 40 Euro,
* PostgreSQL als vorgesehene zentrale Datenbank,
* n8n als vorgesehenes Automatisierungswerkzeug,
* Python als zentrale Programmiersprache,
* Docker als vorgesehene Containerlösung,
* zentrale Medienproduktion,
* FFmpeg, Whisper, Pillow, SVG und ImageMagick als vorgesehene Werkzeuge,
* OpenAI API für KI-gestützte Prozesse,
* gemeinsame Wissensbasis und Recherchearchiv,
* selektive gemeinsame und private Datenbereiche,
* dauerhafte Aufgabenverarbeitung,
* Wiederholungsversuche und Schutz vor doppelter Ausführung.

Die konkrete Implementierung ist noch nicht abgeschlossen.

Die genannten Werkzeuge und technischen Komponenten müssen vor ihrer endgültigen Einführung auf Kompatibilität, Kosten und tatsächliche Anforderungen geprüft werden.

21. Nächste Arbeitsschritte

1. Diese Datei als Technische-Architektur.md in Git übernehmen.
2. Anschließend das Betriebs-und-Sicherheitskonzept.md erstellen.
3. Danach den Entwicklungsstatus und die technische Umsetzungsreihenfolge dokumentieren.
4. Vor der Implementierung die offenen Architekturentscheidungen einzeln prüfen.
5. Die technische Umsetzung schrittweise und innerhalb des verfügbaren Budgets planen.

22. Änderungsprotokoll

Version	Datum	Änderung
1.0	04.11.2026	Erste eigenständige Fassung der technischen Architektur auf Basis des bisherigen Projektstands

Ende des Handbuchs
