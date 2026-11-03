Plattformmodul: Telegram

Version: 1.0
Stand: 04.11.2026
Status: Redaktionelles und technisches Konzept ausgearbeitet; Implementierung offen
Dateipfad: Plattformmodule/Telegram.md

⸻

1. Zweck dieses Moduls

Dieses Modul beschreibt die Telegram-Integration des Redaktionsnetzwerks.

Es dokumentiert:

* die Telegram-Kanal- und Botstruktur,
* die technische Gesamtarchitektur,
* die Rechte und Aufgaben der sechs Bots,
* Veröffentlichungen und Interaktionen,
* Moderation und Gruppenverwaltung,
* die Zusammenarbeit der sechs Redaktionen,
* die Verarbeitung und Archivierung von Inhalten,
* Datenschutz und Datenspeicherung,
* Fehlerbehandlung und Wiederherstellung,
* den Telegram-spezifischen Not-Aus.

Dieses Dokument ist eine eigenständige Übergabe- und Arbeitsgrundlage für die Telegram-Integration.

Die übergeordneten Netzwerkregeln bleiben verbindlich. Dieses Modul konkretisiert sie für Telegram.

2. Abhängigkeiten zu anderen Handbüchern

Handbuch	Relevanz
Projektgrundlage.md	Netzwerkstruktur, politische Grundlagen und gemeinsame Prinzipien
Redaktionshandbuch.md	Sechs Identitäten, redaktionelle Aufgaben und Koordination
Plattformhandbuch.md	Gemeinsame Plattform- und Interaktionsregeln
Technische-Architektur.md	Infrastruktur, Datenbank, Warteschlange und Medienarchiv
Betriebs-und-Sicherheitskonzept.md	Berechtigungen, Datenschutz, Überwachung und Not-Aus
Entwicklungsstatus.md	Implementierungsstand und offene technische Aufgaben

Dieses Modul darf keine übergeordneten Sicherheits- oder Netzwerkregeln eigenständig verändern.

3. Grundstruktur der Telegram-Präsenz

Jede der sechs redaktionellen Identitäten erhält eine eigene Telegram-Präsenz.

Die Struktur besteht aus:

* sechs öffentlichen Telegram-Kanälen,
* sechs jeweils zugehörigen Bots,
* sechs mit den Kanälen verknüpften öffentlichen Diskussionsgruppen.

Alle sechs Kanäle sind öffentlich und über die Telegram-Suche auffindbar.

Jeder Bot repräsentiert ausschließlich seine eigene redaktionelle Identität.

Die sechs Bots teilen sich die technische Infrastruktur, bleiben aber getrennte Identitäten.

3.1 Eigentümerschaft

Der Projektbetreiber bleibt Eigentümer der Kanäle und Gruppen.

Die Bots erhalten Administratorrechte, soweit diese für ihre Aufgaben erforderlich sind.

Die Bots dürfen keine weiteren Administratoren ernennen.

Die alleinige Kontrolle über die Eigentümerschaft und die Vergabe administrativer Rechte bleibt beim Projektbetreiber.

4. Technische Gesamtarchitektur

4.1 Gemeinsamer Telegram-Dienst

Die sechs Bots werden über einen gemeinsamen Telegram-Dienst betrieben.

Es wird kein eigener Server für jeden Bot benötigt.

Die gemeinsame Infrastruktur umfasst:

* einen zentralen Telegram-Dienst,
* sechs unterschiedliche Bot-Tokens,
* einen gemeinsamen Webhook-Dienst,
* eine dauerhafte Aufgabenwarteschlange,
* PostgreSQL,
* ein gemeinsames Medienarchiv,
* zentrale Protokollierung und Überwachung.

Die sechs Bots besitzen jeweils eigene Tokens und werden technisch eindeutig ihrer redaktionellen Identität zugeordnet.

4.2 Kommunikation

Die Kommunikation mit Telegram erfolgt ausschließlich über die offizielle Telegram Bot API.

Es werden keine inoffiziellen Clients oder nicht autorisierten technischen Workarounds verwendet.

4.3 Webhook-Architektur

Für alle sechs Bots wird die Webhook-Variante verwendet.

Die Architektur sieht einen gemeinsamen HTTPS-Endpunkt vor.

Der Dienst ordnet eingehende Updates anhand des jeweiligen Bots und Tokens der richtigen redaktionellen Identität zu.

Die Webhook-Verarbeitung muss abgesichert sein durch:

* HTTPS,
* ein geheimes Webhook-Token,
* dauerhafte Speicherung relevanter Aufgaben,
* Schutz vor doppelter Verarbeitung,
* Fehlerprotokollierung,
* Wiederholungsversuche,
* Überwachung des Dienstes.

Telegram hält nicht zugestellte Updates nur begrenzte Zeit vor. Die geplante Verarbeitung muss deshalb zuverlässig und zeitnah erfolgen.

5. Bot-Rechte und Aufgaben

Jeder Bot erhält nur die Rechte, die er für seinen eigenen Kanal und seine eigene Diskussionsgruppe benötigt.

Vorgesehen sind insbesondere:

* Beiträge veröffentlichen,
* eigene Beiträge bearbeiten,
* Beiträge löschen,
* Beiträge anheften,
* Kanalname und Beschreibung aktualisieren,
* Profilbild aktualisieren,
* Informations- und Begrüßungsbeiträge veröffentlichen,
* Mitgliedschafts- und Beitrittsanfragen verwalten, soweit technisch unterstützt,
* Reaktionen beobachten, sofern die erforderlichen Berechtigungen vorliegen,
* die eigene Diskussionsgruppe moderieren.

Die Bots dürfen keine weiteren Administratoren ernennen.

Sie erhalten keine Rechte zur Verwaltung fremder Kanäle oder Gruppen.

Die konkrete Rechtevergabe muss bei der technischen Einrichtung anhand der offiziellen Telegram-Funktionen geprüft werden.

6. Veröffentlichungen

6.1 Autonome Veröffentlichung

Die Bots veröffentlichen Inhalte entsprechend dem zentralen Redaktionskalender.

Die redaktionelle Entscheidung über Inhalt und Perspektive liegt bei der jeweiligen Redaktion.

Der Koordinationsagent übernimmt die organisatorische Abstimmung.

6.2 Zeitplanung

Die Telegram Bot API bietet keine allgemeine native Funktion zur zeitgesteuerten Veröffentlichung beliebiger Beiträge.

Die Zeitplanung erfolgt deshalb über das zentrale Redaktionssystem.

Dieses löst zum vorgesehenen Zeitpunkt den Veröffentlichungsauftrag aus.

6.3 Veröffentlichungsergebnis

Nach jeder Veröffentlichung übermittelt der Bot dem Koordinationsagenten die verfügbaren Informationen:

* Link zum Beitrag,
* Telegram-Nachrichten-ID,
* Veröffentlichungszeitpunkt,
* Veröffentlichungsstatus,
* verfügbare Leistungsdaten.

Nicht verfügbare Leistungsdaten werden als nicht verfügbar gekennzeichnet.

Es dürfen keine fehlenden Telegram-Statistiken geschätzt oder als tatsächliche Messwerte ausgegeben werden.

6.4 Fehlerbehandlung

Bei einer fehlgeschlagenen Veröffentlichung wird ein erneuter Versuch entsprechend den festgelegten Wiederholungsregeln unternommen.

Bei wiederholtem Scheitern wird der Koordinationsagent informiert.

Fehler und Wiederholungsversuche werden protokolliert.

Die technische Verarbeitung muss Idempotenz gewährleisten, damit ein erneut verarbeiteter Auftrag nicht unkontrolliert einen doppelten Beitrag erzeugt.

7. Interaktionen

7.1 Grundprinzip

Für alle sechs Telegram-Bots gilt das netzwerkweite Prinzip:

Keine menschliche Nachahmung in Interaktion.

Die Bots dürfen redaktionell argumentieren, Informationen bereitstellen, Quellen nennen und sachlich auf öffentliche Diskussionen reagieren.

Sie dürfen jedoch keine menschliche Identität oder persönliche menschliche Erfahrung vortäuschen.

7.2 Öffentliche Kommentare und Antworten

Die Bots dürfen in ihren eigenen Diskussionsgruppen und in anderen offiziell unterstützten öffentlichen Interaktionsbereichen reagieren.

Die Reaktionen müssen zum jeweiligen redaktionellen Profil passen.

Sie können beispielsweise enthalten:

* sachliche Informationen,
* Quellen und Hintergrundinformationen,
* Kontextualisierungen,
* Korrekturen,
* Gegenargumente.

Es gilt die netzwerkweite Begrenzung:

Maximal zwei eigene Antworten auf denselben externen Account unter demselben Beitrag.

Danach wird die Diskussion nicht weitergeführt.

7.3 Direktnachrichten

Für eingehende Direktnachrichten gilt die gemeinsame Netzwerkregel.

Der Bot antwortet ausschließlich mit:

„Vielen Dank für deine Nachricht! Dieser Account wird von einer KI verwaltet. Deine Nachricht wird an den Betreiber weitergeleitet. Er wird sich persönlich bei dir melden.“

Danach findet keine weitere automatische Unterhaltung statt.

Alle eingehenden Direktnachrichten werden an den Projektbetreiber weitergeleitet. Dieser erhält eine sofortige Benachrichtigung.

Ein Bot kann einem Nutzer grundsätzlich keine private Unterhaltung beginnen, solange dieser nicht zuvor den Bot gestartet oder anderweitig eine entsprechende Interaktion ermöglicht hat.

7.4 Öffentliche Fragen als Themenquelle

Öffentliche Fragen und Kommentare können neue redaktionelle Themen anregen.

Die Redaktion darf das Thema eigenständig recherchieren und aufgreifen.

Der ursprüngliche Kommentar darf nicht zitiert oder reproduziert werden, auch nicht in anonymisierter Form.

Die Identität und persönliche Daten der kommentierenden Person dürfen nicht offengelegt werden.

8. Diskussionsgruppen und Moderation

8.1 Verknüpfte Diskussionsgruppen

Jeder der sechs Telegram-Kanäle erhält eine eigene öffentliche Diskussionsgruppe.

Die jeweilige Gruppe ist mit dem dazugehörigen Kanal verknüpft.

Der zugehörige Bot übernimmt die Moderation seiner eigenen Gruppe.

8.2 Moderationsaufgaben

Die Bots dürfen innerhalb ihrer Gruppen autonom moderieren.

Dazu gehören insbesondere:

* Spam entfernen,
* offensichtliche Betrugsversuche entfernen,
* klar erkennbare Regelverstöße bearbeiten,
* relevante Moderationsereignisse protokollieren.

Ein gemeinsamer Inhaltsfilter soll für alle sechs Gruppen gelten.

Dieser soll insbesondere Beleidigungen und rechtswidrige Inhalte berücksichtigen.

Die genaue Definition und technische Umsetzung des Filters ist noch offen.

8.3 Umgang mit Grenzfällen

Bei eindeutigen Verstößen darf der Bot autonom handeln.

Bei unklaren oder grenzwertigen Fällen soll er:

* den Sachverhalt protokollieren,
* den Fall zur Prüfung weiterleiten,
* keine vorschnelle Sanktion verhängen.

8.4 Moderationsprotokoll

Moderationsaktionen müssen dokumentiert werden.

Mindestens erforderlich sind:

* Zeitpunkt,
* betroffene Gruppe,
* Art des Verstoßes,
* zugrunde liegender Grund,
* durchgeführte Maßnahme,
* ausführender Bot.

Personenbezogene Daten dürfen nur im erforderlichen Umfang gespeichert werden.

9. Themenbeobachtung und Koordination

9.1 Zuständigkeit des Koordinationsagenten

Der Koordinationsagent übernimmt die übergreifende Themenbeobachtung und Netzwerkkoordination.

Die sechs Telegram-Bots konzentrieren sich auf ihre eigenen Kanäle und Gruppen.

Sie führen keine eigenständige systematische Beobachtung fremder Telegram-Kanäle durch.

9.2 Aktivitätsdaten der eigenen Kanäle

Die Bots übermitteln relevante Aktivitätsinformationen ihrer eigenen Kanäle an den Koordinationsagenten.

Dazu können gehören:

* verfügbare Reaktionen,
* relevante öffentliche Diskussionen,
* besondere Entwicklungen,
* Auffälligkeiten,
* verfügbare Leistungsdaten.

Die Bots übermitteln zusammengefasste Informationen, soweit möglich ohne unnötige personenbezogene Daten.

9.3 Netzwerkweite Auswertung

Der Koordinationsagent führt die Informationen zusammen und übernimmt die netzwerkweite Auswertung.

Er kann daraus Themenvorschläge, Hinweise und Koordinationsmaßnahmen ableiten.

Die redaktionelle Entscheidung bleibt bei den jeweiligen Redaktionen.

10. Cross-Promotion und gemeinsame Inhalte

Die sechs Redaktionen dürfen auf Inhalte anderer Netzwerkidentitäten verweisen.

Verlinkungen sollen inhaltlich begründet sein und nicht automatisch unter jedem Beitrag erscheinen.

Bei einer Übernahme gelten die gemeinsamen Regeln:

* ursprüngliche Quelle erhalten,
* Urheberschaft berücksichtigen,
* Kontext nicht verfälschen,
* neue Tatsachenbehauptungen eigenständig überprüfen,
* eigene redaktionelle Perspektive entwickeln.

Unterschiedliche redaktionelle Perspektiven auf dasselbe Thema sind ausdrücklich erwünscht.

11. Umfragen und wiederkehrende Formate

Die Telegram-Bots dürfen eigenständig Umfragen in ihren eigenen Kanälen veröffentlichen.

Die Ergebnisse können für die redaktionelle Planung und Themenbeobachtung genutzt werden.

Umfrageergebnisse dürfen nicht als repräsentative Aussagen über die Gesamtbevölkerung ausgegeben werden.

Relevante Diskussionen und Erkenntnisse werden an den Koordinationsagenten weitergegeben.

Jede Redaktion darf außerdem eigene wiederkehrende Telegram-Formate entwickeln.

Diese Formate können in den zentralen Redaktionskalender aufgenommen werden.

12. Korrekturen und fehlerhafte Veröffentlichungen

Fehlerhafte Veröffentlichungen müssen transparent behandelt werden.

Wenn möglich, wird der bestehende Beitrag bearbeitet.

Falls eine ausreichende Korrektur auf diesem Weg nicht möglich ist, wird ein separater Korrekturbeitrag veröffentlicht.

Dabei werden dokumentiert:

* ursprünglicher Beitrag,
* Korrektur,
* Zeitpunkt,
* Grund der Korrektur,
* gegebenenfalls Entfernung oder Rücknahme.

12.1 Schwerwiegende Fehler

Bei schwerwiegenden Fehlern darf der ursprüngliche Beitrag vorübergehend sofort zurückgezogen werden.

Dafür ist keine vorherige Freigabe des Projektbetreibers erforderlich.

Der Koordinationsagent und der Projektbetreiber werden unmittelbar informiert.

Anschließend erfolgt eine transparente Korrektur.

Eine erneute Veröffentlichung erfolgt erst nach erneuter Prüfung.

13. Archivierung

Veröffentlichte Telegram-Inhalte werden im gemeinsamen Archiv gespeichert.

Dazu gehören:

* veröffentlichte Beiträge,
* zugehörige Medien,
* Veröffentlichungszeitpunkt,
* redaktionelle Identität,
* Quellen und Attributionen,
* Beitragslinks,
* Korrekturen und Versionshistorie,
* zurückgezogene Inhalte,
* verfügbare Leistungsdaten.

Veröffentlichte Inhalte können von anderen Redaktionen aufgegriffen werden.

Unveröffentlichte Entwürfe werden nicht automatisch zentral gespeichert. Sie verbleiben grundsätzlich in den privaten redaktionellen Arbeitsbereichen.

14. Fehlerbehandlung und Ausfallsicherheit

14.1 Dauerhafte Aufgabenverarbeitung

Veröffentlichungs- und andere wichtige Aufgaben müssen dauerhaft gespeichert werden.

Ein vorübergehender Ausfall darf nicht zum unkontrollierten Verlust von Aufträgen führen.

14.2 Wiederanlauf

Nach einer technischen Störung werden offene Aufgaben kontrolliert weiterverarbeitet.

Vor der Ausführung wird geprüft:

* ob die Aufgabe noch aktuell ist,
* ob sie bereits erfolgreich ausgeführt wurde,
* ob sie inzwischen überholt ist,
* ob eine doppelte Ausführung droht.

14.3 Wiederholungsversuche

Fehlgeschlagene Aufgaben werden nach definierten Regeln erneut versucht.

Bei wiederholtem Scheitern erfolgt eine Benachrichtigung des Koordinationsagenten.

Alle relevanten Vorgänge werden protokolliert.

15. Dringende Themen und parallele Ereignisse

15.1 Dringende Veröffentlichungen

Dringende Ereignisse können regulär geplante Veröffentlichungen zeitlich verdrängen.

Reguläre Beiträge sollen nach Möglichkeit verschoben und nicht einfach verworfen werden.

Änderungen werden im Kalender dokumentiert und betroffene Redaktionen informiert.

15.2 Gleichzeitige dringende Ereignisse

Bei mehreren gleichzeitigen dringenden Ereignissen priorisiert der Koordinationsagent anhand von Dringlichkeit und gesellschaftlicher Relevanz.

Mehrere Ereignisse können parallel bearbeitet und veröffentlicht werden, sofern keine inhaltlichen, organisatorischen oder technischen Konflikte entstehen.

Unterschiedliche Perspektiven auf dasselbe Ereignis sind kein Konflikt.

Eine Abstimmung ist insbesondere bei tatsächlichen Überschneidungen oder technischen Engpässen erforderlich.

16. Verarbeitungslast und Ressourcensteuerung

Die Telegram-Integration muss mit unterschiedlichen Arbeitslasten umgehen können.

Dafür gelten drei Verarbeitungsprioritäten:

Priorität	Beispiele	Verarbeitung
Normal	Reaktionen, gewöhnliche Kommentare und allgemeine Aktivität	Gebündelte Verarbeitung
Erhöht	Ungewöhnliche Diskussionen und steigendes Nachrichtenaufkommen	Bevorzugte Bearbeitung
Kritisch	Schwere Moderations-, Sicherheits- oder technische Vorfälle	Unmittelbare Bearbeitung

Normale Vorgänge können gebündelt verarbeitet werden.

KI-Verarbeitung soll insbesondere dann eingesetzt werden, wenn eine redaktionelle, inhaltliche oder moderative Bewertung erforderlich ist.

Wiederkehrende Ereignisse können zusammengefasst werden.

Bei hoher technischer Last dürfen normale Vorgänge verzögert werden.

Kritische Vorgänge behalten ihre Priorität.

Der Koordinationsagent überwacht die Ressourcen- und Budgetbelastung.

Konkrete numerische Schwellenwerte sind noch nicht festgelegt.

17. Hashtag-System

Die sechs Telegram-Kanäle verwenden ein gemeinsames Hashtag-System.

Es umfasst:

* netzwerkweite Hashtags,
* redaktionsspezifische Hashtags,
* situative Hashtags.

Die einzelnen Redaktionen dürfen eigene wiedererkennbare Hashtags entwickeln.

Der Koordinationsagent kann gemeinsame Hashtags für übergreifende Themen empfehlen.

Die Entscheidung über die Verwendung in einem konkreten Beitrag bleibt bei der jeweiligen Redaktion.

18. Telegram Bot API und technische Grenzen

18.1 Offizielle Schnittstelle

Die Integration verwendet ausschließlich die offizielle Telegram Bot API.

Die Authentifizierung erfolgt über die jeweiligen Bot-Tokens.

Die Kommunikation erfolgt über HTTPS.

18.2 Updates

Für die sechs Bots wird Webhook-Verarbeitung verwendet.

Webhook und Long Polling werden nicht gleichzeitig für denselben Bot eingesetzt.

Die relevanten Update-Typen umfassen insbesondere:

* neue Nachrichten in Diskussionsgruppen,
* Direktnachrichten,
* Beitrittsanfragen und Mitgliedschaftsänderungen,
* Reaktionen,
* neue Kanalbeiträge,
* Änderungen an Kanalbeiträgen,
* moderationsrelevante Ereignisse.

Die tatsächlich verfügbaren Update-Typen und erforderlichen Berechtigungen müssen bei der Implementierung anhand der aktuellen Bot API geprüft werden.

18.3 Reaktionen

Für die Beobachtung von Reaktionen auf eigenen Kanälen müssen die erforderlichen Bot-Rechte vorliegen.

Die entsprechenden allowed_updates müssen insbesondere message_reaction berücksichtigen.

18.4 Kommentare

Kommentare zu Kanalbeiträgen erfolgen über die verknüpfte Diskussionsgruppe.

Ein Bot muss dafür Mitglied der Gruppe sein und über die erforderlichen Rechte verfügen.

Eine allgemeine Kommentarfunktion unter beliebigen fremden öffentlichen Kanalbeiträgen wird durch die Bot API nicht bereitgestellt.

18.5 Externe Kanalbeobachtung

Die Bots überwachen keine fremden Telegram-Kanäle systematisch.

Diese Aufgabe liegt beim Koordinationsagenten und muss sich innerhalb der offiziell verfügbaren technischen Möglichkeiten bewegen.

18.6 Weitere Grenzen

Die Bot API unterstützt keine beliebigen allgemeinen Likes oder Follows wie bei manchen anderen sozialen Plattformen.

Die technische Umsetzung darf keine nicht vorhandenen Funktionen voraussetzen.

Nicht unterstützte Funktionen werden als technische Einschränkung dokumentiert.

19. Sicherheit der Bot-Tokens

Jeder Bot besitzt ein eigenes Token.

Die Tokens müssen:

* sicher gespeichert,
* verschlüsselt beziehungsweise angemessen geschützt,
* ausschließlich den vorgesehenen Diensten zugänglich gemacht,
* von Git und öffentlich zugänglichen Dokumenten ferngehalten werden.

Bei einer Kompromittierung muss das betroffene Token unabhängig von den übrigen Bots widerrufen und ersetzt werden können.

Der Vorfall wird protokolliert und löst eine kritische Benachrichtigung aus.

20. Datenschutz und Aufbewahrung

Es gelten die gemeinsamen Datenschutzregeln des Netzwerks.

20.1 Direktnachrichten

Direktnachrichten werden an den Projektbetreiber weitergeleitet und nicht mit den Redaktionsagenten geteilt.

20.2 Kommentare und Moderationsdaten

Personenbezogene Daten aus Kommentaren und Moderationsvorgängen werden grundsätzlich höchstens eine Woche gespeichert.

Danach werden sie automatisch gelöscht oder irreversibel anonymisiert.

Gesetzlich erforderliche Aufbewahrungspflichten können eine gesonderte Behandlung notwendig machen.

20.3 Veröffentlichte Inhalte

Veröffentlichte Inhalte und ihre redaktionelle Dokumentation werden im gemeinsamen Archiv aufbewahrt.

Unnötige personenbezogene Daten von Kommentierenden werden nicht dauerhaft übernommen.

21. Telegram-Not-Aus

21.1 Zweck und Geltungsbereich

Der Telegram-Not-Aus stoppt ausschließlich die sechs Telegram-Bots und die dazugehörigen Telegram-Automatisierungen.

Die übrigen Plattformen und ihre Agenten arbeiten weiter.

21.2 Gestoppte Funktionen

Der Telegram-Not-Aus stoppt:

* Veröffentlichungen,
* Kommentare und Antworten,
* Likes und sonstige Interaktionen,
* automatische Nachrichten,
* Moderationsautomatisierungen,
* geplante Veröffentlichungen,
* neue Produktionsaufträge für Telegram.

21.3 Erhaltene Daten und Konten

Folgende Elemente bleiben erhalten:

* Telegram-Kanäle,
* Diskussionsgruppen,
* Bot-Tokens,
* Archive,
* gespeicherte Daten,
* offene Aufgaben zur späteren Prüfung.

21.4 Aufhebung

Nur der Projektbetreiber darf den Telegram-Not-Aus aufheben.

Nach der Aufhebung prüft der Koordinationsagent:

* aufgelaufene Veröffentlichungen,
* Nachrichten,
* Moderationsaufgaben,
* Aktualität,
* mögliche Doppelveröffentlichungen,
* Konflikte mit zwischenzeitlichen Entwicklungen.

Überholte Aufgaben werden entfernt oder verschoben.

Danach erfolgt ein kontrollierter Neustart.

Die Aufhebung und der Wiederanlauf werden protokolliert.

22. Offene technische Entscheidungen

Folgende Punkte sind noch konkret auszuarbeiten:

* endgültige Rechtevergabe für jeden Bot,
* Einrichtung der sechs Kanäle und Diskussionsgruppen,
* endgültige Webhook-Konfiguration,
* Datenbankschema für Telegram-Updates und Veröffentlichungen,
* technische Umsetzung der dauerhaften Warteschlange,
* Idempotenz- und Wiederholungsmechanismen,
* konkrete Moderationsfilter und Grenzfallbehandlung,
* technische Verarbeitung von Direktnachrichten,
* konkrete Archivierungsstruktur,
* technische Lösch- und Anonymisierungsprozesse,
* Ressourcen- und Lastgrenzen,
* technische Umsetzung des Telegram-Not-Aus,
* Tests für Ausfall und kontrollierten Wiederanlauf.

Die jeweils aktuellen Anforderungen der Telegram Bot API müssen vor der Implementierung anhand der offiziellen Dokumentation geprüft werden.

23. Aktueller Stand

Status: Telegram-Konzept ausgearbeitet; technische Umsetzung offen.

Bereits konzeptionell festgelegt sind:

* sechs öffentliche Kanäle,
* sechs Bots,
* sechs verknüpfte öffentliche Diskussionsgruppen,
* Eigentümerschaft des Projektbetreibers,
* gemeinsame technische Infrastruktur,
* sechs individuelle Bot-Tokens,
* ein gemeinsamer Webhook-Dienst,
* zentrale Aufgabenverarbeitung,
* PostgreSQL und gemeinsames Medienarchiv,
* autonome Veröffentlichungen nach Redaktionskalender,
* Fehlerbehandlung und Schutz vor Doppelveröffentlichungen,
* öffentliche Interaktionen im Rahmen der offiziellen Bot API,
* keine menschliche Nachahmung,
* standardisierte DM-Antwort,
* autonome Moderation der eigenen Diskussionsgruppen,
* netzwerkweiter Inhaltsfilter als Ziel,
* zentrale Themenbeobachtung durch den Koordinationsagenten,
* Archivierung veröffentlichter Inhalte,
* Umfragen und wiederkehrende Formate,
* kontrollierte Wiederherstellung nach Ausfällen,
* drei Verarbeitungsprioritäten,
* gemeinsames Hashtag-System,
* Telegram-spezifischer Not-Aus,
* eine Woche Aufbewahrung personenbezogener Kommentar- und Moderationsdaten als Grundregel.

Die technische Implementierung ist noch nicht abgeschlossen.

24. Nächste Arbeitsschritte

1. Diese Datei als Plattformmodule/Telegram.md in Git übernehmen.
2. Die offenen technischen Entscheidungen anhand der aktuellen Telegram Bot API prüfen.
3. Die benötigten Bots, Kanäle und Gruppen organisatorisch vorbereiten.
4. Die gemeinsame Webhook- und Warteschlangenarchitektur entwerfen.
5. Die Telegram-Integration zunächst mit einem einzelnen Test-Bot erproben.
6. Nach erfolgreichem Test die übrigen fünf Bots integrieren.
7. Not-Aus, Fehlerbehandlung, Moderation und Wiederanlauf testen.

25. Änderungsprotokoll

Version	Datum	Änderung
1.0	04.11.2026	Erste eigenständige Fassung des Telegram-Plattformmoduls auf Basis des bisherigen Projektstands

Ende des Plattformmoduls
