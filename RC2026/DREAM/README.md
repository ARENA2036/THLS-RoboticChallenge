# Dream Machines

**Dream Machines** ist ein auf Physical AI spezialisiertes Robotik-Startup mit Wurzeln an der ETH Zürich, gegründet von Dominique Paul (Mathematik & Computer Science, ETH) und Aurel Arnold (Maschinenbau, ETH).

Das Unternehmen entwickelt einen KI-basierten Ansatz zur Roboterautomatisierung, der auf Demonstration statt auf klassischer Programmierung basiert: Statt einen Roboter Schritt für Schritt zu programmieren, macht ein Bediener die gewünschte Aufgabe am realen Roboter vor. Ein vortrainiertes multimodales KI-Modell (basierend auf dem Open-Source-Modell **π0** / Pi Zero, vortrainiert auf ~25.000 Stunden Robotikdaten) erlernt daraus die Steuerungspolitik und führt die Aufgabe anschließend autonom aus. Das Ziel: Automatisierung, die von den Personen durchgeführt werden kann, die die Aufgabe bereits kennen – ohne Systemintegrator und ohne Programmierkenntnisse.

**Website:** (in Aufbau)

---

Der Beitrag von **Dream Machines** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

**Dream Machines** verfolgt einen grundlegend anderen Ansatz als klassische Robotikautomatisierung: Statt deterministischer Bewegungsprogramme setzt das Unternehmen auf ein **dreistufiges KI-Trainingsparadigma** – Vortraining auf Internetdaten, aufgabenspezifisches Finetuning durch Teleoperation und autonomes Reinforcement Learning aus eigenen Erfahrungen. Der Roboter lernt dabei aus den Kamerabildern und Gelenkwinkeln aller 14 Gelenke (7 je Arm) und generiert in Echtzeit die nächste Bewegung – ohne Blick in Vergangenheit oder Zukunft, ausschließlich basierend auf dem aktuellen Zustand.

<!-- Bild Dual-Arm-Setup auf Aluminiumprofil-Tisch hier einfügen -->

Der Demonstrator besteht aus einem kompakten Dual-Arm-System auf einem Item-Aluminiumprofil-Tisch, zwei 6-DOF-Roboterarmen mit Greifern, drei Kameras (eine Kontextkamera von oben, eine pro Hand) und einem lokalen GPU-Rechner für die Modellinferenz. Das gesamte Setup ist auf einem Rolltisch transportabel und kann am nächsten Morgen nach der Datenaufnahme autonom die Aufgabe ausführen.

Der Demonstrator umfasst unter anderem:

* **Dreistufiges KI-Training**: Vortraining (π0, ~25.000 h Robotikdaten) → aufgabenspezifisches Finetuning durch Teleoperation → autonomes Reinforcement Learning zur Taktzeitoptimierung (2–3× Beschleunigung erwartet)
* **Teleoperation durch Joystick**: Datenaufnahme durch Joystick-gesteuerte Demonstrationen; die Lernkurve für Bediener beträgt ca. 15–20 Minuten
* **Dreikamera-Setup**: eine Übersichtskamera (oben) + je eine handnahe Kamera pro Arm für präzise Feinmanipulation
* **14-Gelenkwinkel-Fusion**: Modell verarbeitet simultane Kamerabilder und alle 14 aktuellen Gelenkwinkel als einzige Eingabe – keine Trajektorienplanung, keine Kraft-Sollwerte
* **Kraftschätzung via Motorstrom**: Widerstand und Anpresskraft lassen sich über das Drehmoment-Strom-Verhältnis der Antriebe berechnen – ohne separaten Kraftsensor
* **Vollständige Prozessaufzeichnung**: jede Bewegung ist kamerabasiert aufgezeichnet und nachvollziehbar; ein separates visuelles Inspektionsmodell kann parallel auf denselben Daten laufen
* **3D-gedruckte Greifer**: anpassbar in ~10 Minuten CAD-Änderung + 1 Stunde Druckzeit; Materialkosten ca. 1 €

**Dream Machines** präsentierte einen funktionsfähigen Demonstrator, der – nach ~100 Teleoperation-Demonstrationen und 6–12 Stunden GPU-Training – ein einzelnes vorkonfektioniertes Kabel autonom greift und beidseitig in die entsprechenden Steckverbinder einsteckt.

Im Rahmen des Proof-of-Concept wurde ein einzelnes Kabel verarbeitet: Das System greift das Kabel, hält das Gehäuse mit dem zweiten Arm, und steckt beide Enden ein – vollständig visuell gesteuert, ohne vorab definierte Fügekoordinaten. Das Gesamtziel, den vollständigen Leitungssatz zu konfektionieren, wurde nicht erreicht; das Potenzial der Technologie wurde jedoch klar demonstriert.

Zum Einsatz kommen **zwei 6-DOF-Roboterarme** als Kernsystem:

* Einkaufspreis ca. **7.000 € für beide Arme** (Produktionskosten ca. 3.000 €); perspektivisch weiter sinkend
* aufgebaut auf einem Item-Aluminiumprofil-Tisch; mobil und rollbar
* Greifer: stabil (nicht elastisch), 3D-gedruckt; optimiert für Kabelhandhabung und Steckgehäuse-Griff
* lokale Inferenz über GPU (ca. **5.000 €**); alternativ cloudbasiert bei guter Netzwerkanbindung möglich (dann Gesamtstationskosten: ca. **7.000 €**); Gesamtkosten pro Station mit lokalem GPU: ca. **12.000 €**

Das **KI-Modell (π0 / Pi Zero)** basiert auf einem Open-Source-Foundation-Modell:

* Vortraining auf ca. 25.000 Stunden verschiedener Robotikdaten aus dem Internet (Bewegungsabläufe + Kamerabilder + Gelenkwinkel)
* Finetuning: ca. **100 Teleoperation-Demonstrationen** der konkreten Aufgabe, aufgenommen per Joystick; Trainingszeit: **6–12 Stunden** auf einer GPU
* Inferenz: 14 aktuelle Gelenkwinkel + 3 Kamerabilder → nächste Gelenksollwerte; Regelzykluszeit nicht spezifiziert
* KI-Daten aus dem Challenge-Paket (KBL/VEC/STEP) wurden nicht direkt verwendet; Steckerhalter wurden auf Basis der CAD-Daten (STEP) als 3D-Druckvorrichtungen abgeleitet

Der Demonstrator umfasst folgende Prozessschritte:

* vorkonfektioniertes Kabel liegt auf dem Arbeitstisch (Position und Orientierung nicht fixiert)
* Arm 1 greift das Kabelende, Arm 2 hält und positioniert das Steckgehäuse
* beide Arme bewegen sich koordiniert; der Roboter navigiert das Kabelende visuell in die Steckverbinderöffnung
* Einführen des Krimps: aktuell positionsbasiert mit visuellem Endlagenerkennung; Korrektur durch erneutes Drücken wenn nötig
* zweites Kabelende wird analog gesteckt
* kein Pull-Check implementiert; keine explizite Sekundärverriegelungsprüfung

<!-- Bild Einsteckvorgang / Kameraansicht hier einfügen -->

---

## Ergebnisse

| Kennzahl | Wert |
|---|---|
| Demonstrierter Prozess | Greifen + beidseitiges Einstecken eines einzelnen vorkonfektionierten Kabels |
| Zykluszeit (aktuell) | **~4 Minuten** (ein Kabel, beide Enden) |
| Zykluszeit-Ziel (nach Reinforcement Learning) | **< 2 Minuten** angestrebt (2–3× Beschleunigung durch RL erwartet) |
| Roboterarme | 2 × 6-DOF (Dual-Arm-System) |
| Kameras | 3 (1× Übersicht oben, 2× handnah) |
| Trainingsaufwand | ~100 Teleoperation-Demonstrationen; 6–12 h GPU-Training |
| Kraftmessung | indirekt via Drehmoment-Strom-Verhältnis (kein separater Kraftsensor) |
| Pull-Prüfung / Verrastungskontrolle | nicht implementiert |
| Gesamtkosten pro Arbeitsstation | **~12.000 €** (7.000 € Arme + 5.000 € GPU); alternativ ~7.000 € bei Cloud-Inferenz |
| Anlagen für 400.000 Stück/Jahr | nicht kalkuliert (Zykluszeit noch nicht serienreif) |

---

## Highlights & Alleinstellungsmerkmale

* **Extrem niedrige Hardwarekosten**: ~12.000 € pro vollständiger Arbeitsstation – ein Bruchteil klassischer Automatisierungslösungen
* **No-Code-Automatisierung durch Vormachen**: Mitarbeiter, die die Aufgabe kennen, können den Roboter in 15–20 Minuten einlernen – ohne Systemintegrator oder Programmierkenntnisse
* **Generalisierbares KI-Fundament (π0)**: dasselbe vortrainierte Modell kann für neue Aufgaben mit wenigen Demonstrationen feingetunt werden – progressiv für komplexere Aufgaben skalierbar
* **Vollständige Prozesstraceability**: alle Kameradaten sind aufgezeichnet; visuelle Qualitätsprüfung und Fehlerrückverfolgung auf Teilebasis möglich
* **3D-gedruckte Greifer-Ökosystem**: Greiferanpassung in ~1 Stunde; Materialkosten ~1 €; keine Spezialbeschaffung
* **Reinforcement Learning als nächste Reifestufe**: erwartete 2–3× Taktzeitreduktion ohne neue Demonstrationen – der Roboter optimiert sich aus eigener Erfahrung

---

## Offene Punkte & Ausblick

* **Zykluszeit**: 4 Minuten aktuell; Reduktion auf < 2 Minuten durch Reinforcement Learning geplant, aber noch nicht implementiert
* **Datenbasis (Vortraining)**: primäre Limitierung des Systems liegt nicht in Hardware oder Auflösung, sondern in der globalen Verfügbarkeit von Robotik-Trainingsdaten (Kamera + Gelenkwinkel kombiniert); geschätzte Lücke: Faktor ~1/100.000 gegenüber Textdaten für LLMs
* **Nano-MQS-Kontakte und Kleinstteile**: Teleoperation mit Joystick für sehr kleine Kontakte schwierig; Verbesserung durch haptische Handschuh-Systeme oder direktere Datenerfassungsmethoden geplant
* **Verrastungsprüfung**: kein Pull-Check oder Kraftmessung implementiert; für Serienreife erforderlich
* **Qualitätssicherung**: Empfehlung aus Jury-Diskussion, parallele visuelle Inspektionsmodelle und prozesstechnische Zwischenprüfschritte beizubehalten – analog zur Vertrauensentwicklung bei LLMs
* **Engineering-Daten-Integration**: KBL/VEC/STEP-Daten aus dem Challenge-Paket noch nicht für Modelltraining genutzt; Potenzial für automatisierte Vorrichtungsgenerierung und strukturierte Aufgabenparametrierung vorhanden
* **Skalierung auf vollständigen Leitungssatz**: aktuell ein Kabel, ein Steckvorgang; Gesamtprozess mit mehreren Kabeln, Modulen und Umgehäuse erfordert Multi-Task-Planung und Stationskonzept

---

## Verwendete Komponenten (Auswahl)

| Komponente | Beschreibung |
|---|---|
| Roboterarme | 2× 6-DOF-Arme; Einkaufspreis ~7.000 € für beide |
| KI-Modell | π0 (Pi Zero), Open-Source, vortrainiert auf ~25.000 h Robotikdaten |
| Trainingsdaten | ~100 Teleoperation-Demonstrationen per Joystick |
| Kameras | 3× (1 Übersicht + 2 handnah) |
| Inferenz-Hardware | lokale GPU (~5.000 €) oder Cloud-basiert |
| Greifer | 3D-gedruckt, aufgabenspezifisch; Materialkosten ~1 €; Anpassung in ~1 h |
| Aufbau | Item-Aluminiumprofil-Tisch; mobil, rollbar |
| Datenaufnahme | Joystick-Teleoperation; Lernkurve ~15–20 min für neue Bediener |

---

## Dateien

| Datei | Typ | Beschreibung | Link |
|---|---|---|---|
| **`README.md`** | Markdown | Diese Projektdokumentation | [Öffnen](README.md) |

---

**Weitere Informationen:**  
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)  
[ARENA2036](https://arena2036.de)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*
