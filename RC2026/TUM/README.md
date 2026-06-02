# <img width="65" height="40" alt="image" src="https://github.com/user-attachments/assets/9da41f28-48e6-4507-bdf8-a4edd763ac5d" />


Das **Institut für Werkzeugmaschinen und Betriebswissenschaften (IWB)** der **Technischen Universität München (TUM)** ist ein führendes Forschungsinstitut im Bereich Montagetechnik und Robotik mit Sitz in München.

Das Institut beschäftigt sich mit der Erschließung neuer Automatisierungsfelder – insbesondere der robotergestützten Handhabung und Montage von Leitungen – sowie mit der Vereinfachung von Roboterprogrammierung für industrielle Anwendungen. Das Forschungsprojekt **ROLEI** (Roboterbasiertes Verlegen von Leitungen) bildet die wissenschaftliche Grundlage des Challenge-Beitrags.

**Website:** https://www.mec.ed.tum.de/iwb/

---

Der Beitrag des **IWB TUM** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

Das **IWB TUM** verfolgt einen Ansatz, der bewusst auf Kamerasysteme verzichtet: Statt bildbasierter Lageerfassung setzt das Institut auf geometrisch definierte Bereitstellungsvorrichtungen und einen selbst entwickelten **Doppelgreifer** mit integrierten Formnestern für alle Leitungstypen. Alle Fügeoperationen erfolgen kraftgeregelt, Suchbewegungen über eine Spiralsuche.

<img width="1789" height="955" alt="image" src="https://github.com/user-attachments/assets/f3881ff9-c6d7-4a49-b6fe-ae925b98c084" />

Der Demonstrator basiert auf einem einzelnen kollaborativen Roboter (MRK-fähig), einem Eigenentwicklungs-Doppelgreifer und definierten Bereitstellungsvorrichtungen. Der Roboter entnimmt Leitungen, fügt Krimkontakte und Stecker ein, schließt Sekundärverriegelungen und Deckel und bündelt den fertigen Leitungssatz mit einem HellermannTyton-Kabelbündelungssystem.

Der Demonstrator umfasst unter anderem:

* kraftgeregeltes Einstecken von Krimkontakten in Steckverbinder und Ungehäuse
* simultanes Fügen von zwei Krimkontakten in einem Arbeitsschritt (Doppelgreifer)
* automatisches Schließen von Sekundärverriegelungen und Deckeln
* Spiralsuche zur robusten Lagefindung bei Fügefehlern
* automatisiertes Bündeln des Leitungssatzes mit einem aufnehmbaren Kabelbündelungssystem
* konsistente Maßhaltigkeit des produzierten Leitungssatzes über mehrere Wiederholungen

Das **IWB TUM** präsentierte eine vollständige, kamerafreie Konfektionierung eines Leitungssatzmoduls mit einem einzigen Roboter in **3 Minuten 19 Sekunden**.

Im Rahmen des Demonstrators wurden ein Koaxkabel, ein verdrilltes Kabel sowie eine Dünnleitung verarbeitet. Ziel war der Nachweis, dass durch definierte Bereitstellung und kraftgeregelte Bewegungsführung eine robuste Automatisierung ohne kostenintensive Bildverarbeitung möglich ist.

Zum Einsatz kam ein **kollaborativer Roboter** (MRK-fähig) als Plattform.

Die Fügebewegungen werden durch **kraftgeregelte Robotersteuerung** mit positionsbasierter Enddetektion realisiert:

* Einstecken bis zum Anschlag mit Kraftüberwachung
* automatische Spiralsuche bei erhöhter Gegenkraft (verfehlte Buchse)
* Nachschieben über den hinteren Greifer bei Dünnleitungen

Für die Leitungshandhabung wurde ein **Doppelgreifer (Eigenentwicklung IWB)** verwendet:

* zwei unabhängige Greifereinheiten (vorderer und hinterer Greifer)
* geometrisch definierte Formnester in den Greiferbacken (3D-gedruckt, gummiert beschichtet)
* separate Aufnahmen für verschiedene Krimkontakttypen und das Koaxkabel
* kein Werkzeugwechsel für Kontakte, Stecker oder Deckel erforderlich

Die Bereitstellung der Leitungen erfolgt über **definierte Bereitstellungsvorrichtungen**:

* festgelegte Position und Orientierung aller Krimkontakte ohne Kameraerkennung
* automatisches Schließen der Sekundärverriegelung beim Entnehmen (integrierte Schräge)
* reproduzierbare Maßhaltigkeit des fertig produzierten Leitungssatzes

Der Demonstrator umfasst folgende Prozessschritte:

* Entnahme der Leitungen aus definierten Bereitstellungsvorrichtungen
* kraftgeregeltes Einstecken der Krimkontakte in Steckverbinder
* Fügen der bestückten Stecker in das Ungehäuse
* Schließen von Sekundärverriegelung und Deckel
* Aufnahme des Kabelbündelungssystems und Bündeln des Leitungssatzes an vordefinierten Stellen
* Ablage des fertigen Leitungssatzmoduls

<!-- Bild Prozessübersicht hier einfügen -->

---

## Ergebnisse

| Kennzahl | Wert |
|---|---|
| Zykluszeit (Demonstrator) | **3 min 19 s** |
| Eingesetzte Roboter | 1 |
| Werkzeugwechsel | 1 (Kabelbündelungssystem) |
| Kamerasystem | keines |
| Erfolgsrate (letzte 5 Wiederholungen) | **100 % störungsfrei** |
| Gesamt-Erfolgsrate (Gesamtversuchsreihe) | > 85 % |
| Wirtschaftlichkeit (Break-even) | ab ca. 26.400 Leitungssätzen/Jahr |

---

## Dateien

| Datei | Typ | Beschreibung | Link |
|---|---|---|---|
| **`README.md`** | Markdown | Diese Projektdokumentation | [Öffnen](README.md) |

---

**Weitere Informationen:**  
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)  
[ARENA2036](https://arena2036.de)  
[IWB – TU München](https://www.mec.ed.tum.de/iwb/)

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*
