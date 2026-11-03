Plattformmodul: Instagram

Version: 1.0
Stand: 04.11.2026
Status: Grundkonzept; plattformspezifische Ausarbeitung und technische Prüfung offen
Dateipfad: Plattformmodule/Instagram.md

⸻

1. Zweck dieses Moduls

Dieses Modul beschreibt die geplante Integration von Instagram in das Redaktionsnetzwerk.

Es dokumentiert:

* die vorgesehene Instagram-Präsenz der sechs redaktionellen Identitäten,
* die redaktionelle Nutzung der Plattform,
* mögliche Inhalts- und Veröffentlichungsformate,
* die plattformbezogenen Interaktionsregeln,
* die technische Anbindung,
* die Leistungsanalyse,
* Datenschutz und Sicherheit,
* offene technische und organisatorische Entscheidungen.

Dieses Dokument ist eine eigenständige Übergabe- und Arbeitsgrundlage.

Es beschreibt den bisherigen Planungsstand. Nicht geprüfte Funktionen und technische Möglichkeiten werden ausdrücklich als offen gekennzeichnet.

2. Abhängigkeiten zu anderen Handbüchern

Handbuch	Relevanz
Projektgrundlage.md	Projektziele, politische Grundlagen und Netzwerkstruktur
Redaktionshandbuch.md	Sechs Identitäten und redaktionelle Zuständigkeiten
Plattformhandbuch.md	Gemeinsame Plattform- und Interaktionsregeln
Technische-Architektur.md	Infrastruktur, Medienproduktion und Schnittstellen
Betriebs-und-Sicherheitskonzept.md	Berechtigungen, Freigaben, Datenschutz und Not-Aus
Entwicklungsstatus.md	Implementierungsstand und offene Entscheidungen

Die gemeinsamen Netzwerkregeln gelten auch für Instagram. Dieses Modul konkretisiert sie, sobald die plattformspezifischen Anforderungen geprüft und festgelegt sind.

3. Grundstruktur der Instagram-Präsenz

Die sechs redaktionellen Identitäten sollen jeweils einen eigenen Instagram-Auftritt erhalten.

Vorgesehen sind:

1. Bewegungsmedium
2. Protestmedium
3. Aktivistische Community
4. Satiremedium
5. Jugendkulturmedium
6. Dokumentation & Trends

Jeder Auftritt repräsentiert ausschließlich die jeweilige redaktionelle Identität.

Die Accounts sollen organisatorisch zum Projektbetreiber gehören. Die alleinige uneingeschränkte administrative Kontrolle bleibt beim Projektbetreiber.

Die konkreten Accountnamen, Kontotypen und Einrichtungsschritte sind noch festzulegen.

4. Redaktionelle Nutzung

Instagram dient als Veröffentlichungs- und Kommunikationsplattform für die sechs redaktionellen Identitäten.

Die redaktionelle Grundlage eines Inhalts entsteht unabhängig von Instagram. Anschließend wird entschieden, ob und in welcher Form eine Veröffentlichung sinnvoll ist.

Nicht jeder Inhalt muss auf Instagram erscheinen.

Die Inhalte müssen zum jeweiligen redaktionellen Profil passen.

4.1 Bewegungsmedium

Mögliche Formate:

* dokumentarische Fotostrecken,
* kurze Reportagevideos,
* Porträts von Initiativen und Bewegungen,
* Hintergrundbeiträge,
* visuelle Dokumentationen von Veranstaltungen,
* Beiträge über soziale Bewegungen und Arbeitskämpfe.

Authentisches Material und die Perspektiven der Beteiligten stehen im Mittelpunkt.

4.2 Protestmedium

Mögliche Formate:

* aktuelle Protestdokumentationen,
* Demonstrationsberichte,
* Fotostrecken,
* kurze Ereigniszusammenfassungen,
* dokumentarische Videos,
* Informationen zu Protesten und gesellschaftlichen Konflikten.

Die unmittelbare Dokumentation steht im Mittelpunkt.

4.3 Aktivistische Community

Mögliche Formate:

* Veranstaltungshinweise,
* Informationen zu Initiativen,
* visuelle Veranstaltungskalender,
* politische Bildungsbeiträge,
* Rückblicke auf gemeinschaftliche Aktivitäten,
* Informationen zu öffentlichen Beteiligungsmöglichkeiten.

Die Inhalte sollen zugänglich, verständlich und gemeinschaftsorientiert sein.

4.4 Satiremedium

Mögliche Formate:

* politische Memes,
* satirische Bildbeiträge,
* Collagen,
* Parodien,
* kurze satirische Videos,
* visuelle Kommentare zu aktuellen Ereignissen.

Die satirische Aussage muss erkennbar bleiben. Satirische Darstellungen dürfen nicht unkenntlich als dokumentarische Tatsachenbehauptungen erscheinen.

4.5 Jugendkulturmedium

Mögliche Formate:

* Musik- und Kulturberichte,
* Beiträge über Jugendkultur,
* Streetwear und Subkulturen,
* visuelle Trendbeobachtungen,
* Einordnung aktueller Internetkultur,
* kulturelle Kurzformate.

Die Inhalte sollen kreativ, neugierig und nah an aktuellen kulturellen Entwicklungen sein, ohne belehrend aufzutreten.

4.6 Dokumentation & Trends

Mögliche Formate:

* dokumentarische Kurzvideos,
* spontane Momentaufnahmen,
* Fotostrecken,
* Alltagssituationen,
* Adaptionen aktueller Trendformate,
* visuelle Beobachtungen gesellschaftlicher Entwicklungen.

Die Darstellung soll authentisch, unmittelbar und beobachtend sein.

Abgrenzung zum Satiremedium: Dokumentation & Trends dokumentiert Realität und nutzt Trends als Darstellungsform. Das Satiremedium erzeugt eigenständige satirische Inhalte.

5. Medienproduktion und Plattformadaption

Die zentrale Medienproduktion des Netzwerks stellt die benötigten Inhalte bereit.

Vorgesehene Werkzeuge sind insbesondere:

* FFmpeg für Videobearbeitung,
* Python für automatisierte Verarbeitung,
* Whisper für Transkription und Audioverarbeitung,
* Pillow, SVG und ImageMagick für Grafiken und Bildbearbeitung.

Die technische Produktionsarchitektur wird in Technische-Architektur.md beschrieben.

5.1 Mögliche Medienformate

Für Instagram sind insbesondere folgende Darstellungsformen vorgesehen:

* Einzelbilder,
* Bildserien und Karussellbeiträge,
* Kurzvideos,
* Stories,
* visuelle Infografiken.

Die tatsächliche Automatisierbarkeit der jeweiligen Formate muss geprüft werden.

5.2 Formatadaption

Vor einer Veröffentlichung müssen Inhalte an die technischen und gestalterischen Anforderungen von Instagram angepasst werden.

Zu prüfen sind insbesondere:

* Seitenverhältnis,
* Auflösung,
* Bild- und Videoformat,
* Dateigröße,
* Videolänge,
* Bildrate,
* Ton und Audio,
* Untertitel,
* Textgestaltung,
* Beschreibungen,
* Hashtags,
* Verlinkungsmöglichkeiten.

Die jeweils aktuellen technischen Grenzwerte müssen vor der Implementierung anhand der offiziellen Instagram-Dokumentation geprüft werden.

5.3 Materialverwendung

Es gilt das gemeinsame Prinzip:

Sharing statt Erfinden.

Die bevorzugte Reihenfolge lautet:

1. Eigene authentische Aufnahmen.
2. Echtes Material anderer Urheber mit geklärten Nutzungsrechten.
3. Geeignetes und lizenziertes Archivmaterial.
4. KI-generierte Illustrationen und Grafiken.
5. Fotorealistische KI-Darstellungen als letzte Möglichkeit.

Synthetische oder illustrative Darstellungen dürfen nicht als echte dokumentarische Aufnahmen ausgegeben werden.

6. Trends und Instagram-Kultur

Das Netzwerk beobachtet aktuelle Instagram-Trends und berücksichtigt sie bei der redaktionellen Planung.

Dazu gehören insbesondere:

* visuelle Trends,
* Kurzvideoformate,
* populäre Sounds und Musik,
* Hashtags,
* wiederkehrende Gestaltungsweisen,
* virale Themen,
* kulturelle und gesellschaftliche Diskussionen.

Die Redaktionen dürfen geeignete Trends entsprechend ihrem Profil aufgreifen.

Ein Trend ist jedoch kein Selbstzweck. Er muss zum Inhalt und zur redaktionellen Identität passen.

6.1 Gesellschaftliche Relevanz und Reichweite

Gesellschaftliche Relevanz und Reichweitenpotenzial werden getrennt bewertet.

Ein Trend ist nicht automatisch gesellschaftlich relevant.

Ein gesellschaftlich wichtiges Thema besitzt nicht automatisch ein hohes Reichweitenpotenzial.

Die Gewichtung richtet sich nach dem jeweiligen redaktionellen Profil.

6.2 Musik und Sounds

Die Nutzung von Musik und Sounds muss hinsichtlich Nutzungsrechten und Plattformbedingungen geprüft werden.

Ein auf Instagram verfügbarer Sound darf nicht automatisch außerhalb der Plattform verwendet werden.

Die konkreten Rechtebedingungen und Möglichkeiten zur automatisierten Verwendung von Musik sind noch zu prüfen.

7. Veröffentlichungsstrategie

Instagram-Veröffentlichungen werden in den zentralen Redaktionskalender eingebunden.

Die jeweilige Redaktion entscheidet über Inhalt und redaktionelle Perspektive.

Der Koordinationsagent übernimmt die organisatorische Abstimmung und berücksichtigt:

* geplante Veröffentlichungen,
* aktuelle Ereignisse,
* Dringlichkeit,
* redaktionelle Überschneidungen,
* Veröffentlichungen auf anderen Plattformen,
* verfügbare Leistungsdaten.

Dringende Ereignisse können reguläre Veröffentlichungen zeitlich verdrängen.

Verschobene Beiträge sollen nach Möglichkeit erhalten bleiben und neu eingeplant werden.

7.1 Automatisierte Veröffentlichung

Eine automatisierte Veröffentlichung ist vorgesehen, sofern Instagram sie über offizielle und für das Projekt zugelassene Schnittstellen ermöglicht.

Die konkreten Voraussetzungen, Berechtigungen und Einschränkungen müssen vor der Implementierung geprüft werden.

Es werden keine inoffiziellen Clients oder nicht autorisierten Workarounds eingesetzt.

8. Interaktionen

8.1 Grundprinzip

Für Instagram gilt das netzwerkweite Prinzip:

Keine menschliche Nachahmung in Interaktion.

Die Agenten dürfen redaktionell Stellung beziehen, Informationen bereitstellen und sachlich auf öffentliche Diskussionen reagieren.

Sie dürfen nicht vortäuschen, menschliche Personen zu sein oder persönliche menschliche Erfahrungen zu besitzen.

8.2 Kommentare und Antworten

Öffentliche Kommentare und Antworten sind im Rahmen der offiziell unterstützten Plattformfunktionen vorgesehen.

Kommentare müssen:

* zum jeweiligen redaktionellen Profil passen,
* einen eigenen Informations- oder Diskussionswert besitzen,
* nachvollziehbar und sachlich sein,
* bei Tatsachenbehauptungen auf überprüfbaren Informationen beruhen.

Es gilt die netzwerkweite Begrenzung:

Maximal zwei eigene Antworten auf denselben externen Account unter demselben Beitrag.

Danach wird die Diskussion nicht weitergeführt.

Ob und in welchem Umfang Kommentare und Antworten automatisiert über offizielle Instagram-Schnittstellen möglich sind, ist noch zu prüfen.

8.3 Direktnachrichten

Für eingehende Direktnachrichten gilt die gemeinsame Netzwerkregel.

Es wird ausschließlich folgende standardisierte Antwort verwendet:

„Vielen Dank für deine Nachricht! Dieser Account wird von einer KI verwaltet. Deine Nachricht wird an den Betreiber weitergeleitet. Er wird sich persönlich bei dir melden.“

Danach findet keine weitere automatische Unterhaltung statt.

Eingehende Direktnachrichten werden an den Projektbetreiber weitergeleitet. Dieser erhält eine sofortige Benachrichtigung.

Die technische Möglichkeit und die erforderlichen Berechtigungen müssen geprüft werden.

8.4 Öffentliche Kommentare als Themenquelle

Öffentliche Fragen und Kommentare können neue redaktionelle Themen anregen.

Die Redaktion darf das Thema eigenständig aufgreifen und recherchieren.

Der ursprüngliche Kommentar darf nicht zitiert oder reproduziert werden, auch nicht in anonymisierter Form.

Die Identität und persönliche Daten der kommentierenden Person dürfen nicht offengelegt werden.

9. Account- und Rechteverwaltung

Die Accounts gehören organisatorisch zum Projektbetreiber.

Die alleinige uneingeschränkte administrative Kontrolle bleibt beim Projektbetreiber.

Technische Zugänge und Berechtigungen müssen auf die tatsächlich benötigten Funktionen begrenzt werden.

Vor der Einrichtung ist zu prüfen:

* welche Kontotypen für die geplante Nutzung erforderlich sind,
* welche Account-Rollen Instagram bereitstellt,
* welche Rechte für Veröffentlichungen benötigt werden,
* welche Berechtigungen für Analysefunktionen erforderlich sind,
* welche offiziellen API-Zugänge verfügbar sind,
* welche Voraussetzungen für automatisierte Anwendungen gelten.

Die endgültige Rechtevergabe ist noch offen.

10. Instagram API und technische Anbindung

Die Integration darf ausschließlich über offizielle Instagram-Schnittstellen und ausdrücklich unterstützte Funktionen erfolgen.

Vor der Implementierung müssen die aktuellen offiziellen Dokumentationen und Zulassungsvoraussetzungen geprüft werden.

Insbesondere sind folgende Bereiche zu untersuchen:

* Authentifizierung und OAuth,
* Account-Verknüpfung,
* Veröffentlichungen von Bildern,
* Veröffentlichungen von Karussells,
* Video- und Reel-Veröffentlichungen,
* Story-Veröffentlichungen,
* Kommentare und Antworten,
* Direktnachrichten,
* Account- und Leistungsdaten,
* Berechtigungen und Freigaben,
* Einschränkungen für automatisierte Anwendungen.

Nicht unterstützte Funktionen dürfen nicht durch inoffizielle technische Umwege nachgebildet werden.

10.1 Plattformadapter

Die Instagram-Anbindung wird als eigener Plattformadapter in die gemeinsame technische Infrastruktur integriert.

Der Adapter verarbeitet die zentralen Veröffentlichungs- und Interaktionsaufträge und übersetzt sie in die offiziell unterstützten Instagram-Funktionen.

Die redaktionelle Logik bleibt von der technischen Plattformanbindung getrennt.

10.2 Fehlerbehandlung

Fehlgeschlagene Veröffentlichungen müssen nachvollziehbar protokolliert werden.

Wiederholungsversuche dürfen keine doppelten Veröffentlichungen erzeugen.

Bei wiederholtem Scheitern wird der Koordinationsagent informiert.

Die konkrete technische Umsetzung ist noch offen.

11. Leistungsanalyse

Die Redaktionen analysieren die Leistung ihrer eigenen Instagram-Veröffentlichungen.

Der Koordinationsagent erhält den übergreifenden Überblick über die Leistungsdaten des Netzwerks.

Mögliche Kennzahlen sind, sofern Instagram sie bereitstellt:

* Reichweite,
* Impressionen,
* Aufrufe,
* Wiedergabezeit,
* Likes,
* Kommentare,
* Shares,
* gespeicherte Beiträge,
* Profilaufrufe,
* Followerentwicklung,
* Interaktionen.

Nicht verfügbare Daten werden als nicht verfügbar gekennzeichnet.

Fehlende Werte dürfen nicht geschätzt und als tatsächliche Messwerte ausgegeben werden.

11.1 Experimente

Die Redaktionen dürfen unterschiedliche Formate, Bildgestaltungen, Videoeinstiege, Längen und Veröffentlichungsweisen testen.

Experimente werden nach den gemeinsamen Netzwerkregeln dokumentiert.

Der Koordinationsagent kann Ergebnisse auswerten und anderen Redaktionen Empfehlungen geben.

Die Übernahme eines Experiments bleibt eine redaktionelle Entscheidung.

12. Hashtag-System

Instagram verwendet das gemeinsame Hashtag-System des Netzwerks.

Es umfasst:

* netzwerkweite Hashtags,
* redaktionsspezifische Hashtags,
* situative Hashtags.

Der Koordinationsagent kann gemeinsame Hashtags empfehlen.

Die jeweilige Redaktion entscheidet über ihre Verwendung.

Hashtags sollen der thematischen Einordnung und Auffindbarkeit dienen und nicht wahllos zur künstlichen Reichweitensteigerung eingesetzt werden.

13. Transparenz und Kennzeichnung

Für Instagram gelten die gemeinsamen Transparenzregeln des Netzwerks.

Eine freiwillige allgemeine Kennzeichnung aller Accounts als KI-verwaltet ist nicht vorgesehen.

Bei einer direkten Nachfrage in einer Direktnachricht wird die festgelegte Transparenzantwort verwendet.

Gesetzlich oder durch Instagram vorgeschriebene Kennzeichnungen bleiben davon unberührt.

Insbesondere müssen die jeweils geltenden Kennzeichnungspflichten für KI-generierte oder synthetische Inhalte geprüft und eingehalten werden.

Die konkreten Anforderungen sind vor der Implementierung anhand der aktuellen Plattformregeln zu prüfen.

14. Datenschutz und Sicherheit

Für Instagram gelten die gemeinsamen Datenschutz- und Sicherheitsregeln des Netzwerks.

Insbesondere:

* personenbezogene Daten nur im erforderlichen Umfang speichern,
* private Direktnachrichten ausschließlich an den Projektbetreiber weiterleiten,
* keine unnötigen personenbezogenen Informationen aus Kommentaren dauerhaft archivieren,
* Zugangsdaten und Tokens sicher speichern,
* keine geheimen Zugangsdaten in Git oder öffentlichen Dokumenten ablegen,
* Zugriffsrechte auf notwendige Funktionen begrenzen,
* Sicherheitsvorfälle protokollieren und unverzüglich melden.

Die gemeinsame Regel zur Aufbewahrung personenbezogener Kommentar- und Moderationsdaten beträgt grundsätzlich eine Woche. Gesetzlich erforderliche Aufbewahrungspflichten bleiben unberührt.

15. Instagram-Not-Aus

Der Instagram-Not-Aus soll ausschließlich die Instagram-Integration stoppen.

Andere Plattformen und deren Agenten arbeiten weiter.

Der Instagram-Not-Aus soll insbesondere stoppen:

* Instagram-Veröffentlichungen,
* automatisierte Kommentare und Antworten,
* automatisierte Interaktionen,
* automatische Nachrichten,
* geplante Instagram-Veröffentlichungen,
* neue Produktionsaufträge für Instagram.

Accounts, gespeicherte Inhalte, Archive und Zugangsdaten bleiben zunächst erhalten.

Nur der Projektbetreiber darf den Instagram-Not-Aus aufheben.

Vor dem Wiederanlauf müssen aufgelaufene Aufgaben auf Aktualität, Konflikte und mögliche Doppelveröffentlichungen geprüft werden.

Status: Die grundsätzliche Anforderung folgt aus dem Netzwerk-Not-Aus-Konzept. Die konkrete technische Umsetzung für Instagram ist noch festzulegen.

16. Offene Entscheidungen und Prüfaufgaben

16.1 Organisatorisch

* endgültige Accountnamen,
* Einrichtung und Verifizierung der sechs Accounts,
* Auswahl der geeigneten Kontotypen,
* organisatorische Verwaltung der Zugänge.

16.2 Redaktionell

* verbindliche Instagram-Formatbibliothek,
* wiederkehrende Formate der einzelnen Identitäten,
* konkrete Bild- und Videorichtlinien,
* Umgang mit plattformspezifischen Trends und Sounds.

16.3 Technisch

* Verfügbarkeit und Zulassung der benötigten API-Funktionen,
* Voraussetzungen für automatisierte Veröffentlichungen,
* technische Möglichkeiten für Bilder, Karussells, Reels und Stories,
* Kommentarverarbeitung,
* DM-Verarbeitung,
* verfügbare Leistungsdaten,
* Upload- und Veröffentlichungsgrenzen,
* Fehlerbehandlung und Wiederholungsmechanismen,
* technische Umsetzung des Instagram-Not-Aus.

16.4 Rechtlich und sicherheitsbezogen

* aktuelle Kennzeichnungspflichten für KI-Inhalte,
* Musik- und Soundrechte,
* Datenschutzanforderungen,
* Aufbewahrung und Löschung personenbezogener Daten,
* plattformspezifische Automatisierungsbedingungen.

Diese Punkte müssen vor der technischen Umsetzung geprüft und dokumentiert werden.

17. Aktueller Stand

Status: Grundkonzept erstellt; Instagram-spezifische Detailplanung offen.

Aus den bisherigen Netzwerkentscheidungen übernommen sind:

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
* Nutzung offizieller Plattformfunktionen,
* gemeinsame Leistungsanalyse,
* gemeinsame Hashtag-Systematik,
* selektive Datenfreigabe,
* plattformspezifischer Not-Aus.

Die konkreten Instagram-Funktionen, API-Berechtigungen und Veröffentlichungsabläufe sind noch nicht abschließend geprüft.

18. Nächste Arbeitsschritte

1. Diese Datei als Plattformmodule/Instagram.md in Git übernehmen.
2. Die aktuellen offiziellen Instagram-API-Dokumentationen prüfen.
3. Die Voraussetzungen für automatisierte Veröffentlichungen klären.
4. Bild-, Karussell-, Reel- und Story-Veröffentlichungen auf ihre technische Verfügbarkeit prüfen.
5. Kommentar- und DM-Funktionen auf ihre technische Verfügbarkeit prüfen.
6. Die Accountstruktur und Rechtevergabe festlegen.
7. Eine Instagram-Formatbibliothek für die sechs Identitäten entwickeln.
8. Den technischen Adapter und seine Fehlerbehandlung entwerfen.
9. Die Sicherheits- und Not-Aus-Funktionen in die technische Planung aufnehmen.

19. Änderungsprotokoll

Version	Datum	Änderung
1.0	04.11.2026	Erstfassung des Instagram-Plattformmoduls auf Basis der gemeinsamen Netzwerkregeln

Ende des Plattformmoduls
