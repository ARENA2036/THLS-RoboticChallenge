
# <img width="196" height="50" alt="image" src="https://wemonte.de/media/f4/28/16/1694188630/logo.svg" />

**wemonte AG** ist ein innovativer Entwicklungspartner für prozesssichere Prüftechnik mit Sitz in Stuttgart.

Das Unternehmen entwickelt und fertigt elektrische Prüfadapter und Testsysteme für Anwendungen in Automotive, E-Mobility, Kabelkonfektion und Automatisierungstechnik. Dabei kombiniert wemonte digitale Prozesse, additive Fertigung und klassische Engineering-Methoden zur Entwicklung moderner Prüf- und Automatisierungslösungen.

**Website:** https://wemonte.de

---

Der Beitrag von **wemonte** zur **Robotik Challenge 2026** des **Transformations-Hub Leitungssatz** (gefördert vom BMWK) für das [**Begleitforschungs- und Digitalisierungsmodul**](https://www.leitungssatz-hub.de/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/) ist in diesem Repository hinterlegt zur transparenten Bereitstellung der Challenge-Daten und Förderung des offenen Innovationsaustauschs.

Ziel der Challenge ist die Entwicklung innovativer, robotergestützter Lösungen für die (teil-)automatisierte Montage von Leitungssätzen (Wire Harness).

**wemonte** verfolgt dabei einen bewusst alternativen Ansatz zur klassischen Robotik: Statt eines ortsfest installierten Industrieroboters setzt das Unternehmen auf eine autonom fliegende Drohne mit angedocktem Greifer- und Achsensystem zur flexiblen Leitungssatzmontage.

<img width="771" height="591" alt="Wemonte_Drohne" src="https://github.com/user-attachments/assets/29102be1-5677-431d-b93e-183bc750c3c8" />

Der Demonstrator basiert auf einer innenraumtauglichen Drohne mit eigenem Lokalisierungsverfahren, definierten Wegpunkten sowie zentraler Steuer- und Kommunikationseinheit. Die Drohne greift vorkonfektionierte Litzen, transportiert diese autonom zwischen verschiedenen Stationen und führt Steck- bzw. Fügeoperationen mittels integriertem Manipulator aus.

Der Demonstrator umfasst unter anderem:

* autonome Navigation im Innenraum
* Greifen und Transportieren konfektionierter Leitungen
* robotische Steckung von Kontakten
* Feinpositionierung über ein integriertes Achsensystem
* Transport bestückter Module zwischen verschiedenen Montagestationen
* 
**wemonte** präsentierte eine drohnengestützte, automatisierte Leitungssatzmontage zur robotischen Steckung von Kabeln.

Im Rahmen eines Proof-of-Concepts wurde die automatisierte Steckung einer 1,5 mm²-Litze in ein Steckermodul demonstriert. Ziel war die Entwicklung eines flexiblen, fliegenden Handhabungssystems für Montage- und Steckprozesse.

Zum Einsatz kam eine **DJI Mini 4 Pro** als ultraleichte Drohnenplattform (<250 g).

Die Steckbewegung wird durch einen schrittmotorbasierten Linearantrieb realisiert:

* einachsige Verschiebung des Greifers
* kontrolliertes Einstecken und Abziehen der Leitung

Für die Leitungshandhabung wurde ein **Micro-Gripper mit Servoantrieb** und angepasster Positionsrückmeldung verwendet.

Die Orientierung und Positionsbestimmung im Innenraum erfolgt über ein **Marvelmind SuperBeacon-System**:

* Ultraschallbasierte Lokalisierung
* vier Beacons im Raum
* ein Beacon auf der Drohne
* Nutzung des NIA-Modus zur Kompensation von Drohnengeräuschen

Das System berechnet aus den gemessenen Abständen zu den einzelnen Beacons die aktuelle Position der Drohne im Raum.

Der Demonstrator umfasst folgende Prozessschritte:

* autonomer Flug der Drohne zwischen verschiedenen Stationen
* Aufnahme der Leitung mittels Greifer
* präzise Steckung der Litze in das Modul
* Ablage des montierten Moduls in der Endstation

<img width="861" height="1457" alt="image" src="https://github.com/user-attachments/assets/1733cf68-e24f-42f7-8825-dfbcb8d1dc0c" />

---

**Weitere Informationen:**    
[Transformations-Hub Leitungssatz](https://www.leitungssatz-hub.de)     
[ARENA2036](https://arena2036.de)     
[wemonte AG](https://wemonte.de)    

---

*Dieses Repository dient der transparenten Bereitstellung der Challenge-Daten und fördert den offenen Innovationsaustausch.*

