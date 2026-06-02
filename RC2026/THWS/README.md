# <img width="1771" height="144" alt="image" src="https://github.com/user-attachments/assets/7ed39694-a6df-46e0-911f-f1f0672cb5cc" />


**THWS, RWU, IFB und IILS** entwickelten im Rahmen der **Robotik Challenge 2026** Konzepte zur automatisierten Montageplanung, Bahnplanung und robotischen Leitungssatzmontage.

Der Fokus liegt auf der durchgängigen digitalen Prozesskette — von der KBL-basierten Beschreibung des Leitungssatzes über die automatische Pfad- und Montageplanung bis zur Ausführung auf realen Robotersystemen.

---

Der Beitrag zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Arbeiten ist die Entwicklung automatisierter Verfahren für:

* robotische Leitungssatzmontage
* automatische Pfadplanung
* Kollisionserkennung
* kamerabasierte Kabelerkennung
* adaptive Bahnplanung
* digitale Fabrik- und Prozessmodelle

Die entwickelten Methoden verbinden Engineering-Datenformate wie **KBL**, CAD-Modelle sowie KI-basierte Bildverarbeitung mit realen Robotersystemen.

<p align="center">
<img width="1110" height="631" alt="image" src="https://github.com/user-attachments/assets/1e495a95-7a9f-45b4-9922-b96df180e76f" />
</p>

---

## Demonstrator

Der Demonstrator umfasst:

* Montageplanung im Design Compiler 43® (DC43®)
* automatische Generierung von Pfaden aus KBL-Daten
* robotische Bahnplanung und Trajektoriengenerierung
* Kollisionserkennung mittels Bounding-Boxen
* Ausführung auf realen Robotersystemen
* kamerabasierte Erkennung von Kabelorientierung und Verdrehung
* automatische Pfadanpassung bei KBL-Modifikationen

---

## Technologiebausteine

### KBL-basierte Datenmodelle

Die Leitungssatzdaten werden aus KBL-Dateien extrahiert und sowohl als Klassendiagramm als auch als Graphstruktur verarbeitet. Daraus werden automatisiert Montage- und Pfadinformationen abgeleitet.

### Robotik-Toolbox

Die entwickelte Robotik-Toolbox unterstützt:

* Denavit-Hartenberg-Modellierung
* Forward Kinematics
* Inverse Kinematics
* Trajektorienplanung

### KI-basierte Bildverarbeitung

Für die Lage- und Verdrehungserkennung der Kabel kommen kamerabasierte Verfahren mit YOLOv11-Pose und YOLOv11-Segmentation zum Einsatz.

### Adaptive Montageplanung

Änderungen an KBL-Daten können automatisiert erkannt und in aktualisierte Roboterpfade überführt werden.

---

## Dateien

| Datei                                              | Typ      | Beschreibung                                                    | Link                                                   |
| -------------------------------------------------- | -------- | --------------------------------------------------------------- | ------------------------------------------------------ |
| **`README.md`**                                    | Markdown | Diese Projektdokumentation                                      | [Öffnen](README.md)                                    |
---

Die Arbeiten zeigen einen durchgängigen Ansatz zur automatisierten Leitungssatzmontage — von der Engineering-Datenbasis bis zur adaptiven Ausführung auf realen Robotersystemen.

---

**Beteiligte Partner:**

* Technische Hochschule Würzburg-Schweinfurt (THWS)
* Hochschule Ravensburg-Weingarten (RWU)
* Institut für Fördertechnik und Logistik (IFB)
* IILS mbH

---

## Weiterführende Links

* Design Compiler 43® (DC43®)
  https://www.iils.de

* DC43® Harness
  https://www.iils.de/en/product/dc43_harness/#dc43_harness

* ARENA2036 Transformations-Hub Leitungssatz
  https://www.leitungssatz-hub.de/technologien/3d-kabelbaumentwurf-automatisieren/

* Vision-Driven Robotic Cable Insertion
  https://am-robo-projects.github.io/cableOrienter/

* [Dissertation zum Kabelbaumentwurf](https://elib.uni-stuttgart.de/items/c389b615-7987-461f-9e97-c0ea62a1f0e3)

* [Forschungsprojekt FORTIFIER der Universität Stuttgart](https://www.era-learn.eu/network-information/networks/manunet-iii/manunet-call-2020/aritifical-intelligence-enhanced-digital-factory-twins-for-wire-harness-manufacturing)

---

## Ansprechpartner

**Philipp Kranz**
[philipp.kranz@thws.de](mailto:philipp.kranz@thws.de)

**Timo Schuchter**
[timo.schuchter@rwu.de](mailto:timo.schuchter@rwu.de)

**PD Dr.-Ing. Stephan Rudolph**
[rudolph@ifb.uni-stuttgart.de](mailto:rudolph@ifb.uni-stuttgart.de)

**Dr.-Ing. Roland Weil**
[roland.weil@iils.de](mailto:roland.weil@iils.de)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*

