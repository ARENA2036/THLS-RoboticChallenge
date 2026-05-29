## 📌 Digitaler Produktpass (DPP) für den Leitungssatz

Ein zentrales Ziel des **Begleitforschungs- und Digitalisierungsmoduls** der Robotik Challenge 2026 ist die **Definition eines branchenspezifischen Digitalen Produktpasses** für Leitungssätze (Wiring Harnesses).

### Warum ein DPP für Leitungssätze?

Der Digitale Produktpass soll Transparenz, Rückverfolgbarkeit und Kreislauffähigkeit über den gesamten Lebenszyklus eines Leitungssatzes ermöglichen – von der Entwicklung über die Produktion bis hin zu Reparatur, Recycling und Second-Life-Anwendungen. Er unterstützt damit gesetzliche Anforderungen (EU ESPR, Batterie-Verordnung, zukünftige Delegated Acts) und schafft Mehrwert für OEMs, Zulieferer und Recyclingunternehmen.

### Kernziele des DPP im Projekt

- Automatische Erzeugung des DPP am Ende des robotergestützten Fertigungsprozesses
- Verknüpfung von Engineering-Daten (VEC/KBL), Fertigungsdaten und Qualitätsdaten
- Interoperabilität mit bestehenden Industriestandards (besonders **Asset Administration Shell – AAS**)
- Offene und nachnutzbare Spezifikation für die gesamte Leitungssatz-Branche

---

### Geplante Inhalte des Digitalen Produktpasses (Leitungssatz-spezifisch)

| Kategorie                    | Beispiele für Inhalte                                                                 | Datenquelle                  | Granularität      |
|-----------------------------|---------------------------------------------------------------------------------------|------------------------------|-------------------|
| **Identifikation**          | Unique Product ID, Seriennummer, Batch-ID, Hersteller, Produktionsdatum              | Fertigungsprozess            | Item / Batch      |
| **Produktzusammensetzung**  | Stückliste (Einzeladern, Verdrillungen, Koax, Stecker, Clips, Kabelbäume etc.)      | VEC / KBL + Fertigungsdaten  | Komponente        |
| **Materialien & Chemie**    | Materialien der Isolierung, Leiterwerkstoffe, Halogenfreiheit, REACH/ RoHS-Status    | Engineering + Lieferant      | Material / Teil   |
| **Fertigungsdaten**         | Prozessparameter, Energieverbrauch, Zykluszeiten, Rüstzeiten, verwendete Roboter     | Sensorik & Steuerung         | Prozessschritt    |
| **Qualität & Prüfung**      | Prüfergebnisse (Crimphöhe, Isolation, Kontinuität, HV-Test etc.), Fehlerprotokolle   | Qualitätssicherung           | Item              |
| **Kreislaufwirtschaft**     | Demontageanleitung, Recyclierbarkeit, Reparierbarkeit, Second-Life-Potenzial        | Engineering + Simulation     | Produkt / Modul   |
| **Umwelt & Nachhaltigkeit** | Product Carbon Footprint (PCF), Energieverbrauch pro Einheit, kritische Rohstoffe    | Berechnet aus Prozessdaten   | Produkt           |
| **Konformität**             | CE-Kennzeichnung, gesetzliche Deklarationen, Lieferantenerklärungen                 | Engineering                  | Produkt           |

---

### Technische Umsetzung

- **Datenmodell**: Basierend auf **Asset Administration Shell (AAS)** – kompatibel zu Catena-X und Industrie 4.0
- **Zugang**: REST-API, dezentrale Verwaltungsschale (AAS Submodels)
- **Datenquellen**: VEC / KBL, OPC UA, MES/PLC-Daten, Qualitätsdatenbanken
- **Microservices**: Open-Source-Bausteine des Leitungssatz-Hubs (z. B. DPP-Generator per REST-API)
- **Unique Identifier**: GS1-konform oder AAS-spezifisch (Global Unique Identifier)

**Geplante Deliverables:**
- DPP-Datenmodell-Spezifikation (AAS Submodel Template für Leitungssätze)
- [Referenzimplementierung zur automatischen Erzeugung](https://dpp-generator.arena2036.app/)
- [Open-Source-Beiträge](https://github.com/ARENA2036/THLS-DPP-Generator)
- [Veröffentlichung zur ETFA 2026](https://github.com/ARENA2036/THLS-RoboticChallenge/blob/main/RC2026/DPP/ETFA2026-0128__Digital_Product_Passport_for_the_Wiring_Harness.pdf)
- Demonstrator am Innovationsforum Leitungssatz 2026
---

### Mögliche Erweiterungen (Zukunft)

- Integration von Echtzeit-Daten (Zustandsüberwachung im Fahrzeug)
- Verknüpfung mit Digitalem Zwilling des Fahrzeugs
- Blockchain-basierte Nachverfolgbarkeit (optional)
- Vollständige Lieferketten-Transparenz (Tier-n)

---
