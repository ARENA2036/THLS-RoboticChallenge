# <img width="260" height="180" alt="image" src="https://github.com/user-attachments/assets/eb9f1a31-b0ff-482b-8d8f-d70cfd1132f3" />

**Bosch Rexroth AG** ist ein weltweit führendes Unternehmen in der Antriebs- und Steuerungstechnik mit Sitz in Stuttgart. Das Team entstammt dem Bereich **PAN – Product Area for New Business**, der neue Geschäftsfelder und innovative Technologieansätze für Bosch Rexroth entwickelt und validiert.

Das sechsköpfige AI Robotics Team um Christian Lasarczyk, Jonas Beigel und Lukas Küstermann, Maximilian Hess  sowie Ralf Becker und David Brandt (Partner) verfolgt mit diesem Projekt eine Doppelstrategie: den Nachweis einer vollautomatisierten Leitungssatzkonfektionierung mit Bosch-Rexroth-Industriekomponenten – und den Aufbau eines **KI-gestützten Automatisierungssystems**, das es ermöglicht, Roboterprogramme für neue Leitungssatz-Varianten durch textuelles Fachwissen statt durch manuelle Programmierung zu erzeugen.

**Website:** https://www.boschrexroth.com

---

Der Beitrag des **AI Robotics Teams Bosch Rexroth** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

**Bosch Rexroth** verfolgt zwei eng verzahnte Ansätze: Zum einen eine **industrietaugliche Roboterzelle** aus Bosch-Rexroth-Katalogkomponenten (Kassow KR1205, ctrlX AUTOMATION, Cambrian Vision, Schunk-Greifer), die alle Steckvorgänge des Challenge-Leitungssatzes vollautomatisch ausführt. Zum anderen ein **KI-gestütztes Automatisierungssystem (Skills + Flows + CLIs)**, das es einem LLM ermöglicht, aus textuell beschriebenem Fachwissen vollständige Roboterprogramme für neue Leitungssatz-Varianten zu generieren – ohne manuelle Programmierung.

<!-- Bild Roboterzelle auf Aluminiumprofil-Tisch hier einfügen -->

Der Demonstrator besteht aus einem kompakten, transportablen Tischaufbau mit integriertem IPC, ctrlX CORE-Steuerung, Kassow KR1205-Roboter (7 Achsen, 120 cm Reichweite, 5 kg Traglast), Cambrian-Kameramodul und Schunk-EGK-Greifer mit 3D-gedruckten, gummierten Greiferbacken. Alle Vorrichtungen wurden vom Team selbst konstruiert und 3D-gedruckt; der Aufbau benötigt weder Druckluft noch Schutzumhausung und läuft an 220-V-Anschluss.

Der Demonstrator umfasst unter anderem:

* **Vollständige Stecksequenz**: alle Kabel des Challenge-Leitungssatzes (Twisted-Pair-MQS, Einzel-MQS Nano, AMP-MCP, Koaxial) werden vollautomatisch gegriffen, positioniert, orientiert und in die jeweiligen Steckverbinder eingeführt
* **Kameragestützte 6D-Positionserkennung**: Cambrian Vision erkennt Kontakte und Gehäuse aus CAD-trainierten Kantenmodellen in < 1 Sekunde; Training auf Basis der bereitgestellten STEP-Daten in 8–10 Stunden
* **Trichter-geführte Twisted-Pair-Insertion (Funnel Insert)**: eigens entwickelte passive Vorrichtung mit Führungskontur + Schieber für synchrone Ausrichtung beider Enden eines verdrillten Doppelkabels – für die Schutzanmeldung eingereicht
* **Nachgreif-Strategie für Nano-MQS**: bei sehr tiefer Einführtiefe greift der Roboter das Kabel am hinteren Ende nach, um Abknicken zu verhindern; Einführung bis zum Verrasten
* **Sekundärverriegelungs-Betätigung durch Roboter**: alle passiven Vorrichtungsschieber werden rein über den Roboter betätigt – keine Aktorik in der Vorrichtung
* **Werkstückträger-Konzept**: separate Zuführung von Einzelkabeln und Leitungssatz mit Referenzierungsobjekt für schnelle Kamera-basierte Lagebestimmung
* **KI-gestütztes Programm-Onboarding (Skills + Flows)**: LLM schreibt JSON-basierte Montageabläufe aus textuell beschriebenem Fachwissen; generierte Flows können über standardisierte CLI-Tools direkt ausgeführt werden
* **LLM-Debugging via Session-Recordings**: jeder Roboterlauf wird als NDJSON aufgezeichnet; das LLM liest Fehlerereignisse und korrigiert Programme eigenständig

**Bosch Rexroth** präsentierte einen vollständigen, aufgezeichneten Durchlauf der Leitungssatzkonfektionierung – alle Steckvorgänge inklusive Sekundärverriegelungen mit einem einzigen Roboterarm, kameragestützt und ohne Greiferwechsel.

Im Rahmen des demonstrierten Durchlaufs wurden alle Kabel des Challenge-Leitungssatzes in die entsprechenden Steckverbinder eingeführt und die Sekundärverriegelungen geschlossen. Das Einsetzen der bestückten Stecker in das Umgehäuse sowie das Kabelbündeln wurden bewusst zurückgestellt, um Stabilität der übrigen Schritte zu priorisieren; beides ist für die Live-Demo geplant.

Zum Einsatz kommt der **Kassow KR1205** als Roboterarm:

* 7 Achsen (gegenüber Standard-6-Achs-Systemen ermöglicht die 7. Achse Arbeit um Ecken und in beengten Konfigurationen)
* 120 cm Reichweite, 5 kg Traglast
* Programmierung über Teach-Panel oder C++-KORD-API
* Kraftschätzung über Drehmoment-Strom-Verhältnis der Gelenke (kein separater Kraftsensor); Pull-Prüfung per leichtem Zurückziehen geplant

Die **ctrlX AUTOMATION**-Plattform (Bosch Rexroth) bildet das Steuerungsherz:

* ctrlX CORE (X5/X7) als Echtzeit-Linux-Industrial-OS mit offenem App-Ökosystem
* unterstützt Python, C/C++, Go, Node.js, ROS/ROS2, IEC 61131, .NET
* ctrlX IPC für GPU-basierte Bildverarbeitungslast
* nahtlose Integration von Cambrian Vision und Kassow-Roboter über ctrlX Data Layer
* eigene C++-Applikation als ctrlX-OS-App verpackt für industrielle Echtzeitumgebung

Das **Cambrian Vision System** ermöglicht die kameralose Lagebestimmung:

* Industrie-PC mit GPU + Kameramodul (stereoskopisch, 2 Kameras)
* Training auf Basis von STEP-CAD-Modellen: synthetische Kantenmuster-Datenbank → Echtzeit-Edge-Matching in < 1 Sekunde
* 6D-Pose (Translation + Rotation) für Kontakt und Steckgehäuse; Offset-Translation und -Rotation werden pro Steckertyp in `connectors.json` konfiguriert
* Warnung des Systems bei Nano-MQS-Kontakten aufgrund sehr kleiner Kantenmerkmale

Der **KI-gestützte Programmierprozess** läuft in drei Stufen:

**Stufe A – AI schreibt Flows (Montagerezepte):** JSON-basierte Ablaufdateien mit Skills und Parametern werden vom LLM generiert. Reales Beispiel: Coax-Pick-&-Insert-Flow mit `open_gripper → move_to_pose → close_gripper → trigger_vision → transform_prediction → plug_insert → release_gripper`. Connector-spezifische Parameter (Greifpunkt-Offset, Einführtiefe, Rotationskorrektur) liegen in separater `connectors.json` – zukünftig soll das LLM diese aus Stecker-Datenblättern ableiten.

**Stufe B – AI implementiert neue Skills:** Fachexperte beschreibt neues Steckverhalten in natürlicher Sprache; LLM implementiert einen neuen Compound Skill (z. B. `funnel_align_insert`), der dann in allen zukünftigen Flows wiederverwendet werden kann. Testen aktuell noch am realen System; Simulation in Vorbereitung.

**Stufe C – AI debuggt mit Session-Recordings:** NDJSON-Aufzeichnungen aller Roboterläufe; LLM liest Fehlercode + Kontext und korrigiert Flow-Konfiguration (z. B. Einführtiefe +1 mm bei wiederholt nicht-verrastendem Kontakt).

Der Demonstrator umfasst folgende **Prozessschritte**:

* Kamera-Referenzierung des Werkstückträgers über Fixture-Objekt
* Greifer fährt über Kabelbereitstellung, Kamera detektiert Kontakt → Griff
* für Twisted-Pair: Routing durch Trichtervorrichtung, Ablegen auf Ebene, Umorientierung, Einführen beider Crimps synchron; Schieber schließt Sekundärverriegelung
* für Nano-MQS Einzel: Griff weiter hinten am Kabel, tiefes Einführen, Nachgreifen, erneutes Einführen bis Verrastung; Vorrichtungsschieber öffnet zweite Kavitätsebene
* für AMP-MCP und Koax: Kamera über Vorrichtung, Detektion Kontakt + Stecker, Ausrichtung, Einführen; Greiferfinger betätigt Sekundärverriegelungs-Lasche
* Video läuft in 2× Geschwindigkeit; reale Zykluszeit im Video dargestellt

<!-- Bild Trichtervorrichtung / Nano-MQS-Nachgreifen hier einfügen -->

---

## Ergebnisse

| Kennzahl | Wert |
|---|---|
| Demonstrierter Prozess | Vollständige Stecksequenz aller Kabel inkl. Sekundärverriegelungen (ohne Umgehäuse-Zusammenführung und Bündeln) |
| Aktuelle Zykluszeit (Gesamtdurchlauf) | **~9–10 Minuten** (2× beschleunigt aufgezeichnet) |
| Ziel-Zykluszeit (nach Optimierung) | **~3,5 Minuten** |
| Erste-Durchlauf-Erfolgsrate (Video-Aufnahme) | 1 von 9 Versuchen ohne Parameternachstellung – Robustheitsmessung noch ausstehend |
| Roboterarme | 1 × Kassow KR1205 (7-Achsen-Kollaborativroboter) |
| Greifer | Schunk EGK (Standard-Zweifingergreifer), 3D-gedruckte Backen mit Gummibeschichtung |
| Kamerasystem | Cambrian Vision (Stereokamera + GPU-IPC); Training aus STEP-CAD in 8–10 h |
| Kraftmessung | indirekt via Motorstrom/Drehmoment (kein separater Kraftsensor); Pull-Prüfung geplant |
| Werkzeugwechsel | keiner |
| Druckluft | keine |
| Spannungsversorgung | 220 V |
| Hardwarekosten | **58.300 € VK** (ctrlX CORE+IPC 3.700 € + KR1205 31.500 € + Schunk EGK 3.100 € + Aluprofile 3.000 € + Cambrian 17.000 €) |
| Betriebskosten/Jahr | **~10.000 €** (verschlissene Teile, Strom) |
| Investitionskosten Gesamtanlage | **~100.000 €** (60.000 € Hardware + 40.000 € Inbetriebnahme & Software) |
| KI-Onboarding-Ziel (neue Variante) | **< 1 Woche** |

---

## KI-Architektur: Skills + Flows + CLIs

Das Herzstück des Bosch-Rexroth-Beitrags ist eine **LLM-fähige Automatisierungsarchitektur**, die es einem Sprachmodell erlaubt, direkt als Programmierer des Roboters zu fungieren:

| Ebene | Beschreibung |
|---|---|
| **Primitives** | Einzelne Grundbefehle: `move_to_pose`, `close_gripper`, `trigger_vision`, `wait` |
| **Compound Skills** | Fachlich zusammengesetzte Arbeitsschritte: `plug_insert`, `funnel_align_insert`, `funnel_pre_position` – hier fließt Leitungssatz-Know-how ein |
| **Flows (JSON)** | Vollständiger Montageablauf als maschinenlesbares Rezept; vom LLM generiert |
| **CLI-Tools** | `cli_calibrate`, `cli_poses`, `cli_run`, `cli_gripper` – LLM-taugliche Werkzeuge mit JSON-Output, standardisierten Exit-Codes, Dry-Run-Modus und selbstdokumentierendem `--help` |
| **Session-Recordings (NDJSON)** | Vollprotokollierung aller Roboterläufe; LLM liest Fehler und korrigiert eigenständig |
| **`connectors.json`** | Steckertyp-spezifische physikalische Parameter (Greifpunkt-Offset, Einführtiefe, Rotationskorrektur); vom Fachexperten gepflegt, zukünftig KI-generiert aus Datenblättern |

---

## Highlights & Alleinstellungsmerkmale

* **Vollständige Industriekomponenten**: ausschließlich Bosch-Rexroth-Katalogkomponenten – kein Sonderbau, keine Druckluft, kein Greiferwechsel; direkt skalierbar
* **7-Achsen-Kinematik (Kassow KR1205)**: ermöglicht Arbeit in beengten Räumen und um Ecken – für Leitungssatzmontage an Formbrettern besonders relevant
* **Trichter-Insertion für Twisted-Pair** (Schutzanmeldung eingereicht): passive Vorrichtung mit Führungskontur + Schieber löst das schwierigste Handhabungsproblem des Challenge-Leitungssatzes – synchrone Ausrichtung beider verdrillter Kabelenden
* **LLM als Roboter-Programmierer**: dreistufige KI-Architektur (Flow-Generierung → Skill-Implementierung → Session-Debugging) ermöglicht Onboarding neuer Leitungssatz-Varianten in < 1 Woche ohne Programmierexperten
* **Cambrian-CAD-Training**: keine manuelle Einlernphase – STEP-Modelle direkt als Trainingsgrundlage; neuer Steckertyp in 8–10 Stunden einsatzbereit
* **ctrlX OS als offene Plattform**: eigene C++-Applikationen als industrietaugliche Apps deployen; ROS/ROS2-Integration möglich; Fanuc- und KUKA-Apps bereits verfügbar

---

## Offene Punkte & Ausblick

* **Umgehäuse-Zusammenführung**: Bestückten Stecker in Umgehäuse einsetzen – technisch vorbereitet, bis zur Live-Demo geplant
* **Kabelbündeln**: Prozessschritt noch nicht umgesetzt; Kabelbinder-System (HellermannTyton ~6.000 €) und Heißkleber-Bündelung wurden als Optionen evaluiert
* **Zykluszeit-Reduktion auf ~3,5 Minuten**: durch Robotergeschwindigkeitserhöhung und optimierte Posenkonfiguration
* **Pull-Prüfung / Verrastungskontrolle**: leichte Zugkraft mit Kraftmessung über KR1205-Drehmoment; visuelle Prüfung via Cambrian 2D geplant
* **Robustheitsmessung**: systematische Erfolgsrate-Erhebung über mehrere konsekutive Durchläufe steht aus
* **Trichter-Skalierung**: aktuell 2 Slots im Trichter; für vollständige Leitungssätze mit mehreren Twisted-Pair-Kabeln in einer Reihe sind erweiterte Führungskonzepte erforderlich
* **Leitungslängenänderungen**: Routing-Anpassungen müssen noch automatisiert werden (Graph-Algorithmen geplant); aktuell manuell
* **KBL/VEC-Datenintegration**: Verbindungsplan-Import in die KI-Pipeline noch schwach ausgebaut; Ziel: automatische Ableitung von Greifpunkt-Offsets und Vorrichtungsgeometrien aus Stecker-Datenblättern und VEC-Daten
* **Wirtschaftlichkeit**: Business Case für 400.000 Stück/Jahr noch nicht vollständig ausgearbeitet

---

## Verwendete Komponenten (Auswahl)

| Komponente | Hersteller | Beschreibung | VK-Preis |
|---|---|---|---|
| KR1205 | Kassow Robots / Bosch Rexroth | 7-Achsen-Kollaborativroboter, 120 cm, 5 kg | 31.500 € |
| ctrlX CORE X5/X7 + IPC | Bosch Rexroth | Industrial OS, Echtzeit-Linux, offenes App-Ökosystem | 3.700 € |
| Schunk EGK | Schunk | Standard-Zweifingergreifer, 3D-gedruckte Backen (gummiert) | 3.100 € |
| Cambrian Vision System | Cambrian | Kameramodul + CAD-basierte 6D-Pose-Erkennung, < 1 s | 17.000 € |
| Aluprofile + Verkleidung | Item | Transportabler Zellenaufbau | 3.000 € |
| Trichtervorrichtung | Eigenentwicklung | Funnel-Align-Insert für Twisted-Pair; Schutzanmeldung eingereicht | – |
| LLM-Integrationsschicht | Eigenentwicklung | Skills + Flows + CLIs; NDJSON Session-Recordings | – |

---

**Weitere Informationen:**  
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)  
[ARENA2036](https://arena2036.de)  
[Bosch Rexroth AG](https://www.boschrexroth.com)  
[ctrlX AUTOMATION](https://www.boschrexroth.com/ctrlx-automation)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*
