# <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/75bbe4b9-c0a3-4a96-bf6f-53f2d0f582bd" />


**EKS InTec GmbH & Co. KG** ist ein Engineering- und Technologieunternehmen mit Sitz in Weingarten, spezialisiert auf digitale Anlagenplanung, virtuelle Inbetriebnahme und industrielle Automatisierungslösungen.

Das Unternehmen begleitet den vollständigen Lebenszyklus von Produktionsanlagen – von der ersten Planung über die Simulation und virtuelle Inbetriebnahme bis hin zu Betrieb, Wartung und Optimierung. EKS InTec arbeitet eng mit dem Mutterkonzern **FFT Produktionssysteme GmbH & Co. KG** zusammen und ist unter anderem in der Karosseriefertigung, Batteriemontage und Leichtbauproduktion tätig.

**Website:** https://www.eks-intec.de

---

Der Beitrag von **EKS InTec** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

**EKS InTec** verfolgt einen industriell erprobten, volldigitalen Ansatz: Statt eines reinen Demonstrations-Setups wurde die Zelle behandelt wie ein reales Kundenprojekt – inklusive Taktzeit-Analyse, Sicherheitskonzept, CE-Zertifizierungsplanung, Kostenkalkulation und virtueller Inbetriebnahme. Als Kalkulationsrahmen wurde der Mutterkonzern FFT als fiktiver Auftraggeber und Anlagenbauer gesetzt.

<!-- Bild Gesamtanlage hier einfügen -->

Der Demonstrator basiert auf einer umhausten, vollautomatisierten Roboterzelle mit drei kollaborierenden Robotern, einem 180°-Drehtisch und kameragestützter Positionserkennung. Über Stauförderanlagen werden Stecker und Kabel zugeführt; ein Werker befüllt die Anlage in entkoppelten Zeitfenstern.

Der Demonstrator umfasst unter anderem:

* vollautomatische Zuführung von Steckern und Kabeln über Stauförderanlagen mit ca. 45 Minuten Entkopplungspuffer
* Positionierung der Stecker in geometrisch definierte Formnester auf einem 180°-Drehtisch
* kameragestütztes Greifen und Fügen der Kabel durch zwei kollaborierende Roboter (ABB)
* Kraftüberwachung beim Fügevorgang sowie optionale Pull-Prüfung zur Verrastungskontrolle
* automatisches Verriegeln der Kontakte und Bündeln mit einer permanent montierten Kabelbinderpistole
* parametrierbare Roboterprogramme für verschiedene Leitungssatz-Derivate und Kabellängen (800 mm / 1000 mm demonstriert)
* vollständige virtuelle Inbetriebnahme (Siemens Process Simulate + ABB RobotStudio + Codesys Soft-SPS)
* Operator-Training über simulierte Fehlereinstreu-Szenarien und Nvidia Omniverse-Integration

**EKS InTec** präsentierte eine vollautomatisierte, industriell ausgelegte Leitungssatzmontage-Zelle mit einer Zielzykluszeit von **185 Sekunden** bei drei Robotern und einem Werker zur Anlagenbedienung.

Im Rahmen des Konzepts wurden fünf Leitungstypen (Coax, FLRY 1,5 mm², FLRY 0,13 mm², UTP/Twisted-Pair sowie ein Doppelkabel) und acht Steckverbinder-Komponenten verarbeitet. Ziel war der Nachweis einer prozesssicheren, serienfähigen Vollautomatisierung auf Basis industrieller Engineering-Methoden – von der digitalen Montage-Spezifikation bis zur virtuellen Inbetriebnahme.

**Verarbeitete Bauteile (gemäß Taktzeitdiagramm):**

| Bauteil | Typ | Artikelnummer |
|---|---|---|
| Stecker 10-pol | Steckverbinder | 1418796-3 |
| Stecker 2-pol | Steckverbinder | 2302475-1 |
| Stecker 1-pol | Steckverbinder | 2-2310137-1 |
| Stecker Modul 1 (4-pol) | MCP2.8-Modul | 2470646-9 |
| Stecker Modul 2 (4-pol) | MCP2.8-Modul | 2470648-9 |
| Stecker Modul 3 (4-pol) | MATE-AX-Modul | 2470653-9 |
| Umgehäuse (6-fach) | Gehäuse | 2470829 |
| Cover | Deckelkomponente | 2470839-1 |
| Kabel 1–4 | FLRY 1,5 mm², Coax, UTP, FLRY 0,13 mm² | – |
| Kabel 5 (Doppel) | FLRY 1,5 mm² | – |

Zum Einsatz kommen **drei kollaborierende ABB-Roboter** als Kernkomponenten der Zelle:

* **Roboter 020IR001 (Bestückungsroboter)**: Entnimmt alle Stecker einzeln per QR-Code-Scan aus der Zuführpalette (Station 010) und positioniert sie in den Formnestern auf dem Drehtisch (Station 030); übernimmt nach Drehtisch-Rotation das Aufsetzen des Deckels auf das Umgehäuse sowie die Bauteilentladung in Station 060 – Gesamtdauer im Zyklus: **177,5 s**
* **Roboter 050IR001 (Fügeroboter 1)**: Entnimmt aus der Kabelzuführung (Station 040) nacheinander je eine Seite der Kabel 1–5, scannt den Kabeltyp, legt die Kabel in die Clips der Vorrichtung (Station 030), prüft den Sitz, schließt die Sekundärverriegelung und fügt abschließend die drei Steckermodule in das Umgehäuse – Gesamtdauer im Zyklus: **177,5 s**
* **Roboter 050IR002 (Fügeroboter 2, spiegelbildlich parallel)**: Arbeitet synchron zu Roboter 050IR001 für die gegenüberliegenden Kabelenden (Kabel 1–5 je Seite); übernimmt zusätzlich das Kabelbündeln alle 50 mm über 1200 mm Kabellänge (ca. 24 s) – Gesamtdauer aktiv: **134 s**, danach Wartezeit bis zur nächsten Drehtisch-Freigabe

Für die Leitungshandhabung wurde ein **CFK-Freiformgreifer (Eigenentwicklung EKS/FFT)** verwendet:

* Leichtbauausführung aus kohlenstofffaserverstärktem Kunststoff (CFK) für minimale Robotertraglast
* geometrisch auf die Produktdaten (CAD) ausgelegt
* kompatibel mit allen drei Leitungstypen

Die Positionserkennung und Fügequalität werden über **kameragestützte Bildverarbeitung** sichergestellt:

* Kamera am Greifer zur Lageerkennung der Kabelenden in der Zuführpalette
* Korrekturfähigkeit für Lage- und Winkelabweichungen vor dem Fügevorgang
* Formnester auf dem Drehtisch gewährleisten präzise Steckerpositionierung ohne zusätzliche Kamerakorrektur
* Kraftüberwachung beim Fügen; Verrastungsprüfung über Gegenkraft-Messung (Pull-Check)

Die digitale Grundlage bildet eine **Digitale Montage-Spezifikation (DMS)** im Asset-Administration-Shell (AAS)-Format:

* strukturierte Beschreibung aller Prozessschritte, Fügefolgen und Parameter auf Basis von KBL/VEC-Daten
* hierarchische Stückliste zur Abbildung von Varianzen und Parallelisierungsmöglichkeiten
* Variantenvergleich über integriertes Datenmanagement-Tool (AAS-Diff-Funktion)
* Exportfähigkeit in Richtung Digitaler Produktpass (DPP) und AutomationML

Der Demonstrator umfasst folgende **Prozessschritte** (Zeitangaben aus dem Taktzeitdiagramm, Skalierung 15,0 s/Einheit):

* **1.** (0–50 s) – Werker belädt Station 010 mit Steckerpalette (10 s); geht zu Station 060 (8 s); entnimmt fertige Bauteile (11 s); kehrt zu Station 010 zurück (8 s); wartet (9 s)     
* **2.** (0–177,5 s) – Roboter 020IR001 entnimmt nacheinander alle 8 Stecker-/Gehäusekomponenten mit QR-Code-Scan aus Station 010 und positioniert sie einzeln in den Formnestern auf dem Drehtisch (Station 030); Deckel und Block-Bauteile werden separat behandelt und in Station 060 ausgeschleust     
* **3.** (0–177,5 s) – Roboter 050IR001 entnimmt parallel die Kabelenden 1–5 aus Station 040 (je Kabelscan, Greifen, Einlegen in Clips, Clip-Check, Sekundärverriegelung) und fügt anschließend die drei Steckermodule (MATE-AX, MCP2.8 links, MCP2.8 rechts) in das Umgehäuse ein
* **4.** (0–134 s) – Roboter 050IR002 arbeitet spiegelbildlich synchron zu 050IR001 für die gegenüberliegenden Kabelenden; führt nach Abschluss das Kabelbündeln alle 50 mm über 1200 mm Kabellänge durch (~24 s); wartet danach auf Drehtisch-Freigabe
* **5.** (177,5–183,5 s) – Drehtisch rotiert 180° (6 s) und präsentiert den fertig bestückten Leitungssatz
* **6.** (183,5–185 s) – Zyklus-Ende; ab dem 2. Zyklus laufen Drehtisch-Bestückung und Fügen parallel → **Zykluszeit 185 s**
* **7.** Fehlerhafte Bauteile werden über eine NEO-Strategie ausgeschleust oder dem Werker zur manuellen Nacharbeit übergeben



<!-- Bild Drehtisch / Formnester hier einfügen -->

---

## Ergebnisse

| Kennzahl | Wert |
|---|---|
| Zielzykluszeit | **185 s** (ab 2. Zyklus durch Drehtisch-Parallelisierung) |
| Taktzeit Bestückungsroboter 020IR001 | **177,5 s** (8 Komponenten mit QR-Scan + Entladung) |
| Taktzeit Fügeroboter 050IR001 | **177,5 s** (5 Kabel + 3 Steckermodule in Umgehäuse) |
| Taktzeit Fügeroboter 050IR002 | **134 s** aktiv (5 Kabel + Kabelbündeln alle 50 mm / 1200 mm) |
| Drehtisch-Rotationszeit | 6 s (180°) |
| Eingesetzte Roboter | 3 (020IR001 Bestückung + 050IR001/002 Fügen) |
| Werkzeugwechsel | keiner (Kabelbinderpistole permanent montiert) |
| Kamerasystem | ja (greiferseitig: Kabeltyp-Scan + Lageerkennung) |
| QR-Code-Verifikation | je Stecker vor Einlegen in Formnest |
| Sekundärverriegelungen | automatisch nach Kabeln 1+2, 3+4 und 5 (3× im Zyklus) |
| Werker-Entkopplungszeit | ~45 Minuten (Entnahmeband Station 060) |

---

## Digitalisierungskonzept

EKS InTec legte besonderen Fokus auf die durchgängige Digitalisierung des Engineering-Prozesses:

* **Digitale Montage-Spezifikation (DMS)** im AAS-Format als maschinenlesbare Grundlage für parametrierbare Roboterprogramme
* **Ablauf- und Erreichbarkeitssimulation** in Siemens Process Simulate
* **3D-Geometrie- und Kinematiksimulation** in ABB RobotStudio
* **Virtuelle Inbetriebnahme** mit übergeordneter Codesys Soft-SPS (Schrittketten, Sicherheitslogik)
* **Operator-Training** mit simulierten Fehlerszenarien (vor physischem Aufbau)
* **Metaverse-Integration** via Nvidia Omniverse (kollaborative Live-Kopplung möglich)
* **Prozessanalyse & DPP-Export** in AutomationML-Format für nachgelagerte Nutzung


---

**Weitere Informationen:**  
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)  
[ARENA2036](https://arena2036.de)  
[EKS InTec GmbH & Co. KG](https://www.eks-intec.de)  
[FFT Produktionssysteme GmbH & Co. KG](https://www.fft.de)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*
