# <img width="180" alt="mowito logo" src="https://cdn.prod.website-files.com/61b318e08b693e2bd64e9a90/65ded674eabb951dca601555_MW_LOGO_H_COLOR_NT.svg" />

**mowito** ist ein Physical-AI-Unternehmen für die Fertigungsindustrie, gegründet 2024, mit Sitz in Detroit. Das Unternehmen entwickelt KI-Software, die Industrieroboter befähigt, komplexe Montageaufgaben aus menschlichen Demonstrationen zu erlernen und mit produktionsreifer Präzision autonom auszuführen.
 
Kern der Technologie ist ein proprietärer **Physical-AI-Stack**, der Imitation Learning, Reinforcement Learning, Computer Vision und Echtzeit-Robotersteuerung kombiniert. Statt monatelanger Roboterprogrammierung lernen Roboter direkt von erfahrenen Bedienern und passen sich kontinuierlich an reale Fabrikbedingungen an. mowito ist bereits auf sechs Live-Produktionslinien bei führenden Unternehmen im Einsatz – darunter Foxconn (Elektronikmontage) und Denso (Fortune-500-Automobilzulieferer). Das Unternehmen wird von führenden KI- und Robotikinvestoren unterstützt, darunter Soumith Chintala, CTO von Thinking Machines. Gründer Puru Rastogi und Safar vereinen über 17 Jahre kombinierte Erfahrung in Robotik und Industrieautomation; Mitgründer Adityanag Nagesh ist Serial Entrepreneur und baut mit mowito sein drittes Startup.

**Website:** https://mowito.ai, https://www.youtube.com/@mowito7248

---

Der Beitrag von **mowito** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

**mowito** verfolgt einen grundlegend anderen Ansatz als klassische Robotikautomatisierung: Statt vordefinierter Trajektorien setzt das Unternehmen auf ein **lernbasiertes Physical-AI-Modell (NeuralStack)**, das durch Demonstration von Fabrikarbeitern trainiert und ohne Programmierkenntnisse rekonfiguriert werden kann. Kernstück ist der selbst entwickelte **NeuralGripper** – ein 4-DOF-Zweifingergreifer mit taktilen Sensoren an den Fingerspitzen, der sowohl die Lage des Krimpendes am Kabelende kontinuierlich lokalisiert als auch eine In-Hand-Manipulation des flexiblen Kabels ermöglicht.

<img width="1625" height="1020" alt="image" src="https://github.com/user-attachments/assets/fb9175f3-317b-4497-8c1b-7018a8f27f80" />


Der Demonstrator basiert auf einem Dual-Arm-System mit zwei UR-Roboterarmen, jeweils einem NeuralGripper, statischen Zweifingergreifern zur Kabelhalterung, statischen 2D-Kameras und einem automatischen HellermannTyton-Kabelbindewerkzeug. Das Systemkonzept wurde vollständig als physischer Demonstrator aufgebaut und in Betrieb genommen.

Der Demonstrator umfasst unter anderem:

* **Taktile Krimplokalisierung**: Der NeuralGripper fährt entlang des gehaltenen Kabels und ermittelt über das taktile Sensorbild die exakte Relativlage des Krimpendes zum Endeffektor – ohne externe Positionserkennung
* **In-Hand-Manipulation von Kabeln**: Ein trainiertes „Pinch-and-Roll"-Steuerungsmodell korrigiert die Rotationsorientierung des Krimps um die Kabelachse – auch bei Fehlern größer als 60°
* **Lernbasierte Steuerung (NeuralStack)**: Kombinierter Einsatz eines KI-generierten Steuerungsmodells (taktil + visuell) für die Lokaliserungsphase und klassischer Trajektorienplanung für den deterministischen Fügepfad
* **Demonstration statt Programmierung**: 10–15 manuelle Demonstrationen am realen Roboter genügen, um eine neue Aufgabe zu trainieren – durchführbar von Fabrikarbeitern ohne Robotikkenntnisse
* **Automatisches Kabelbündeln**: Integration des HellermannTyton-Kabelbindewerkzeugs am linken Arm für Kabelbinder-Setzung alle 50 mm
* **Erweiterbar auf Bin-Picking**: Die bestehende Hardware ist prinzipiell in der Lage, Kabel direkt aus einem ungeordneten Behälter zu vereinzeln, ohne separaten Zuführmechanismus

**mowito** präsentierte einen funktionsfähigen physischen Demonstrator für die vollständige Krimplokalisierung und taktilgeführte Ausrichtung sowie das Einstecken eines einzelnen Kabels in seinen zugehörigen Steckverbinder.

Im Rahmen eines Proof-of-Concept wurde die vollständige Verarbeitung einer einzelnen Litze demonstriert – von der Lokalisierung des Krimpendes über die taktile Orientierungskorrektur bis zum Einführen in den Steckverbinder. Das Ziel, den gesamten Leitungssatz zu konfektionieren, wurde im Rahmen der Challenge aufgrund mechanischer und datentechnischer Herausforderungen noch nicht vollständig erreicht.

Zum Einsatz kommen **zwei Universal-Robots-Arme (Dual-Arm-System)** mit je einem NeuralGripper als Kernelement:

* jeder NeuralGripper besteht aus 2 Fingern mit je 2 Freiheitsgraden (4 DOF gesamt)
* an der Spitze jedes Fingers sitzt ein **GelSight-Taktilsensor** (Silikon-Membran mit eingebetteter Kamera
* der linke Arm trägt zusätzlich das HellermannTyton-Kabelbindewerkzeug (permanent montiert)
* stationäre Zweifingergreifer halten das Kabel in definierter Ausgangslage zur Aufnahme durch den NeuralGripper

Die **Wire-End-Lokalisierung** erfolgt zweistufig über taktiles und visuelles Feedback:

* der Greifer fährt zum Beginn des statischen Greifers und gleitet mit variierender Greifkraft entlang des Kabels
* das taktile Sensorbild zeigt die Verformung der Silikonmembran durch das Kabel und die Crimp-Kontur
* das KI-Modell vergleicht das aktuelle Sensorbild mit dem Referenzbild und berechnet die notwendige Fingerbewegung, bis das Krimpende reproduzierbar in einer definierten Relativlage zum Endeffektor liegt
* Kalibrierung des Sensors bei Materialveränderung der Silikonmembran über eine dedizierte Kalibriermethode

Der Demonstrator umfasst folgende **Prozessschritte**:

* Einlegen eines einzelnen Kabels in die statischen Zweifingergreifer (Ausgangsorientierung beliebig)
* beide Roboterarme mit NeuralGripper lokalisieren jeweils ein Krimpende taktil und visuell
* bei Rotationsfehlern >60° führt der NeuralGripper eine In-Hand-Manipulation durch (Pinch-and-Roll)
* Einführen der Krimps in die vorpositionierten Steckverbinder (Steckerpositionen sind vorgelehrt und fest)
* Schließen von Sekundärverriegelungen durch denselben Greifer
* Einsetzen bestückter Stecker in das Umgehäuse über taktiles Feedback
* automatisches Setzen von Kabelbindern alle 50 mm mit dem HellermannTyton-Werkzeug

<!-- Bild NeuralGripper / Taktilsensor-Ausgabe hier einfügen -->

---

## Ergebnisse

| Kennzahl | Wert |
|---|---|
| Demonstrierter Prozess | Lokalisierung + Orientierungskorrektur + Einstecken einer einzelnen Litze |
| Erwartete Zykluszeit (vollständiger Leitungssatz, 1 Anlage) | **~4 Minuten** |
| KI-Steuerungszykluszeit | ~200 ms (Sensorfusion + Greiferbewegungsberechnung) |
| Roboterarme | 2 (Dual-Arm, Universal Robots) |
| Greifer | NeuralGripper (4-DOF, Eigenentwicklung) + statische 2-Finger-Greifer |
| Taktilsensor | GelSight |
| Kamerasystem | 2× statische 2D-Kameras + taktile Kamera in jedem Greiferfinger |
| Werkzeugwechsel | keiner (HellermannTyton-Kabelbindewerkzeug permanent montiert) |
| Trainingsaufwand pro Aufgabe | 10–15 manuelle Demonstrationen |


---

## Highlights & Alleinstellungsmerkmale

* **No-Code-Robotik**: Fabrikarbeiter können neue Leitungssatz-Varianten durch Demonstration einlernen – kein Roboterprogrammier-Know-how erforderlich
* **Taktile Krimplobalisierung**: Erstmalige Nutzung von GelSight-Taktilsensorik zur kontinuierlichen Lagebestimmung von Krimps relativ zum Endeffektor – ohne externe Kamera oder Vorrichtung
* **In-Hand-Manipulation flexibler Kabel**: KI-basierte Rotationskorrektur des Krimps im Greifer kompensiert Orientierungsfehler >60° – eine Fähigkeit, die klassische Robotik mit 6-DOF-Kinematik nicht abdecken kann
* **Erweiterbar auf ungeordnete Zuführung**: Dieselbe Hardware kann prinzipiell Kabel direkt aus dem Schüttbehälter vereinzeln

---

## Offene Punkte & Ausblick

* **Mechanische Reife des NeuralGrippers**: Getrieberückspiel und Maßabweichungen durch 3D-Druck reduzieren die Wiederholgenauigkeit – Übergang zu gefrästen Metallbauteilen geplant
* **Datenbasis erweitern**: Mehr Variation im Trainingsdatensatz (insbesondere reale Taktilsignale statt simulationsbasierter Daten) für robusteres Modellverhalten
* **Zykluszeit-Optimierung**: Reduktion der KI-Regelzykluszeit (derzeit ~200 ms) durch leistungsfähigere GPU-Hardware
* **Twisted-Pair-Handling**: Konzept zum Separieren und Einzelverarbeiten der beiden Adern über In-Hand-Manipulation vorhanden, noch nicht erprobt
* **Produktisierung**: Integration in Serienproduktion erfordert Archivierung von Steuerungsmodellen pro Leitungssatz-Variante und skalierbare Deployment-Infrastruktur
* **Sensorlebensdauer**: Langzeitverhalten der GelSight-Silikonmembran bei Krimpentkontakt noch nicht abschließend validiert; Kalibriermethode für materialbedingte Drift vorhanden

---

## Verwendete Komponenten (Auswahl)

| Komponente | Beschreibung |
|---|---|
| Roboter | 2× Universal Robots (Dual-Arm-System) |
| NeuralGripper | Eigenentwicklung mowito, 4-DOF-Zweifingergreifer, 3D-gedruckt |
| Taktilsensor | GelSight (Silikon-Membran + eingebettete Kamera, je Finger) |
| KI-Modell | Mowito-NeuralStack (multimodal: taktil + visuell + Gelenkwinkel) |
| Kabelbindewerkzeug | HellermannTyton (automatisch, permanent am linken Arm) |
| Steckerhalter | 3D-gedruckte Vorrichtungen auf Basis bereitgestellter CAD-Daten (STEP/KBL) |
| Kameras | 2× statische 2D-Kameras |

---

## Dateien

| Datei | Typ | Beschreibung | Link |
|---|---|---|---|
| **`README.md`** | Markdown | Diese Projektdokumentation | [Öffnen](README.md) |
| **`mowito_Robotik_presentation.pdf`** | PDF | Präsentation mit Systemkonfiguration, Prozessschritten und Videos | [Öffnen](mowito_Robotik_presentation.pdf) |
| **`Wire_harness_assembly_by_Mowito.pdf`** | PDF | Technische Lösungsbeschreibung: Hardware, NeuralGripper-Innovationen, Trainingsmethodik | [Öffnen](Wire_harness_assembly_by_Mowito.pdf) |

---

**Weitere Informationen:**  
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)  
[ARENA2036](https://arena2036.de)  
[mowito robotics](https://mowito.ai)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*
