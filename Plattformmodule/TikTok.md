Plattformmodul: TikTok

Version: 1.0
Stand: 04.11.2026
Status: Grundkonzept; plattformspezifische Ausarbeitung und technische Prüfung offen
Dateipfad: Plattformmodule/TikTok.md

⸻

1. Zweck dieses Moduls

Dieses Modul beschreibt die geplante Integration von TikTok in das Redaktionsnetzwerk.

Es dokumentiert:

* die vorgesehene TikTok-Präsenz der sechs redaktionellen Identitäten,
* die redaktionelle Nutzung der Plattform,
* die Anforderungen an Videoformate und Veröffentlichungen,
* die plattformbezogenen Interaktionsregeln,
* die technische Anbindung,
* die verfügbaren Analyse- und Leistungsdaten,
* Datenschutz und Sicherheit,
* offene technische und organisatorische Entscheidungen.

Dieses Dokument ist eine eigenständige Übergabe- und Arbeitsgrundlage.

Es beschreibt den bisherigen Planungsstand. Nicht abschließend geprüfte Funktionen oder technische Möglichkeiten werden ausdrücklich als offen gekennzeichnet.

2. Abhängigkeiten zu anderen Handbüchern

Handbuch	Relevanz
Projektgrundlage.md	Projektziele, politische Grundlagen und Netzwerkstruktur
Redaktionshandbuch.md	Sechs Identitäten und redaktionelle Zuständigkeiten
Plattformhandbuch.md	Gemeinsame Regeln für Plattformen und Interaktionen
Technische-Architektur.md	Infrastruktur, Medienproduktion und Schnittstellen
Betriebs-und-Sicherheitskonzept.md	Berechtigungen, Freigaben, Datenschutz und Not-Aus
Entwicklungsstatus.md	Implementierungsstand und offene Entscheidungen

Die gemeinsamen Netzwerkregeln gelten auch für TikTok. Dieses Modul konkretisiert sie, sobald die plattformspezifischen Anforderungen geprüft und festgelegt sind.

3. Grundstruktur der TikTok-Präsenz

Das Netzwerk besitzt sechs eigenständige redaktionelle Identitäten.

Die geplante TikTok-Präsenz soll diese Identitäten getrennt abbilden.

Damit sind grundsätzlich sechs redaktionelle TikTok-Auftritte vorgesehen:

1. Bewegungsmedium
2. Protestmedium
3. Aktivistische Community
4. Satiremedium
5. Jugendkulturmedium
6. Dokumentation & Trends

Jeder Auftritt repräsentiert ausschließlich die jeweilige redaktionelle Identität.

Die genaue Einrichtung der Accounts, ihre Namen und ihre organisatorische Verwaltung sind noch festzulegen.

4. Redaktionelle Nutzung

TikTok wird als Veröffentlichungs- und Kommunikationsplattform genutzt.

Die redaktionelle Grundlage eines Inhalts entsteht unabhängig von TikTok. Anschließend wird entschieden, ob und in welcher Form eine Veröffentlichung auf der Plattform sinnvoll ist.

Nicht jeder redaktionelle Inhalt muss auf TikTok erscheinen.

Die Inhalte müssen zum jeweiligen redaktionellen Profil passen.

4.1 Bewegungsmedium

Mögliche TikTok-Formate:

* kurze dokumentarische Videos,
* Porträts von Initiativen und Bewegungen,
* Ausschnitte aus Reportagen,
* Hintergrundinformationen zu sozialen Bewegungen,
* visuelle Dokumentationen von Veranstaltungen.

Authentisches Material und die Perspektiven der Beteiligten stehen im Mittelpunkt.

4.2 Protestmedium

Mögliche TikTok-Formate:

* aktuelle Protestdokumentationen,
* kurze Demonstrationsberichte,
* dokumentarische Ereigniszusammenfassungen,
* Informationen zu Protesten und gesellschaftlichen Konflikten,
* visuelle Einordnung aktueller Ereignisse.

Die unmittelbare Dokumentation steht im Mittelpunkt.

4.3 Aktivistische Community

Mögliche TikTok-Formate:

* Hinweise auf öffentliche Veranstaltungen,
* Informationen zu Initiativen,
* niedrigschwellige politische Bildung,
* Rückblicke auf gemeinschaftliche Aktivitäten,
* Informationen zu öffentlichen Beteiligungsmöglichkeiten.

Die Inhalte sollen zugänglich und verständlich sein.

4.4 Satiremedium

Mögliche TikTok-Formate:

* satirische Kurzvideos,
* visuelle Parodien,
* politische Pointen,
* humoristische Reaktionen auf aktuelle Ereignisse,
* Adaptionen geeigneter Internetformate.

Die satirische Aussage muss erkennbar bleiben. Satirische Darstellungen dürfen nicht unkenntlich als dokumentarische Tatsachenbehauptungen erscheinen.

4.5 Jugendkulturmedium

Mögliche TikTok-Formate:

* Musik- und Kulturberichte,
* Beiträge über Jugendkultur,
* Trends und kulturelle Ausdrucksformen,
* Streetwear und Subkulturen,
* Einordnung aktueller Internetkultur.

Die Inhalte sollen neugierig, kreativ und nah an aktuellen kulturellen Entwicklungen sein, ohne belehrend aufzutreten.

4.6 Dokumentation & Trends

Mögliche TikTok-Formate:

* dokumentarische Kurzvideos,
* spontane Beobachtungen,
* Alltagssituationen,
* visuelle Momentaufnahmen,
* Adaptionen aktueller Trendformate,
* dokumentarische Kurzkommentare.

Die Darstellung soll unmittelbar, authentisch und beobachtend wirken.

Abgrenzung zum Satiremedium: Dokumentation & Trends dokumentiert Realität und nutzt Trends als Darstellungsform. Das Satiremedium erzeugt eigenständige satirische Inhalte.

5. Video- und Medienproduktion

TikTok ist für die Veröffentlichung von Videoinhalten vorgesehen.

Die zentrale Medienproduktion des Netzwerks soll die erforderlichen Inhalte bereitstellen.

Dafür sind insbesondere folgende Werkzeuge vorgesehen:

* FFmpeg für Videoschnitt und Formatkonvertierung,
* Python für automatisierte Verarbeitung,
* Whisper für Transkription und Audioverarbeitung,
* Pillow, SVG und ImageMagick für ergänzende Grafiken.

Die technische Produktionsarchitektur wird im Technische-Architektur.md beschrieben.

5.1 Plattformadaption

Vor einer Veröffentlichung müssen Inhalte an die technischen und gestalterischen Anforderungen von TikTok angepasst werden.

Zu prüfen sind insbesondere:

* Seitenverhältnis,
* Auflösung,
* Videolänge,
* Dateiformat,
* Dateigröße,
* Bildrate,
* Ton und Audio,
* Untertitel,
* Textgestaltung,
* Beschreibungen,
* Hashtags.

Die jeweils aktuellen technischen Grenzwerte müssen vor der Implementierung anhand der offiziellen TikTok-Dokumentation geprüft werden.

5.2 Vorhandenes Material

Das Netzwerk bevorzugt authentisches vorhandenes Material.

Die Grundregel lautet:

Sharing statt Erfinden.

Für TikTok bedeutet das insbesondere:

1. Eigene authentische Aufnahmen bevorzugen.
2. Echtes Material anderer Urheber nur mit geklärten Rechten verwenden.
3. Geeignetes und lizenziertes Archivmaterial nutzen.
4. KI-generierte Illustrationen und Grafiken ergänzend einsetzen.
5. Fotorealistische KI-Darstellungen nur als letzte Möglichkeit verwenden.

Synthetische oder illustrative Darstellungen dürfen nicht als echte dokumentarische Aufnahmen ausgegeben werden.

6. Trends und Plattformkultur

TikTok ist für die Beobachtung und Nutzung aktueller digitaler Trends vorgesehen.

Dazu gehören insbesondere:

* populäre Videoformate,
* Sounds und Musik,
* Hashtags,
* visuelle Trends,
* wiederkehrende Erzählweisen,
* virale Themen,
* kulturelle und gesellschaftliche Diskussionen.

Die Redaktionsagenten dürfen geeignete Trends entsprechend ihrem Profil aufgreifen.

Die Verwendung eines Trends ist kein Selbstzweck.

Ein Trend muss zum Inhalt und zur redaktionellen Identität passen.

6.1 Gesellschaftliche Relevanz und Reichweite

Gesellschaftliche Relevanz und Reichweitenpotenzial werden getrennt bewertet.

Ein virales Format ist nicht automatisch gesellschaftlich relevant.

Ein gesellschaftlich wichtiges Thema muss nicht zwangsläufig eine hohe Reichweite erzielen.

Die Gewichtung richtet sich nach dem jeweiligen redaktionellen Profil.

6.2 Sounds und Musik

Die Nutzung von Musik und Sounds muss hinsichtlich Nutzungsrechten und Plattformbedingungen geprüft werden.

Es darf nicht vorausgesetzt werden, dass ein auf TikTok verfügbarer Sound automatisch außerhalb der Plattform verwendet werden darf.

Die konkrete Nutzung kommerzieller und nichtkommerzieller Musik sowie die entsprechenden Rechtebedingungen sind noch zu prüfen.

7. Veröffentlichungsstrategie

Die TikTok-Veröffentlichungen werden in den zentralen Redaktionskalender eingebunden.

Die jeweilige Redaktion entscheidet über den Inhalt und seine redaktionelle Perspektive.

Der Koordinationsagent übernimmt die organisatorische Abstimmung und berücksichtigt:

* geplante Veröffentlichungen,
* aktuelle Ereignisse,
* Dringlichkeit,
* redaktionelle Überschneidungen,
* Veröffentlichungen anderer Plattformen,
* verfügbare Leistungsdaten.

Dringende Ereignisse können reguläre Veröffentlichungen zeitlich verdrängen.

Verschobene Beiträge sollen nach Möglichkeit erhalten bleiben und neu eingeplant werden.

7.1 Automatisierte Veröffentlichung

Eine automatisierte Veröffentlichung ist grundsätzlich vorgesehen, sofern TikTok sie über offizielle und für das Projekt zugelassene Schnittstellen ermöglicht.

Die konkrete technische Möglichkeit, notwendige Berechtigungen und mögliche Einschränkungen sind noch zu prüfen.

Es werden keine inoffiziellen Clients oder nicht autorisierten Workarounds eingesetzt.

8. Interaktionen

8.1 Grundprinzip

Für TikTok gilt das netzwerkweite Prinzip:

Keine menschliche Nachahmung in Interaktion.

Die Agenten dürfen redaktionell Stellung beziehen, Informationen bereitstellen und sachlich auf öffentliche Diskussionen reagieren.

Sie dürfen nicht vortäuschen, menschliche Personen zu sein oder persönliche menschliche Erfahrungen zu besitzen.

8.2 Kommentare

Öffentliche Kommentare und Antworten sind im Rahmen der offiziell unterstützten Plattformfunktionen vorgesehen.

Kommentare müssen:

* zum jeweiligen redaktionellen Profil passen,
* einen eigenen Informations- oder Diskussionswert besitzen,
* nachvollziehbar und sachlich sein,
* bei Tatsachenbehauptungen auf überprüfbaren Informationen beruhen.

Es gilt die netzwerkweite Begrenzung:

Maximal zwei eigene Antworten auf denselben externen Account unter demselben Beitrag.

Danach wird die Diskussion nicht weitergeführt.

Ob und in welchem Umfang Kommentare und Antworten automatisiert über offizielle TikTok-Schnittstellen möglich sind, ist noch zu prüfen.

8.3 Direktnachrichten

Für eingehende Direktnachrichten gilt die gemeinsame Netzwerkregel.

Es wird ausschließlich folgende standardisierte Antwort verwendet:

„Vielen Dank für deine Nachricht! Dieser Account wird von einer KI verwaltet. Deine Nachricht wird an den Betreiber weitergeleitet. Er wird sich persönlich bei dir melden.“

Danach findet keine weitere automatische Unterhaltung statt.

Eingehende Direktnachrichten werden an den Projektbetreiber weitergeleitet. Dieser erhält eine sofortige Benachrichtigung.

Die technische Möglichkeit und die Berechtigungen für diese Weiterleitung müssen geprüft werden.

8.4 Öffentliche Kommentare als Themenquelle

Öffentliche Fragen und Kommentare können neue redaktionelle Themen anregen.

Die Redaktion darf das Thema eigenständig aufgreifen und recherchieren.

Der ursprüngliche Kommentar darf nicht zitiert oder reproduziert werden, auch nicht in anonymisierter Form.

Die Identität und persönliche Daten der kommentierenden Person dürfen nicht offengelegt werden.

9. Account- und Rechteverwaltung

Die Accounts gehören organisatorisch zum Projektbetreiber.

Die alleinige uneingeschränkte administrative Kontrolle bleibt beim Projektbetreiber.

Technische Zugänge und Berechtigungen müssen auf die erforderlichen Funktionen begrenzt werden.

Vor der Einrichtung ist zu prüfen:

* welche Account-Rollen TikTok bereitstellt,
* welche Rechte für Veröffentlichungen erforderlich sind,
* welche Berechtigungen für Analysefunktionen erforderlich sind,
* welche offiziellen API-Zugänge verfügbar sind,
* welche Voraussetzungen für eine automatisierte Verwaltung gelten.

Die endgültige Rechtevergabe ist noch offen.

10. TikTok API und technische Anbindung

Die Integration darf ausschließlich über offizielle TikTok-Schnittstellen und ausdrücklich unterstützte Funktionen erfolgen.

Vor der Implementierung müssen die aktuellen offiziellen Dokumentationen und Zulassungsvoraussetzungen geprüft werden.

Insbesondere sind folgende Bereiche zu untersuchen:

* Authentifizierung und OAuth,
* Account-Verknüpfung,
* Videoveröffentlichung,
* Upload- und Veröffentlichungsstatus,
* Medienanforderungen,
* Kommentare und Antworten,
* Direktnachrichten,
* Account- und Leistungsdaten,
* Berechtigungen und Freigaben,
* Einschränkungen für automatisierte Anwendungen.

Nicht unterstützte Funktionen dürfen nicht durch inoffizielle technische Umwege nachgebildet werden.

10.1 Plattformadapter

Die TikTok-Anbindung wird als eigener Plattformadapter in die gemeinsame technische Infrastruktur integriert.

Der Adapter verarbeitet die zentralen Aufträge der Redaktionen und übersetzt sie in die offiziell unterstützten TikTok-Funktionen.

Die redaktionelle Logik bleibt von der technischen Plattformanbindung getrennt.

10.2 Fehlerbehandlung

Fehlgeschlagene Veröffentlichungen müssen nachvollziehbar protokolliert werden.

Wiederholungsversuche dürfen keine doppelten Veröffentlichungen erzeugen.

Bei wiederholtem Scheitern wird der Koordinationsagent informiert.

Die konkrete technische Umsetzung ist noch offen.

11. Leistungsanalyse

Die Redaktionen analysieren die Leistung ihrer eigenen TikTok-Veröffentlichungen.

Der Koordinationsagent erhält den übergreifenden Überblick über die Leistungsdaten des Netzwerks.

Mögliche Kennzahlen sind, sofern TikTok sie bereitstellt:

* Videoaufrufe,
* Reichweite,
* Wiedergabezeit,
* durchschnittliche Wiedergabedauer,
* Abschlussrate,
* Likes,
* Kommentare,
* Shares,
* Profilaufrufe,
* Followerentwicklung.

Nicht verfügbare Daten werden als nicht verfügbar gekennzeichnet.

Fehlende Werte dürfen nicht geschätzt und als tatsächliche Messwerte ausgegeben werden.

11.1 Experimente

Die Redaktionen dürfen unterschiedliche Videoformate, Einstiege, Längen und Veröffentlichungsweisen testen.

Experimente werden nach den gemeinsamen Netzwerkregeln dokumentiert.

Der Koordinationsagent kann Ergebnisse auswerten und anderen Redaktionen Empfehlungen geben.

Die Übernahme eines Experiments bleibt eine redaktionelle Entscheidung.

12. Hashtag-System

TikTok verwendet das gemeinsame Hashtag-System des Netzwerks.

Es umfasst:

* netzwerkweite Hashtags,
* redaktionsspezifische Hashtags,
* situative Hashtags.

Der Koordinationsagent kann gemeinsame Hashtags empfehlen.

Die jeweilige Redaktion entscheidet über ihre Verwendung.

Hashtags sollen der thematischen Einordnung und Auffindbarkeit dienen und nicht wahllos zur künstlichen Reichweitensteigerung eingesetzt werden.

13. Transparenz und Kennzeichnung

Für TikTok gelten die gemeinsamen Transparenzregeln des Netzwerks.

Eine freiwillige allgemeine Kennzeichnung aller Accounts als KI-verwaltet ist nicht vorgesehen.

Bei einer direkten Nachfrage in einer Direktnachricht wird die festgelegte Transparenzantwort verwendet.

Gesetzlich oder durch TikTok vorgeschriebene Kennzeichnungen bleiben davon unberührt.

Insbesondere müssen die jeweils geltenden Kennzeichnungspflichten für KI-generierte oder synthetische Inhalte geprüft und eingehalten werden.

Die konkreten Kennzeichnungsanforderungen müssen vor der Implementierung anhand der aktuellen Plattformregeln geprüft werden.

14. Datenschutz und Sicherheit

Für TikTok gelten die gemeinsamen Datenschutz- und Sicherheitsregeln des Netzwerks.

Insbesondere:

* personenbezogene Daten nur im erforderlichen Umfang speichern,
* private Direktnachrichten ausschließlich an den Projektbetreiber weiterleiten,
* keine unnötigen personenbezogenen Informationen aus Kommentaren dauerhaft archivieren,
* Zugangsdaten und Tokens sicher speichern,
* keine geheimen Zugangsdaten in Git oder öffentlichen Dokumenten ablegen,
* Zugriffsrechte auf notwendige Funktionen begrenzen,
* Sicherheitsvorfälle protokollieren und unverzüglich melden.

Die gemeinsame Regel zur Aufbewahrung personenbezogener Kommentar- und Moderationsdaten beträgt grundsätzlich eine Woche. Gesetzlich erforderliche Aufbewahrungspflichten bleiben unberührt.

15. TikTok-Not-Aus

Der TikTok-Not-Aus soll ausschließlich die TikTok-Integration stoppen.

Andere Plattformen und deren Agenten arbeiten weiter.

Der TikTok-Not-Aus soll insbesondere stoppen:

* TikTok-Veröffentlichungen,
* automatisierte Kommentare und Antworten,
* automatisierte Interaktionen,
* automatische Nachrichten,
* geplante TikTok-Veröffentlichungen,
* neue Produktionsaufträge für TikTok.

Accounts, gespeicherte Inhalte, Archive und Zugangsdaten bleiben zunächst erhalten.

Nur der Projektbetreiber darf den TikTok-Not-Aus aufheben.

Vor dem Wiederanlauf müssen aufgelaufene Aufgaben auf Aktualität, Konflikte und mögliche Doppelveröffentlichungen geprüft werden.

Status: Die grundsätzliche Anforderung folgt aus dem Netzwerk-Not-Aus-Konzept. Die konkrete technische Umsetzung für TikTok ist noch festzulegen.

16. Offene Entscheidungen und Prüfaufgaben

Folgende TikTok-spezifische Punkte sind noch nicht abschließend festgelegt:

16.1 Organisatorisch

* endgültige Accountnamen,
* Einrichtung und Verifizierung der sechs Accounts,
* konkrete Account-Verwaltung,
* organisatorische Zuordnung der Zugänge.

16.2 Redaktionell

* verbindliche TikTok-Formatbibliothek,
* wiederkehrende Formate der einzelnen Identitäten,
* konkrete Videolängen und Gestaltungsrichtlinien,
* Umgang mit plattformspezifischen Trends und Sounds.

16.3 Technisch

* Verfügbarkeit und Zulassung der benötigten API-Funktionen,
* Voraussetzungen für automatisierte Veröffentlichungen,
* technische Möglichkeiten zur Kommentarverarbeitung,
* technische Möglichkeiten zur DM-Verarbeitung,
* verfügbare Leistungsdaten,
* Upload- und Veröffentlichungsgrenzen,
* Fehlerbehandlung und Wiederholungsmechanismen,
* technische Umsetzung des TikTok-Not-Aus.

16.4 Rechtlich und sicherheitsbezogen

* aktuelle Kennzeichnungspflichten für KI-Inhalte,
* Musik- und Soundrechte,
* Datenschutzanforderungen,
* Aufbewahrung und Löschung personenbezogener Daten,
* plattformspezifische Automatisierungsbedingungen.

Diese Punkte müssen vor der technischen Umsetzung geprüft und dokumentiert werden.

17. Aktueller Stand

Status: Grundkonzept erstellt; TikTok-spezifische Detailplanung offen.

Aus dem bisherigen Netzwerkbeschluss übernommen sind:

* sechs eigenständige redaktionelle Identitäten,
* plattformunabhängige redaktionelle Grundlage,
* individuelle Plattformadaption,
* Nutzung von Trends im Rahmen der jeweiligen Profile,
* gemeinsame Veröffentlichungskoordination,
* das Prinzip „Keine menschliche Nachahmung in Interaktion“,
* maximal zwei eigene Antworten auf denselben externen Account unter demselben Beitrag,
* standardisierte Antwort auf Direktnachrichten,
* keine freiwillige allgemeine Kennzeichnung aller Accounts als KI-verwaltet,
* Einhaltung verpflichtender Kennzeichnungspflichten,
* offizielle Plattformfunktionen als technische Grenze,
* gemeinsame Leistungsanalyse,
* gemeinsame Hashtag-Systematik,
* selektive Datenfreigabe,
* plattformspezifischer Not-Aus.

Noch nicht beschlossen oder technisch geprüft sind die konkreten TikTok-Funktionen, API-Berechtigungen und Veröffentlichungsabläufe.

18. Nächste Arbeitsschritte

1. Diese Datei als Plattformmodule/TikTok.md in Git übernehmen.
2. Die aktuellen offiziellen TikTok-API-Dokumentationen prüfen.
3. Die Voraussetzungen für automatisierte Veröffentlichungen klären.
4. Kommentar- und DM-Funktionen auf ihre technische Verfügbarkeit prüfen.
5. Die Accountstruktur und Rechtevergabe festlegen.
6. Eine TikTok-Formatbibliothek für die sechs Identitäten entwickeln.
7. Den technischen Adapter und seine Fehlerbehandlung entwerfen.
8. Die Sicherheits- und Not-Aus-Funktionen in die technische Planung aufnehmen.

19. Änderungsprotokoll

Version	Datum	Änderung
1.0	04.11.2026	Erstfassung des TikTok-Plattformmoduls auf Basis der gemeinsamen Netzwerkregeln

Ende des Plattformmoduls
