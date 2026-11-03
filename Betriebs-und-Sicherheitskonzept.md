Betriebs- und Sicherheitskonzept

Version: 1.0
Stand: 04.11.2026
Status: Erstfassung
Dateiname: Betriebs-und-Sicherheitskonzept.md

⸻

1. Zweck dieses Handbuchs

Dieses Handbuch beschreibt die organisatorischen und technischen Anforderungen an den sicheren Betrieb des Redaktionsnetzwerks.

Es regelt insbesondere:

* administrative Zuständigkeiten und Berechtigungen,
* Autonomie und menschliche Freigaben,
* Risikobewertung redaktioneller Inhalte,
* Dashboard und zentrale Steuerung,
* Redaktionskalender und Aufgabenüberwachung,
* Benachrichtigungen und Berichte,
* Protokollierung und Nachvollziehbarkeit,
* Datenschutz und Datenaufbewahrung,
* Sicherheitsmaßnahmen,
* Not-Aus und Wiederherstellung.

Das Handbuch ist eine eigenständige Übergabe- und Arbeitsgrundlage.

Es beschreibt den vorgesehenen Betrieb. Die tatsächliche technische Umsetzung der Funktionen muss im Entwicklungsverlauf erfolgen und überprüft werden.

2. Abhängigkeiten zu anderen Handbüchern

Handbuch	Relevanz
Projektgrundlage.md	Projektstruktur, Grundprinzipien und administrative Hierarchie
Redaktionshandbuch.md	Redaktionelle Aufgaben, Autonomie und Zuständigkeiten
Plattformhandbuch.md	Gemeinsame Plattformregeln und Interaktionen
Technische-Architektur.md	Infrastruktur, Datenbank, Schnittstellen und technische Dienste
Plattformmodule	Plattformbezogene Sicherheits- und Not-Aus-Regeln
Entwicklungsstatus.md	Umsetzungsstand und offene technische Aufgaben

Dieses Handbuch regelt den Betrieb und die Sicherheit des Gesamtnetzwerks. Plattformmodule können zusätzliche plattformspezifische Sicherheitsmaßnahmen festlegen, dürfen aber die netzwerkweiten Sicherheitsgrenzen nicht eigenmächtig lockern.

3. Administrative Hierarchie

3.1 Projektbetreiber

Der Projektbetreiber besitzt die alleinigen uneingeschränkten administrativen Rechte.

Er kann insbesondere:

* Agenten starten und stoppen,
* einzelne Agenten pausieren,
* das gesamte Netzwerk pausieren,
* Berechtigungen verändern,
* Autonomiegrenzen festlegen,
* Freigaben erteilen oder verweigern,
* Sicherheitsfunktionen aktivieren,
* den Not-Aus auslösen und aufheben,
* technische und organisatorische Einstellungen ändern,
* die Beendigung des gesamten Projekts veranlassen.

3.2 Koordinationsagent

Der Koordinationsagent besitzt zentrale organisatorische und koordinierende Aufgaben.

Er darf innerhalb der vom Projektbetreiber vorgegebenen Grenzen Einstellungen und Abläufe koordinieren.

Er darf jedoch nicht:

* seine eigenen Sicherheitsgrenzen aufheben,
* Sicherheitsbeschränkungen eigenständig lockern,
* dem Projektbetreiber vorbehaltene administrative Rechte übernehmen,
* die alleinige Entscheidungsbefugnis des Projektbetreibers umgehen.

3.3 Redaktionsagenten

Die sechs Redaktionsagenten besitzen keine administrativen Rechte über das Gesamtsystem.

Sie dürfen innerhalb ihrer jeweiligen Zuständigkeiten redaktionell arbeiten und die ihnen freigegebenen Funktionen verwenden.

Sie dürfen keine Sicherheitsgrenzen, Berechtigungsmodelle oder zentralen Systemeinstellungen verändern.

4. Autonomie und menschliche Freigaben

4.1 Grundprinzip

Die Redaktionsagenten sollen möglichst autonom arbeiten können.

Die Autonomie ist jedoch an verbindliche redaktionelle, rechtliche und sicherheitstechnische Grenzen gebunden.

4.2 Routineinhalte

Routineinhalte dürfen innerhalb der festgelegten Regeln autonom:

* recherchiert,
* erstellt,
* geprüft,
* für Plattformen adaptiert,
* veröffentlicht werden.

Voraussetzung ist, dass Tatsachen, Quellen und Nutzungsrechte ausreichend geklärt sind.

4.3 Sensible und kontroverse Inhalte

Sensible oder kontroverse Inhalte benötigen eine menschliche Freigabe.

Dazu gehören Inhalte, bei denen eine erhöhte Gefahr von Fehlinterpretationen, rechtlichen Problemen oder gesellschaftlich erheblichen Folgen besteht.

Die konkrete Zuordnung zu Risikostufen ist noch festzulegen.

4.4 Risikoreiche Inhalte

Risikoreiche Inhalte benötigen die ausdrückliche Freigabe des Projektbetreibers.

Die Agenten dürfen solche Inhalte nicht eigenständig veröffentlichen.

4.5 Unklare Tatsachen und Rechte

Unklare Tatsachenbehauptungen oder ungeklärte Nutzungsrechte verhindern eine Veröffentlichung.

Die Agenten müssen Unsicherheiten dokumentieren und dürfen fehlende Informationen nicht durch unbelegte Annahmen ersetzen.

4.6 Grenzen autonomer Entscheidungen

Die Agenten dürfen keine Sicherheitsgrenzen eigenständig erweitern.

Eine vom Projektbetreiber festgelegte Beschränkung kann nicht durch eine redaktionelle Entscheidung aufgehoben werden.

5. Risikobewertung

Vor einer Veröffentlichung muss eine angemessene Risikoprüfung stattfinden.

Zu berücksichtigen sind insbesondere:

* Richtigkeit der Tatsachenbehauptungen,
* Zuverlässigkeit der Quellen,
* Rechte und Genehmigungen,
* rechtliche Risiken,
* sensible personenbezogene Informationen,
* mögliche Gefährdung von Personen,
* irreführende oder missverständliche Darstellungen,
* Einhaltung der Plattformregeln,
* mögliche Auswirkungen einer Veröffentlichung.

5.1 Risikostufen

Die konkrete Risikoklassifizierung ist noch nicht abschließend definiert.

Bereits festgelegt ist die grundsätzliche Freigabelogik:

Kategorie	Erforderliche Behandlung
Routineinhalt	Autonome Bearbeitung und Veröffentlichung innerhalb der Regeln
Sensibler oder kontroverser Inhalt	Menschliche Freigabe
Risikoreicher Inhalt	Ausdrückliche Freigabe des Projektbetreibers
Unklare Tatsachen oder ungeklärte Rechte	Keine Veröffentlichung bis zur Klärung

Die endgültigen Kriterien und technischen Prüfmechanismen müssen noch ausgearbeitet werden.

6. Dashboard und zentrale Steuerung

6.1 Grundaufbau

Das Netzwerk erhält ein zentrales Dashboard zur Überwachung und Steuerung.

Es soll sieben Agenten darstellen:

* sechs Redaktionsagenten,
* einen Koordinationsagenten.

Für jeden Agenten soll eine eigene Statusübersicht vorhanden sein.

6.2 Agentenstatus

Das Dashboard soll mindestens folgende Informationen anzeigen:

* aktueller Status,
* laufende Aufgaben,
* offene Aufgaben,
* abgeschlossene Aufgaben,
* Probleme und Fehler,
* Veröffentlichungen,
* relevante Benachrichtigungen,
* aktuelle Experimente.

Die konkreten Statuswerte und ihre technische Definition sind noch festzulegen.

6.3 Steuerungsmöglichkeiten

Der Projektbetreiber soll über das Dashboard:

* einzelne Agenten pausieren und fortsetzen können,
* alle sechs Redaktionsagenten gemeinsam pausieren können,
* das gesamte Netzwerk einschließlich Koordinationsagenten stoppen können,
* einzelne Funktionen deaktivieren können,
* Autonomiegrenzen verändern können.

Bei einer Pause muss der bisherige Arbeitsstand erhalten bleiben.

Eine Pause darf nicht dazu führen, dass laufende Aufgaben, Daten oder redaktionelle Entwürfe unkontrolliert verloren gehen.

6.4 Rechte

Uneingeschränkte administrative Steuerungsmöglichkeiten stehen ausschließlich dem Projektbetreiber zur Verfügung.

Der Koordinationsagent kann innerhalb seiner festgelegten Grenzen organisatorische Einstellungen und Abläufe koordinieren.

Die Redaktionsagenten besitzen keine administrativen Dashboardrechte.

7. Redaktionskalender

Der Koordinationsagent verwaltet einen zentralen Redaktionskalender.

Dieser enthält insbesondere:

* vorgeschlagene Themen,
* angenommene Themen,
* Recherche- und Produktionsaufgaben,
* geplante Veröffentlichungen,
* tatsächliche Veröffentlichungen,
* zuständige Redaktion,
* betroffene Plattform,
* Veröffentlichungszeitpunkt,
* gemeinsame Themen,
* Verschiebungen,
* Absagen.

Der Koordinationsagent darf Veröffentlichungszeitpunkte anhand von Ereignissen, Trends, Leistungsdaten und der Aktivität anderer Redaktionen optimieren.

Änderungen müssen nachvollziehbar dokumentiert werden.

Dringende Ereignisse können regulär geplante Veröffentlichungen verdrängen. Verschobene Beiträge sollen nach Möglichkeit erhalten bleiben und später eingeplant werden.

8. Chatsteuerung über den Koordinationsagenten

Der Projektbetreiber soll das Netzwerk über einen Chat mit dem Koordinationsagenten steuern können.

Der Projektbetreiber kann dort beispielsweise:

* Themen vorgeben,
* redaktionelle Parameter verändern,
* neue Aufgaben erteilen,
* Prioritäten festlegen,
* Veröffentlichungen anpassen,
* Agenten oder Funktionen pausieren,
* Statusinformationen anfordern.

8.1 Verarbeitung von Anweisungen

Der Koordinationsagent interpretiert die Anweisung und ermittelt, welche Redaktionen betroffen sind.

Anschließend übersetzt er die Anweisung in konkrete Arbeitsaufträge.

Dabei muss er die ursprüngliche Bedeutung erhalten.

Unklare oder widersprüchliche Anweisungen müssen vor der Umsetzung geklärt werden.

8.2 Transparenz bei Änderungen

Nach einer Parameteränderung soll der Koordinationsagent anzeigen:

1. ursprüngliche Anweisung des Projektbetreibers,
2. betroffene Redaktionsagenten,
3. daraus abgeleitete Arbeitsanweisungen,
4. tatsächlich geänderte Einstellungen,
5. erwarteter Umfang der Änderung.

Der Projektbetreiber muss nachvollziehen können, wie seine Anweisung umgesetzt wurde.

9. Protokollierung und Audit-Log

Alle relevanten Aktionen müssen nachvollziehbar protokolliert werden.

Das Audit-Log soll mindestens enthalten:

* Zeitstempel,
* ausführenden Agenten oder Benutzer,
* ausgeführte Aktion,
* betroffenes Thema oder Projekt,
* verwendete Quellen, soweit relevant,
* Ergebnis,
* erforderliche Freigabe,
* Risikobewertung,
* technische Fehler,
* administrative Änderungen.

Auch Änderungen durch den Projektbetreiber müssen protokolliert werden.

Die Protokollierung dient insbesondere:

* der Nachvollziehbarkeit,
* der Fehleranalyse,
* der Sicherheitskontrolle,
* der Überprüfung autonomer Entscheidungen,
* der Rekonstruktion von Veröffentlichungen und Änderungen.

Die technische Umsetzung und die Aufbewahrungsfristen der Protokolle sind noch festzulegen.

10. Berichte und Benachrichtigungen

10.1 Regelmäßige Berichte

Das Netzwerk soll regelmäßige Berichte bereitstellen.

Vorgesehen sind:

* tägliche Berichte,
* wöchentliche Berichte,
* monatliche Berichte.

Die Berichte sollen unter anderem enthalten:

* Veröffentlichungen,
* relevante Themen und Entwicklungen,
* Arbeitsfortschritt,
* offene Aufgaben,
* Probleme,
* Leistungsentwicklungen,
* Experimente und deren Ergebnisse,
* Ressourcen- und Budgetverbrauch.

Der Projektbetreiber kann jederzeit einen aktuellen Status über den Koordinationsagenten anfordern.

10.2 Kritische Ereignisse

Bei kritischen Ereignissen muss eine sofortige Benachrichtigung erfolgen.

Dazu gehören insbesondere:

* Ausfall eines Agenten,
* fehlgeschlagene Veröffentlichung,
* ungewöhnlicher Reichweitenabfall,
* kritischer Budgetverbrauch,
* Sicherheitsvorfall,
* ungelöste Fakten- oder Rechteprobleme,
* Ausfall einer Plattformanbindung,
* Fehler in einer Automatisierung.

10.3 Dringlichkeitsstufen

Es gelten drei Benachrichtigungsstufen:

Stufe	Bedeutung	Reaktion
Information	Normale Statusmeldung	Anzeige im Dashboard
Warnung	Erhöhte Aufmerksamkeit erforderlich	Push-Benachrichtigung
Kritisch	Unmittelbarer Handlungsbedarf	Sofortige Push-Benachrichtigung und gegebenenfalls automatische Einschränkung

Die Push-Benachrichtigungen sollen auf iPhone und iPad zugestellt werden.

E-Mail-Benachrichtigungen sind nicht vorgesehen.

Die genauen technischen Schwellenwerte und Auslöser sind noch zu definieren.

11. Datenschutz und Datenverwaltung

11.1 Grundprinzip

Das Netzwerk speichert personenbezogene Daten nur, soweit sie für redaktionelle Analyse, Moderation, Sicherheit oder technische Nachvollziehbarkeit erforderlich sind.

Es sollen keine unnötigen personenbezogenen Daten gesammelt oder dauerhaft gespeichert werden.

11.2 Direktnachrichten

Eingehende Direktnachrichten werden an den Projektbetreiber weitergeleitet.

Sie werden nicht mit den Redaktionsagenten geteilt.

Die Agenten führen keine automatisierten persönlichen Gespräche fort.

11.3 Kommentare und Moderationsdaten

Personenbezogene Daten aus Kommentaren und Moderationsvorgängen sollen grundsätzlich eine Woche gespeichert werden.

Danach werden sie automatisch gelöscht oder irreversibel anonymisiert.

Gesetzlich erforderliche Aufbewahrungspflichten können eine gesonderte Behandlung notwendig machen.

Die Ein-Wochen-Regel hebt solche Pflichten nicht auf.

11.4 Veröffentlichte Inhalte

Veröffentlichte Inhalte werden im gemeinsamen Archiv gespeichert.

Dazu gehören insbesondere:

* veröffentlichte Texte,
* Medien,
* Veröffentlichungszeitpunkte,
* Quellen und Rechteinformationen,
* Korrekturen,
* Versionshistorien,
* gegebenenfalls zurückgezogene Inhalte.

Personenbezogene Informationen von Kommentierenden sollen dabei nicht unnötig übernommen werden.

11.5 Zugriffsrechte

Die Datenzugriffe richten sich nach dem Modell shared_selective.

Gemeinsame Wissensbestände und veröffentlichte Inhalte sind entsprechend ihrer Zweckbestimmung zugänglich.

Private redaktionelle Notizen und unveröffentlichte Arbeitsstände bleiben grundsätzlich im jeweiligen redaktionellen Bereich.

Die Zugriffsbeschränkungen müssen technisch durchgesetzt werden.

12. Sicherheitsarchitektur

12.1 Zugangsdaten

API-Tokens, Passwörter und andere vertrauliche Zugangsdaten dürfen nicht in Git-Repositories, Handbüchern oder öffentlich zugänglichen Konfigurationsdateien gespeichert werden.

Sie müssen sicher aufbewahrt werden.

Der Zugriff darf nur den dafür vorgesehenen technischen Diensten gestattet werden.

12.2 Berechtigungsbegrenzung

Jeder Agent und jede technische Komponente erhält nur die Rechte, die für ihre Aufgaben erforderlich sind.

Die Redaktionsagenten dürfen keine administrativen Rechte des Projektbetreibers übernehmen.

12.3 Sicherheitsvorfälle

Bei einem Sicherheitsvorfall müssen die betroffenen Komponenten kontrolliert eingeschränkt werden können.

Kompromittierte Zugangsdaten müssen gesperrt beziehungsweise ersetzt werden können.

Sicherheitsrelevante Ereignisse müssen protokolliert und dem Projektbetreiber unverzüglich gemeldet werden.

12.4 Schutz der Sicherheitsgrenzen

Der Koordinationsagent darf Sicherheitsregeln nicht eigenständig lockern.

Auch bei hohem Arbeitsaufkommen, dringenden Ereignissen oder technischen Problemen bleiben die festgelegten Sicherheitsgrenzen verbindlich.

13. Not-Aus-System

Das Netzwerk erhält zwei übergeordnete Not-Aus-Stufen.

13.1 Not-Aus 1: Gesamtnetzwerk anhalten

Not-Aus 1 stoppt sämtliche sieben Agenten und alle Aktivitäten des Netzwerks.

Gestoppt werden insbesondere:

* Veröffentlichungen,
* Kommentare und Antworten,
* Likes und Shares,
* Follows und sonstige automatisierte Interaktionen,
* automatische Nachrichten,
* geplante Veröffentlichungen,
* neue Produktionsaufträge,
* laufende Automatisierungen.

Die vorhandenen Daten, Konten und Projektinformationen bleiben erhalten.

Der Zweck dieser Stufe ist eine vollständige Betriebspause, ohne das Projekt zu beenden.

13.2 Not-Aus 2: Gesamtes Projekt beenden

Not-Aus 2 leitet die Beendigung des gesamten Projekts ein.

Vorgesehen sind:

1. Alle Agenten stoppen.
2. Alle Automatisierungen stoppen.
3. Geplante Veröffentlichungen stoppen.
4. Die sechs Social-Media-Konten zur Deaktivierung beziehungsweise Löschung vormerken.
5. API-Zugriffe und Zugangsdaten widerrufen.
6. Den Server herunterfahren.
7. Projektdaten zunächst erhalten.

Es gilt eine Wiederherstellungsfrist von 14 Tagen.

Nach Ablauf dieser Frist darf eine endgültige Löschung von Konten, Servern und Daten erst nach einer ausdrücklichen Bestätigung des Projektbetreibers erfolgen.

Die tatsächliche Löschung von Plattformkonten hängt von den Möglichkeiten und Regeln der jeweiligen Plattform ab.

Die technische Umsetzung dieser Stufe ist noch zu entwickeln. Das Konzept allein bewirkt keine automatische Löschung.

14. Wiederanlauf nach einer Betriebspause

Nach Aufhebung von Not-Aus 1 darf das Netzwerk nicht unkontrolliert sämtliche aufgelaufenen Aufgaben ausführen.

Vor dem Wiederanlauf müssen offene Aufgaben und Veröffentlichungen geprüft werden.

Dabei ist insbesondere zu berücksichtigen:

* Ist das Thema noch aktuell?
* Ist eine Veröffentlichung inzwischen überholt?
* Besteht die Gefahr einer doppelten Veröffentlichung?
* Sind neue Informationen hinzugekommen?
* Sind Aufgaben miteinander in Konflikt geraten?
* Müssen Veröffentlichungen verschoben oder verworfen werden?

Der Koordinationsagent führt diese Prüfung durch und dokumentiert die Ergebnisse.

Anschließend erfolgt ein kontrollierter Neustart.

Die Aufhebung des Not-Aus und der Wiederanlauf bleiben dem Projektbetreiber vorbehalten.

15. Telegram-spezifischer Not-Aus

Zusätzlich zum netzwerkweiten Not-Aus existiert ein eigener Telegram-Not-Aus.

Dieser betrifft ausschließlich die sechs Telegram-Bots und die dazugehörigen Telegram-Automatisierungen.

Er stoppt:

* Telegram-Veröffentlichungen,
* Telegram-Kommentare und Antworten,
* Telegram-Interaktionen,
* automatische Telegram-Nachrichten,
* Telegram-Moderationsautomatisierungen,
* geplante Telegram-Veröffentlichungen,
* neue Telegram-Produktionsaufträge.

Die übrigen Plattformen und ihre Agenten arbeiten weiter.

Telegram-Kanäle, Gruppen, Tokens, Archive und Daten bleiben erhalten.

Nur der Projektbetreiber darf diesen Not-Aus aufheben.

Vor dem Wiederanlauf prüft der Koordinationsagent aufgelaufene Veröffentlichungen, Nachrichten und Moderationsaufgaben auf Aktualität und mögliche Konflikte.

Der Neustart wird dokumentiert.

Weitere plattformspezifische Not-Aus-Regeln können in anderen Plattformmodulen festgelegt werden.

16. Ressourcen- und Budgetüberwachung

Das monatliche Gesamtbudget beträgt zunächst 40 Euro.

Die vorläufige Aufteilung lautet:

Bereich	Monatliches Budget
Hosting und Backups	15 €
OpenAI API	20 €
Reserve	5 €
Gesamt	40 €

Die Budgetüberwachung verwendet folgende Schwellenwerte:

Verbrauch	Reaktion
70 %	Warnung
90 %	Kritische Warnung und Einschränkung kostenintensiver Prozesse
100 %	Stopp neuer kostenintensiver Produktionsaufträge

Wartung, Datensicherung und sicherheitsrelevante Grundfunktionen sollen nach Möglichkeit weiterlaufen.

Die tatsächliche Ressourcenverteilung und technische Umsetzung der Budgetgrenzen sind noch festzulegen.

17. Betriebsausfälle und Wiederherstellung

Das System muss auf vorübergehende Ausfälle vorbereitet sein.

Wichtige Aufgaben sollen dauerhaft gespeichert werden, damit sie nach einer Störung kontrolliert weiterverarbeitet werden können.

Dabei gelten folgende Anforderungen:

* Aufgaben dürfen bei einem vorübergehenden Ausfall nicht unkontrolliert verloren gehen.
* Wiederholungsversuche müssen protokolliert werden.
* Doppelte Ausführungen müssen verhindert werden.
* Wiederhergestellte Dienste müssen kontrolliert anlaufen.
* Der Koordinationsagent muss wiederhergestellte Aufgaben auf Aktualität prüfen.
* Kritische Ausfälle müssen dem Projektbetreiber gemeldet werden.

Die konkreten Wiederherstellungsziele, Backup-Intervalle und technischen Verfahren sind noch offen.

18. Offene Sicherheits- und Betriebsentscheidungen

Folgende Punkte sind noch nicht abschließend definiert:

* genaue Risikokriterien und Risikostufen,
* konkrete Freigabeoberfläche,
* technische Rechte- und Rollenmatrix,
* Dashboard-Statuswerte,
* technische Umsetzung der Push-Benachrichtigungen,
* konkrete Audit-Log-Aufbewahrungsfristen,
* technische Lösch- und Anonymisierungsverfahren,
* Backup-Intervalle und Wiederherstellungsziele,
* konkrete Umsetzung von Not-Aus 1 und Not-Aus 2,
* technische Prüfung und Wiederanlauf nach einem Not-Aus,
* Sicherheitsüberwachung und Alarmierung,
* konkrete Budgetkontrolle.

Diese Punkte müssen vor beziehungsweise während der Implementierung einzeln ausgearbeitet werden.

19. Aktueller Stand

Status: Betriebs- und Sicherheitsregeln konzeptionell beschrieben.

Bereits festgelegt sind:

* alleinige uneingeschränkte Adminrechte des Projektbetreibers,
* begrenzte Rechte des Koordinationsagenten,
* keine administrativen Rechte für Redaktionsagenten,
* autonome Routinearbeit innerhalb festgelegter Grenzen,
* menschliche Freigabe sensibler und kontroverser Inhalte,
* ausdrückliche Freigabe des Projektbetreibers für risikoreiche Inhalte,
* keine Veröffentlichung bei ungeklärten Tatsachen oder Rechten,
* zentrales Dashboard mit sieben Agenten,
* individuelle und gemeinsame Pausenfunktionen,
* Erhalt des Arbeitsstands bei einer Pause,
* zentraler Redaktionskalender,
* Chatsteuerung über den Koordinationsagenten,
* nachvollziehbare Darstellung von Parameteränderungen,
* vollständiges Audit-Log relevanter Aktionen,
* tägliche, wöchentliche und monatliche Berichte,
* drei Benachrichtigungsstufen,
* Push-Benachrichtigungen auf iPhone und iPad,
* keine E-Mail-Benachrichtigungen,
* selektive Datenfreigabe,
* eine Woche Aufbewahrung personenbezogener Kommentar- und Moderationsdaten als Grundregel,
* zwei übergeordnete Not-Aus-Stufen,
* eigenständiger Telegram-Not-Aus,
* kontrollierter Wiederanlauf,
* Budgetüberwachung mit 70-, 90- und 100-Prozent-Schwellen.

Die technische Umsetzung ist noch nicht abgeschlossen.

20. Nächste Arbeitsschritte

1. Diese Datei als Betriebs-und-Sicherheitskonzept.md in Git übernehmen.
2. Anschließend die Plattformmodule einzeln erstellen beziehungsweise vervollständigen.
3. Danach den Entwicklungsstatus.md erstellen.
4. Die offenen Sicherheitsentscheidungen vor der Implementierung konkretisieren.
5. Not-Aus, Berechtigungen, Freigaben und Wiederherstellung technisch testen, bevor das Netzwerk produktiv arbeitet.

21. Änderungsprotokoll

Version	Datum	Änderung
1.0	04.11.2026	Erste eigenständige Fassung des Betriebs- und Sicherheitskonzepts auf Basis des bisherigen Projektstands

Ende des Handbuchs
