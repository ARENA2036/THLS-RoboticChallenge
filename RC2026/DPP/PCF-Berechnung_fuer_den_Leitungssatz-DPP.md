# PCF-Berechnung für den Digitalen Produktpass des Leitungssatzes

**Jann Warnecke**
*Friedrich-Alexander-Universität*
Nürnberg, Deutschland
(jann.warnecke@faps.fau.de)

**Markus Rentschler**
*ARENA2036 e.V.*
Stuttgart, Deutschland
(markus.rentschler@arena2036.de)

**Yanni Sandro Astono**
*Ludwig-Bölkow-Systemtechnik GmbH*
Ottobrunn, Deutschland
(Yanni.Astono@LBST.de)

**Johannes Becker**
*4Soft GmbH*
München, Deutschland
(becker@4soft.de)

**Uwe Prüfer**
*smartCable GmbH*
Erlangen, Deutschland
(uwe.pruefer@smartcable.de)

**Klaus Falkenberg**
*SEI Automotive Europe GmbH*
Wiesbaden, Deutschland
(Klaus.Falkenberg@sei-ae.com)

---

## Zusammenfassung

Diese Arbeit untersucht den aktuellen Stand standardisierter Methoden zur Erstellung des Digitalen Produktpasses (DPP) und zur Berechnung des Produkt-Carbon-Footprints (PCF) für automotive Leitungssätze. Der Schwerpunkt liegt auf der Definition einer Vorlage mit standardisierten Datenmodellen für Materialien, Prozesse und Emissionen, um transparente, automatisierbare und unternehmensübergreifend austauschbare CO₂-Bilanzen zu ermöglichen. Ziel ist es, der Industrie die Erfüllung kommender gesetzlicher Anforderungen zur DPP-Erstellung mit automatisierter PCF-Berechnung zu ermöglichen, Orientierung bei der Auswahl der PCF-Berechnungsmethode zu geben, eine generische Datenvorlage sowohl für Asset Administration Shell (AAS)- als auch für Catena-X-Ökosysteme vorzuschlagen sowie die Herausforderungen für die produzierende Industrie hinsichtlich Datenanforderungen und IT-Infrastruktur aufzuzeigen.

**Schlüsselwörter:** AAS, Catena-X, DPP, PCF, KBL, VEC

---

# 1. Einleitung

Im Dezember 2025 erzielten EU-Rat und Europäisches Parlament eine vorläufige Einigung über die neue Altfahrzeug-Verordnung (ELV), die einen entscheidenden Schritt in Richtung einer zirkulären Automobilwirtschaft darstellt. Die Verordnung schreibt steigende Anteile von Recyclingkunststoffen in neuen Fahrzeugen vor: mindestens 15 % innerhalb von 6 Jahren nach Inkrafttreten, steigend auf 25 % innerhalb von 10 Jahren, wobei 20 % des Rezyklats aus dem Closed-Loop-Recycling stammen müssen (Materialien, die aus Altfahrzeugen zurückgewonnen wurden). (Rat der Europäischen Union 2025)

Um diese Ziele zu erreichen und zu messen, ist eine zentrale Innovation der verpflichtende **Kreislaufwirtschafts-Fahrzeugpass**. Dieser Digitale Produktpass (DPP) liefert detaillierte, aktuelle Daten zur Materialzusammensetzung, zu Rezyklat-Anteilen und zu genauen Demontageanweisungen und wirkt sich damit grundlegend darauf aus, wie Leitungssatzsysteme konstruiert, dokumentiert, demontiert und recycelt werden.

Die Erweiterte Herstellerverantwortung (EPR) macht OEMs nun finanziell und organisatorisch für den gesamten Fahrzeuglebenszyklus verantwortlich, einschließlich der Nettokosten für Sammlung und Behandlung. Für die Leitungssatzindustrie — geprägt durch komplexe Kunststoffisolierungen und Mehrmaterialdesigns — entstehen dadurch neue Herausforderungen bei der Erstellung und Verwaltung digitaler Produktpässe, die eine entsprechende IT-Infrastruktur erfordern.

Die Grundsätze der *Ökobilanzierung*, insbesondere im Kontext produktbezogener Bewertungen, werden angewendet, um den *Produkt-Carbon-Footprint* (PCF) als Summe aller direkten und indirekten Treibhausgasemissionen über die Lebenszyklusphasen eines Produkts zu quantifizieren. Emissionen werden typischerweise in Tonnen CO₂-Äquivalenten (t CO₂-eq) ausgedrückt, was Kohlendioxid und andere Treibhausgase einschließt.

Zur Strukturierung dieser Untersuchung werden folgende Forschungsfragen behandelt:

- **FF1**: Welche Datenstandards und -modelle sind für die Erstellung eines Digitalen Produktpasses für automotive Leitungssätze relevant? (Abschnitte 2 und 3)
- **FF2**: Welche Methoden und Datenmodelle sollen für die PCF-Berechnung im Leitungssatz-Bereich angewendet werden? (Abschnitte 3 und 4)
- **FF3**: Wie können bestehende standardisierte Submodell-Vorlagen angepasst werden, um einen generischen, interoperablen DPP mit integrierten PCF-Daten für Leitungssätze zu ermöglichen? (Abschnitt 4)

Der Rahmen dieser Arbeit ist auf den DPP während der Engineering- und Produktionsphasen begrenzt. Die Handhabung des Leitungssatz-DPP während des Produktbetriebs, d. h. während der Leitungssatz im Fahrzeug verbaut ist, liegt außerhalb des Betrachtungsbereichs.

---

# 2. Stand der Technik

Dieser Abschnitt gibt einen Überblick über bestehende Standards, Datenmodelle und Rahmenwerke, die für die DPP-Erstellung und PCF-Berechnung bei automotiven Leitungssätzen relevant sind, und legt damit die Grundlage zur Beantwortung von **FF1**. Das Forschungsprojekt *DigiTain* (Digitalisierung für Nachhaltigkeit)[^1] entwickelte Prozesse, Methoden und Modelle für die vollständig digitale Produktentwicklung und Zertifizierung nachhaltiger elektrischer Antriebsarchitekturen. Ein zentrales Ziel von DigiTain war die Integration ökologischer und ökonomischer Nachhaltigkeitskriterien bereits in der frühen Entwicklungsphase. Dazu gehörte der Einsatz digitaler Technologien wie der Asset Administration Shell (AAS), Catena-X-Datenräumen und Digitalen Produktpässen (DPP), um einen nahtlosen Lebenszyklus-Datenaustausch, eine transparente PCF-Berechnung und Rückverfolgbarkeit entlang der automobilen Wertschöpfungskette zu ermöglichen. Die Konzepte wurden anhand eines Technologieträgers für elektrische Antriebskomponenten validiert (Haenel, Hedemann und Huschka 2026).

## 2.1 ISO 14067

ISO 14067:2018 legt Grundsätze, Anforderungen und Richtlinien für die Quantifizierung und Berichterstattung des Carbon Footprints von Produkten, allgemein bekannt als Produkt-Carbon-Footprints (PCF), fest. Die Norm basiert auf dem Ökobilanz-Rahmenwerk der ISO 14040 und ISO 14044 und konzentriert sich ausschließlich auf die Wirkungskategorie Klimawandel, ausgedrückt in Kohlendioxidäquivalenten (CO₂eq). Ein PCF gemäß ISO 14067 erfordert eine Ziel- und Rahmendefinition, eine Sachbilanzanalyse (LCI), eine Wirkungsabschätzung (LCIA) und eine Interpretation der Ergebnisse. Die Norm ist nicht auf ein bestimmtes Produkt oder eine bestimmte Branche zugeschnitten, und die Ergebnisse hängen stark von den definierten Systemgrenzen, Modellierungsentscheidungen und Wirkungsabschätzungsmethoden ab. Dies schränkt die Vergleichbarkeit von PCF-Ergebnissen verschiedener Unternehmen ein.

## 2.2 GHG-Protokoll

Das GHG-Protokoll stellt einen internationalen Rahmen für die Quantifizierung und Verwaltung von Treibhausgasemissionen (THG) dar. Es wurde gemeinsam vom World Resources Institute (WRI) und dem World Business Council for Sustainable Development (WBCSD) entwickelt, um standardisierte Methoden bereitzustellen, die Transparenz, Konsistenz und Vergleichbarkeit von Emissionsdaten über Organisationen und Produkte hinweg gewährleisten. Das GHG-Protokoll bietet mehrere Standards, die sich hauptsächlich auf Corporate Carbon Footprints (CCF) konzentrieren. Innerhalb des CCF werden Emissionen in Scope 1 (direkte Emissionen), Scope 2 (indirekte Energieemissionen) und Scope 3 (Wertschöpfungskettenemissionen) eingeteilt. Neben CCF-Standards wird ein Produktlebenszyklus-Standard bereitgestellt, der eng mit ISO 14067 verwandt ist. Im Jahr 2025 kündigten ISO und GHG-Protokoll eine Partnerschaft zur Entwicklung einheitlicher globaler Standards für die THG-Emissionsbilanzierung an. Das PACT-Netzwerk stellt eine aktuelle Spezifikation des GHG-Datenaustauschprotokolls bereit.[^3]

## 2.3 LCA-Studie zu automotiven Leitungssätzen

Der *Transformations-Hub Leitungssatz* veröffentlichte im April 2025 eine Studie mit dem vollständigen Titel *LCA-Studie zur Untersuchung der Umweltauswirkungen von Kfz-Leitungssätzen konventioneller und elektrischer Fahrzeuge*. Die Studie liefert eine vergleichende Cradle-to-Cradle-Ökobilanz von Teilleitungssätzen in konventionellen Verbrennungsfahrzeugen gegenüber batterieelektrischen Fahrzeugen, um Umweltauswirkungen zu quantifizieren, Hotspots zu identifizieren, Datenlücken aufzudecken und Hebel zur Wirkungsreduzierung abzuleiten (z. B. Materialoptimierung und Recycling). Sie unterstützt Nachhaltigkeit in der automobilen Lieferkette, Ökodesign, Closed-Loop-Recycling und EU-Vorschriften (z. B. bezüglich kritischer Rohstoffe).

## 2.4 DIN DKE SPEC 99100

DIN DKE SPEC 99100 (DIN und DKE 2025) definiert Datenattribute für den digitalen Batteriepass gemäß der EU-Batterieverordnung (Verordnung (EU) 2023/1542). Der Standard ist speziell auf Batterien zugeschnitten und kann nicht direkt auf Leitungssätze angewendet werden. Eine Anpassung als strukturelle Vorlage für andere Produktgruppen wie Elektronik, Fahrzeuge usw. ist jedoch vielversprechend. Der strukturierte Ansatz mit Pflicht- und Empfehlungsattributen, maschinenlesbarem Format, QR-Code-Verknüpfung usw. kann als Blaupause für einen Leitungssatzpass durch eine modulare Erweiterung dienen.

## 2.5 Ontologien

Forschungsgetriebene Ontologien für die Kreislaufwirtschaft (CEON)[^4] und DPP (DPPO)[^5] wurden definiert und als Open-Source veröffentlicht, um einen allgemeinen Rahmen für die Erstellung und den Austausch von Daten im Produktlebenszyklusmanagement bereitzustellen.

## 2.6 Catena-X

Das automotive Catena-X-Datenökosystem bietet eine kollaborative, souveräne Dateninfrastruktur für ein resilientes Lieferkettenmanagement. Es hat die PCF-Standardisierung in der Automobilindustrie durch sein PCF-Rulebook und das zugehörige semantische Datenmodell maßgeblich vorangetrieben.

Das *„Product (Carbon) Footprint"*-Aspektmodell `(io.catenax.pcf/9.0.0)` ist eine SAMM-basierte[^6] Ontologie für den interoperablen, maschinenlesbaren Austausch von PCF-Daten entlang der Lieferkette. Es unterstützt den primärdatengetriebenen PCF-Austausch über Eclipse Dataspace Components (EDC), digitale Zwillinge und APIs und orientiert sich am Catena-X PCF-Rulebook. Das Rulebook definiert Berechnungsregeln, Datenqualitätsanforderungen, Allokationsmethoden und einen Cradle-to-Gate-Fokus, unter Einbeziehung von Standards wie ISO 14067 und dem GHG-Protokoll.

Zu den wesentlichen Merkmalen gehören PCF-Werte in kg CO₂eq pro deklarierter Einheit, Produkt- und Unternehmensidentifikatoren, Rückverfolgbarkeitsinformationen, Stücklistenreferenzen und Unterstützung für mehrstufige Aggregation. Das Modell ist Teil des Catena-X Use Case PCF (CX-0136) und integriert sich in andere Aspektmodelle, einschließlich solcher für Digitale Produktpässe.

## 2.7 IMDS

Das *International Material Data System* (IMDS) ist die weltweit etablierte Plattform zur Erfassung und zum Austausch von Materialzusammensetzungsdaten in der Automobilindustrie. Es dient als zentrale Datenbank zur Dokumentation der Material- und Stoffzusammensetzung von Bauteilen, Halbzeugen und Rohstoffen, um die Einhaltung von Vorschriften wie ELV, REACH und GADSL zu gewährleisten und Recyclingbewertungen zu unterstützen.

IMDS erfasst nachhaltigkeitsbezogene Informationen, darunter:

- Detaillierte Materialzusammensetzung und Stoffdeklarationen,
- Rezyklat-Anteile (post-industriell und post-konsumatorisch),
- Kunststoffkennzeichnungen für Sortierung und Recycling.

Alle Materialien müssen gemäß VDA 231-106 klassifiziert werden. Das Feld „Normen/Standards" sollte vorzugsweise auf öffentliche Standards (DIN, EN, ISO, ASTM usw.) verweisen. Tabelle 1 fasst die wichtigsten Felder des IMDS-Materialdatenmodells zusammen.

**Tabelle 1: Felder des IMDS-Materialdatenmodells**

| **Feld** | **Pflicht** | **Semantik / Regeln / Namenskonventionen** |
|:---|:---|:---|
| Name | Pflichtfeld | Muss das Material selbst beschreiben (kein Handelsname). Öffentliche Standards bevorzugen (EN, ISO usw.). Englisch ist Pflicht; andere Sprachen optional. |
| Handelsname | Pflichtfeld, wenn auf Zeichnungen angegeben | Kommerzieller Name des Herstellers (z. B. „Teflon"). |
| Interne Mat.-Nr. | Optional | Lieferanteninterner Bezeichner (nur zur internen Verwendung). |
| Std.-Mat.-Nr. | Pflichtfeld für Metalle >5 g | Standardmaterialnummer/-symbol aus öffentlichen Normen. Nur für Klassen 1–4. |
| Symbol | Pflichtfeld für Polymere Klasse 5.x | ISO-basiertes Symbol (z. B. PE-LD, PA6-GF30). |
| Klassifikation | Pflichtfeld | Basierend auf VDA 231-106 (Anlage I zu Empf. 001). |
| SCIP-Materialkategorie | Optional | EU-SCIP-Datenbankkategorie (REACH). |
| Zusätzliche Materialeigenschaften | Optional | Freitext, wenn keine Standardkategorie passt. |
| Normen / Standards | Pflichtfeld (meiste Fälle >5 g oder Klasse 5) | Öffentliche oder veröffentlichte Hausnormen. |
| Lieferant | Optional | Hersteller des Materials. |
| Bemerkung | Optional | Freitextkommentare. |
| Enthält Rezyklat? | Pflichtfeld | Ja/Nein (gemäß Empf. 025). |
| Rezyklat-Anteil | Pflichtfeld bei Ja | Anorganischer/fossiler Rezyklat-Anteil. |
| Biobasierter Anteil | Pflichtfeld für anwendbare Klassen | Aufschlüsselung primär + sekundär biobasiert. |
| Zusammensetzung (Stoffe) | Pflichtfeld | Stoffe + Joker (max. 9). Müssen im ausgehärteten Endzustand exakt 100 % ergeben. |

Für die bevorstehende EU-Altfahrzeug-Verordnung bietet IMDS eine solide Grundlage für den Nachweis von Recyclingkunststoff-Quoten. Es fehlt jedoch an Unterstützung für die Closed-Loop-Verifizierung, dynamische Lebenszyklusaktualisierungen und detaillierte Demontageanweisungen, die für den verpflichtenden Kreislaufwirtschafts-Fahrzeugpass erforderlich sind.

Seit der Veröffentlichung von IMDS Version 15.0 können PCF-Daten direkt in Material- und Komponentendatensätzen gemäß Empfehlung 027 eingegeben werden, die am Catena-X PCF-Rulebook ausgerichtet ist. Dies ermöglicht eine konsistente Berichterstattung über produkt- und transportbezogene CO₂-Fußabdrücke in kg CO₂eq bei gleichzeitiger Wahrung der Datensouveränität. Es wird erwartet, dass IMDS das primäre System für Lieferanten-Materialdeklarationen bleibt, muss jedoch durch zusätzliche digitale Werkzeuge wie Catena-X und Digitale Produktpässe für vollständige Lebenszykltransparenz und künftige ESG/CSRD-Anforderungen ergänzt werden.

## 2.8 KBL und VEC

KBL (*KAbelBaumListe*, VDA-4964) und VEC (*Vehicle Electric Container*, VDA-4968) sind Engineering-Datenstandards für automotive elektrische Systeme. Beide sind XML-basiert und unterstützen Erweiterungen über benutzerdefinierte Eigenschaften. Das VEC-Modell wird zudem als OWL2-Ontologie für Semantic-Web-Anwendungen veröffentlicht. Sie werden im Engineering-Prozess zur Beschreibung des Designs eines Leitungssatzes sowie im Fall des VEC für detaillierte technische Komponentendaten weitgehend eingesetzt. Aus PCF-Perspektive sind die wichtigsten Informationen, die sie liefern, die vollständige Stücklistenhierarchie des Leitungssatzes, die in klassischen PDM-Systemen aufgrund der Produktkomplexität oft fehlt. In begrenztem Umfang liefern sie auch die beteiligten Materialien und ihre Gewichte.

Die **KBL** ordnet Teile in einer hierarchischen Stückliste (Leitungssatz, Module, Baugruppen, Komponenten) an, um Variantenmanagementmethoden zuzuordnen. Das Material kann für jedes Teil über ein Tupel bestehend aus einem Referenzsystem und einem Schlüssel definiert werden. Das Referenzsystem (z. B. IMDS oder ein Standard) definiert die Semantik des Schlüssels. Der primäre Fokus der KBL liegt auf der Bereitstellung einer Build-to-Print-Definition des Leitungssatzes. Daher werden Stoffdetails bewusst weggelassen und an externe Referenzsysteme (z. B. IMDS) delegiert.

Der **VEC** bietet dieselben Möglichkeiten wie die KBL. Darüber hinaus ermöglicht er die gleichzeitige Referenzierung von Materialdefinitionen aus verschiedenen Referenzsystemen. Er verfügt auch über eine formal definierte und web-referenzierbare Ontologie[^7]. Außerdem erlaubt er die Spezifikation von Materialzusammensetzungen einschließlich Massenanteilen. Für die Identifizierung spezifischer Materialien und Stoffe definiert der VEC jedoch kein eigenes Referenzsystem, sondern stützt sich auf externe Standards.

## 2.9 Asset Administration Shell (AAS)

Die *Asset Administration Shell* (AAS) ist das zentrale standardisierte Rahmenwerk von Industrie 4.0 für die semantische Modellierung und den interoperablen Austausch von anlagenbezogenen Daten über den gesamten Lebenszyklus. Als Kernimplementierung des digitalen Zwillings bietet sie ein modulares, maschinenlesbares Informationsmodell bestehend aus Submodellen, die Eigenschaften, Fähigkeiten, Zustände, Dienste und Lebenszyklusinformationen physischer oder logischer Assets beschreiben. Ihre standardisierten Schnittstellen und Serialisierungsformate ermöglichen eine nahtlose Datenintegration und automatisierte Nutzung über heterogene Systeme und Organisationsgrenzen hinweg.

Mehrere AAS-Submodell-Vorlagen (SMTs) sind für Digitale Produktpässe im automotiven Bereich besonders relevant:

Die SMT-Reihe *IDTA-02035-x: Digital Battery Passport*[^8] definiert Datenstrukturen gemäß DIN DKE SPEC 99100 und der EU-Batterieverordnung (EU) 2023/1542. Sie umfasst sieben Teile, von denen viele für einen Leitungssatz-DPP angepasst werden können.

Die SMT *IDTA-02023: Carbon Footprint* bietet ein standardisiertes, erweiterbares Modell für den Austausch anlagenbezogener Carbon-Footprint-Daten entlang von Wertschöpfungsketten. Es kombiniert eine generische übergeordnete Fußabdruckstruktur mit branchenspezifischen Berechnungsregeln und gewährleistet die Kompatibilität mit ISO 14067, ISO 14040/14044, dem GHG-Protokoll und den Catena-X PCF-Konventionen. Ein Berechnungsassistent für dieses Submodell wurde im BaSyx-Framework entwickelt.[^9]

Die SMT *IDTA-02011: Hierarchical Structures enabling Bills of Material* definiert eine standardisierte Darstellung komplexer mehrstufiger Asset-Hierarchien und eignet sich damit besonders für die Modellierung der mehrstufigen Stückliste (BoM) und der verteilten Asset-Strukturen von Leitungssätzen.

## 2.10 DIN 182xx

Die kürzlich veröffentlichte DIN EN 182xx-Reihe ist eine Gruppe von Spezifikationen zur technischen Infrastruktur für DPPs, d. h. zur Datenhandhabung, -sicherheit und zum Zugang für, jedoch nicht zum eigentlichen Inhalt des digitalen Produktpasses, der aus produktspezifischen delegierten Rechtsakten stammt.

Diese Spezifikationen werden unter dem DIN-Normenausschuss *NA 043-02-06 GA* koordiniert und bilden gemeinsam ein vollständiges technisches Rahmenwerk:

- **DIN EN 18216** — Protokolle für den Datenaustausch (sichere Formate und Protokolle für die Übertragung von DPP-Daten).
- **DIN EN 18219** — Eindeutige Bezeichner (Regeln für Produkt-IDs, Wirtschaftsbeteiligten-IDs und Betriebsstätten-IDs).
- **DIN EN 18220** — Datenträger (Anforderungen an QR-Codes, RFID usw., die auf einen DPP verweisen).
- **DIN EN 18221** — Datenspeicherung, Archivierung und Datenpersistenz (dezentrale Speicherregeln und Langzeitbeständigkeit).
- **DIN EN 18222** — APIs für Lebenszyklusmanagement und Auffindbarkeit.
- **DIN EN 18223** — Systeminteroperabilität (übergreifende Regeln, damit verschiedene DPP-Systeme miteinander kommunizieren können).
- **DIN EN 18239** — Verwaltung von Nutzerrechten, IT-Sicherheit und Geschäftsgeheimnissen (Zugriffskontrolle, Datenschutz und Verantwortungsübertragung).
- **DIN EN 18246** — Datenauthentizität, -zuverlässigkeit und -integrität (für manipulationssichere und vertrauenswürdige Daten).

Das Ziel ist ein sicherer, interoperabler, dezentraler, maschinenlesbarer und zukunftssicherer DPP.

---

# 3. Analyse

Aufbauend auf den in Abschnitt 2 vorgestellten Standards und Datenmodellen untersucht dieser Abschnitt die praktischen Herausforderungen ihrer Anwendung im Leitungssatz-Bereich. Er beantwortet **FF1** durch die Analyse der Materialdatendarstellung in bestehenden Systemen und **FF2** durch die Untersuchung von PCF-Berechnungsmethoden, Datenaustauschverfahren und der Schwierigkeiten entlang der Liefer- und Produktionsketten.

## 3.1 Fragmentiertes Identitätsmanagement

Die Leitungssatz-Lieferkette ist stark dezentralisiert, wobei die Beteiligten separate Teilenummerierungsschemata und Datenspeicher pflegen. Das Fehlen eines durchgehenden unternehmensübergreifenden Identitätsmanagementsystems führt zu Datensilos und inkonsistenten, schlecht maschinenlesbaren Produktmodellen.[^10]

## 3.2 Materialeigenschaften in IMDS, KBL, VEC und AAS

KBL und VEC bieten begrenzte Unterstützung für Materialeigenschaften, während IMDS häufig für die regulatorische Compliance (z. B. REACH, ELV) verwendet wird, obwohl es von den Standards nicht vorgeschrieben ist. Weder KBL noch VEC speichern nativ Informationen auf Stoffebene wie CAS-Nummern. Die IMDS-Integration in VEC kann erreicht werden, indem *referenceSystem* auf „https://public.mdsystem.com/" gesetzt und das Feld *key* für die IMDS-MDS-ID verwendet wird. Für reichhaltigere Materialdaten erlaubt VEC benutzerdefinierte Eigenschaften auf *GeneralTechnicalPartSpecification*. Ein verallgemeinertes AAS-Submodell basierend auf *IDTA-02035-6: Digital Battery Passport – Part 6: Material Composition* kann IMDS als Brücke nutzen, indem es die explizite Unterstützung für IMDS-Referenzen in KBL und VEC verwendet. Dieser Ansatz ermöglicht die semantische Ausrichtung über CAS-Nummern und Materialhierarchien bei minimalen benutzerdefinierten Erweiterungen. Allerdings führen inkonsistente Anwendungen von Standards (hauptsächlich VDA 231-106 und ISO 1043) in IMDS häufig zu semantischen Identifikationsproblemen, die bewältigt werden müssen.

## 3.3 PCF-Berechnung

Die PCF-Berechnung gemäß ISO 14067 umfasst mehrere methodische Entscheidungen, darunter die Definition der funktionellen Einheit, Systemgrenzen, Allokationsregeln und Wirkungsabschätzungsmethoden. Darüber hinaus werden die Ergebnisse von der Datenqualität und der Verwendung sekundärer Datensätze beeinflusst, was den Prozess komplex macht und ausgeprägte LCA-Expertise erfordert, insbesondere für kleinere Zulieferer.

Um dem entgegenzuwirken, führt das Catena-X PCF-Rulebook branchenspezifische Berechnungsregeln ein, die den methodischen Spielraum reduzieren und die Vergleichbarkeit entlang automotiver Lieferketten verbessern. Ergänzende Mechanismen wie Primary Data Share (PDS), Data Quality Ratings (DQR) und Product Verification Share (PVS) erhöhen die Transparenz und das Vertrauen in die gemeldeten Ergebnisse bei gleichzeitiger Beibehaltung eines standardisierten Berechnungsansatzes.

![PCF-Berechnungsbeispiel für den Crimpingprozess](https://github.com/user-attachments/assets/55e12e52-8621-4035-a5da-7d4222bfdd30)

*Abbildung 1: PCF-Berechnungsbeispiel für den Crimpingprozess*

Abbildung 1 zeigt ein einfaches PCF-Berechnungsbeispiel für den Prozess des *Crimpens*, bei dem ein *Kabel* und ein *Terminal* Materialeingaben für den Crimpingprozess liefern. Alle Ein- und Ausgaben basieren auf einer Einheit von 1 Stück gecrimpetem Kabel (bekannt als deklarierte Einheit). Der PCF jedes Flusses wird wie folgt berechnet:

$$PCF_i = \text{Aktivitätsdaten}_i \times \text{Emissionsfaktor}_i$$

Im Catena-X-Ökosystem sind die Zulieferer der Produkte dafür verantwortlich, die jeweiligen PCF-Daten für die Berechnung bereitzustellen. In diesem Beispiel wird davon ausgegangen, dass die Zulieferer in wirtschaftlicher oder operativer Hinsicht für die ausgehende Logistik verantwortlich sind. Emissionen aus dem Transport des Kabels und des Terminals müssen in diesem Fall von den Zulieferern berücksichtigt werden. Der Emissionsfaktor für den Crimpingprozess wird in diesem Fall aus der Stromrechnung des Herstellers abgeleitet. Es ist zu beachten, dass die neueste Version des Catena-X PCF-Rulebooks vorschreibt, dass Infrastrukturemissionen aus der Stromerzeugung in die PCF-Berechnung einbezogen werden müssen. Sobald alle Eingaben berücksichtigt wurden, müssen die Emissionen aus den Ausgaben berechnet werden. Dieses Beispiel erzeugt keine direkten Emissionen, aber einen Materialfluss, der aus dem Schneiden des Kabelisoliermaterials resultiert. Die Behandlung dieses Isolationsabfalls führt zu THG-Emissionen, die dem Produktsystem zugerechnet werden müssen, das den Abfall erzeugt hat. Im Beispiel wird der Prozess der Verbrennung von Kunststoffabfällen ohne Energierückgewinnung angenommen und ein Emissionsfaktor aus einer Sekundärdatenbank verwendet.

Dies ergibt einen Gesamt-PCF von 1,0055 kg CO₂eq für das produzierte gecrimpe Kabel. Der PCF des Crimpingprozesses einschließlich der Verbrennung des Isolationsabfalls beläuft sich auf 0,0005 kg CO₂eq, was nur 0,05 % des Gesamtergebnisses entspricht. Das Catena-X PCF-Rulebook erlaubt den Ausschluss von Emissionen, wenn ihre Summe weniger als 3 % des Gesamt-PCF ausmacht. Diese Cut-off-Regel kann auf eine Reihe von Prozessen bei der Herstellung von Leitungssätzen angewendet werden, da der Großteil der Emissionen in einem Leitungssatz-Lebenszyklus gemäß der LCA-Studie des Transformations-Hubs Leitungssatz während der Materialproduktion anfällt.

Ein detaillierteres PCF-Berechnungsbeispiel gemäß dem Catena-X PCF-Rulebook einschließlich einer Screening-Analyse und der Anwendung des Cut-off-Ansatzes ist in der Catena-X PCF Academy verfügbar. Die Verarbeitung umfangreicherer Daten oder komplexer Berechnungen kann dedizierte PCF-Berechnungssoftware erfordern.

## 3.4 PCF-Datenaustausch

Wie zuvor beschrieben, stützen sich PCF-Berechnungen auf Aktivitätsdaten kombiniert mit Emissionsfaktoren, die typischerweise aus IMDS-Materialdaten ergänzt durch primäre oder Datenbankwerte abgeleitet werden. Materialbeschreibungen in IMDS sind jedoch häufig inkonsistent oder fehlen, was eine manuelle Expertenbearbeitung erfordert.

In Catena-X werden PCF-Daten auf Komponentenebene ausgetauscht. Jeder Zulieferer stellt einen PCF-Datensatz für seine Produkte im AAS-Format bereit. Vorgelagerte PCF-Werte von Zulieferern niedrigerer Ebenen werden aggregiert und zum PCF der eigenen Produktionsprozesse des Zulieferers hinzugefügt.

Dieser Ansatz verteilt die Arbeitsbelastung theoretisch über die Lieferkette, wobei jede Stufe für ihre eigenen Produkte verantwortlich ist und damit Lücken in den LCI-Daten und fehlende Emissionsfaktoren reduziert.

In der Praxis fehlt es vielen Tier-1- und niedrigeren Zulieferern noch an der Expertise, zuverlässige PCF-Daten zu generieren. Eine zentrale Aufgabe ist daher die systematische Erfassung standardisierter PCF-Datensätze von Komponentenherstellern. Diese müssen einen definierten Mindestumfang erfüllen und im JSON-Format gemäß dem Catena-X PCF-Submodell (Version 9.0.0) bereitgestellt werden.

Tabelle 2 zeigt die relevanten Eigenschaften unter *productLifeCycleStagesandEmissions* – *productionStage* für das Kabel-Crimping-Beispiel. Die *distributionStage* und *packagingStage* folgen derselben Struktur. Alle Werte sind in kg CO₂eq pro deklarierter Einheit angegeben.

**Tabelle 2: Catena-X PCF-Submodell-Eigenschaften unter *productLifeCycleStagesandEmissions* – *productionStage* für das Kabel-Crimping-Beispiel**

| **Eigenschaft** | **Wert** | **Pflicht** |
|:---|:---|:---|
| pcfIncludingBiogenicUptake | 1,0055 | Pflichtfeld |
| pcfExcludingBiogenicUptake | 1,0055 \* | Pflichtfeld |
| fossilGhgEmissions | 1,0055 \* | Optional |
| biogenicNonCO2Emissions | 0 \* | Optional |
| biogenicCO2Uptake | 0 \* | Optional |
| landUseChangeGhgEmissions | 0 \* | Optional |
| landManagementBiogenicCO2Emissions | 0 \* | Optional |
| landManagementBiogenicCO2Removals | 0 \* | Optional |
| aircraftGhgEmissions | 0 \*\* | Optional |

\* Keine biogenen Emissionen in diesem Beispiel  
\*\* Kein Lufttransport in diesem Beispiel

Aufgrund der hohen Anzahl an Komponenten und der extremen Varianz bei automotiven Leitungssätzen (oft kundenspezifisch) werden täglich mehrere tausend Leitungssätze in einem einzigen Werk produziert. Diese Komplexität erfordert eine vollautomatisierte Datenverarbeitung. Aktuelle Softwarelösungen sind noch begrenzt, und eine umfassende, vollständig automatisierte End-to-End-Lösung ist noch nicht verfügbar.

## 3.5 DPP während des Engineerings

In der Engineering-Phase müssen relevante Daten in den Engineering-Modellen und zugehörigen Systemen für die spätere Erstellung eines DPP im Produktionsprozess bereitgestellt werden. In der Praxis bestehen häufig Lücken, die KBL- und VEC-Engineering-Modelle weitgehend ungeeignet machen, um ordnungsgemäß in Datenraum-Umgebungen übertragen zu werden. Die Engineering-Werkzeuge und ihre Fähigkeiten sind in dieser Phase entscheidend, um eine ausreichende Datenqualität und die Anbindung an Datenräume wie Catena-X sicherzustellen.

## 3.6 DPP in der Lieferkette

Die Erstellung und kontinuierliche Aktualisierung eines DPP für Leitungssätze ist aufgrund der Komplexität globaler mehrstufiger Lieferketten und der hohen Variabilität von Produktkonfigurationen äußerst herausfordernd. Zu den wesentlichen Schwierigkeiten zählt die Integration heterogener Datenquellen (ERP, PLM, Zuliefererdeklarationen und Materialdatenbanken), die sich in Struktur, Granularität und Zugänglichkeit unterscheiden. Semantische Inkonsistenzen — insbesondere in Daten aus dem IMDS — erschweren eine konsistente Interpretation zusätzlich, da identische Materialien und Stoffe häufig mit unterschiedlichen Klassifikationsschemata und Namenskonventionen beschrieben werden. Während Standardisierungsbemühungen, wie die der IEC, vielversprechende Lösungen für die semantische Harmonisierung bieten, ist die praktische Übernahme in der gesamten Lieferkette noch begrenzt. Darüber hinaus ist die Beschaffung zuverlässiger lieferantenspezifischer Daten für PCF-Berechnungen besonders schwierig, da die erforderlichen Informationen zu Materialien, Prozessen und Energieverbrauch häufig unvollständig, proprietär oder auf dem erforderlichen Detailgrad nicht verfügbar sind. Eine effektive DPP-Implementierung für Leitungssätze erfordert daher robuste Datenintegrationstrategien, semantische Ausrichtungsmechanismen und integrierte Lösungen für den Umgang mit Datenlücken und Unsicherheiten.

## 3.7 DPP während des Produktionsprozesses

Die Erstellung und kontinuierliche Aktualisierung eines Digitalen Produktpasses (DPP) während der Produktion stellt vor allem bei stark manuellen Produkten wie Leitungssätzen vor mehrere Herausforderungen. Auch wenn die fortschreitende Modularisierung von Leitungssätzen darauf hindeutet, dass jeder Teilleitungssatz kleiner wird und damit die DPP-Berechnung einfacher, bleibt der Gesamtaufwand für das Gesamtprodukt hoch.

Die **erste Herausforderung** ist die Echtzeit-Datenerfassung im Shopfloor. Die Leitungssatzproduktion umfasst zahlreiche manuelle und halbautomatisierte Schritte (Schneiden, Crimpen, Montage auf Formboards), die die Erfassung von Energieverbrauch, Materialeinsatz und Ausschussraten je Prozessschritt und deren Zuordnung zu einzelnen Produktinstanzen erfordern. Dedizierte Identifikations- und Rückverfolgungsmechanismen sind unerlässlich, um eine klare Verknüpfung zwischen dem physischen Produkt und seiner digitalen Repräsentation über die gesamte Produktionssequenz hinweg aufrechtzuerhalten.

Die **zweite Herausforderung** ist die Festlegung der geeigneten Datengranularität. Ob der PCF auf Los-, Auftrags- oder Einzelstückebene berechnet wird, beeinflusst maßgeblich die erforderliche Messinfrastruktur und das Datenvolumen. Für viele kleine und mittelständische Unternehmen in der Leitungssatz-Lieferkette bleibt das Tracking auf Einzelstückebene aufgrund unzureichend digitalisierter Shopfloor-Systeme unpraktikabel. Dies wird durch fragmentierte und heterogene IT-Landschaften über ERP, PLM, MES und Qualitätsmanagementsysteme hinweg verschärft, denen häufig eine einzige Quelle der Wahrheit fehlt.

Die **dritte Herausforderung** liegt in der schrittweisen Anreicherung des DPP. Anders als ein statisches Dokument muss der DPP progressiv aktualisiert werden, wenn das Produkt die aufeinanderfolgenden Produktionsstufen durchläuft. Dies erfordert robuste Aktualisierungsmechanismen, die Nacharbeit, Qualitätsabweichungen und Komponentensubstitutionen handhaben können, während die Datenkonsistenz gewahrt bleibt. Obwohl die AAS über modulare Submodelle ein standardisiertes Rahmenwerk bietet, bleibt ihre praktische Integration mit bestehenden Fertigungsleitsystemen eine erhebliche Engineering-Herausforderung, insbesondere für Unternehmen mit Legacy-Infrastruktur.

## 3.8 Catena-X-Datenmodelle

Catena-X bietet etablierte Datenmodelle sowohl für den DPP als auch für den PCF. Es existiert jedoch derzeit kein dediziertes Modell zur Darstellung eines Leitungssatzes als Komponentensystem. Automotive Leitungssätze bestehen aus zahlreichen Komponenten mit hochgradig kundenspezifischen Konfigurationen je Fahrzeug. Da täglich mehrere tausend Leitungssätze in einem einzigen Werk produziert werden, ist eine vollautomatisierte Datenverarbeitung unerlässlich. Aktuelle Softwarelösungen bleiben rudimentär, ohne klaren Weg hin zur Vollautomatisierung.

Das Catena-X PCF-Aspektmodell (Version 9.0.0) ist mäßig bis stark komplex. Während seine detaillierte Struktur einen qualitativ hochwertigen, nachvollziehbaren und interoperablen PCF-Datenaustausch im Einklang mit dem PCF Rulebook V4 unterstützt, schafft diese Granularität erhebliche praktische Herausforderungen. Eigenschaften wie *biogenicCarbonContent*, *biogenicNonCO2Emissions* oder *landUseChangeEmissions* erfordern oft Informationen, die für viele Zulieferer — insbesondere niedrigrangige und nicht-europäische — unmöglich oder äußerst schwer bereitzustellen sind. Infolgedessen riskiert die vollständige Compliance, zu unvollständigen Datensätzen, Platzhalterwerten oder dem Ausschluss kleinerer Akteure aus der Lieferkette zu führen.

---

# 4. Lösungsansatz

Aufbauend auf der Analyse in Abschnitt 3 schlägt dieser Abschnitt konkrete Maßnahmen vor, um die identifizierten Herausforderungen bei der DPP-Erstellung und PCF-Berechnung für automotive Leitungssätze anzugehen. Damit vervollständigt er die Beantwortung von **FF2** durch gezielte Anpassungen des Catena-X PCF-Datenmodells und **FF3** durch die Empfehlung von AAS-Submodell-Anpassungen, Datenqualitätsmechanismen und einen pragmatischen stufenweisen Ansatz für die Produktionsdatenerfassung.

## 4.1 Anpassung des Catena-X PCF-Aspektmodells in der AAS

Das Catena-X PCF-Aspektmodell sollte als *SubmodelElementCollection* innerhalb von *ProductOrSectorSpecificRule* der SMT *IDTA-02023: Carbon Footprint* abgebildet werden.

Das Catena-X PCF-Aspektmodell (v4) sollte als *SubmodelElementCollection* innerhalb des *ProductOrSectorSpecificRule*-Elements der IDTA-02023 Carbon Footprint Submodel Template integriert werden. Ältere Catena-X-Versionen (v1–v3) gelten als veraltet. Ein neuer Eintrag für *Catena-X v4* (`urn:samm:io.catenax.pcf:9.0.0`) muss zur Werteliste *PcfCalculationMethod* hinzugefügt werden. Native Catena-X semanticIds werden gegenüber ECLASS-IRDIs stark bevorzugt, um externe Abhängigkeiten zu minimieren.

**Tabelle 3: Werteliste für *PcfCalculationMethod***

| **Wert** | **ECLASS-IRDI** | **Native *semanticId*** |
|:---|:---|:---|
| EN 15804 | 0173-1#07-ABU223 | |
| GHG Protocol | 0173-1#07-ABU221 | |
| IEC TS 63058 | 0173-1#07-ABU222 | |
| IEC 63366 | 0173-1#07-ACA792 | |
| ISO 14040, 14044 | 0173-1#07-ABV505 | |
| ISO 14067 | 0173-1#07-ABU218 | |
| PEP Ecopassport | 0173-1#07-ABU220 | |
| PACT v1.0.1 | 0173-1#07-ACC004 | |
| PACT v2.0.0 | 0173-1#07-ACC003 | |
| PACT v3.0.0 | 0173-1#07-ACC012 | |
| TFS v2 | 0173-1#07-ACC005 | |
| TFS v3 | 0173-1#07-ACC010 | |
| Catena-X v1 | 0173-1#07-ACC007 | urn:samm:io.catenax.pcf:2.0.0 |
| Catena-X v2 | 0173-1#07-ACC006 | urn:samm:io.catenax.pcf:4.0.0 |
| Catena-X v3 | 0173-1#07-ACC011 | urn:samm:io.catenax.pcf:7.0.0 |
| *Catena-X v4* | | urn:samm:io.catenax.pcf:9.0.0 |
| BS PAS 2050 | 0173-1#07-ACC008 | |
| IEC 63372 | 0173-1#07-ACC019 | |

Da kein offizieller HTTP-Namespace für Catena-X SAMM-Modelle existiert, sollen Referenzen das Schema `urn:samm:` verwenden.

## 4.2 Anpassung von AAS-Submodellen

Aktuell existiert kein neutrales IDTA-Submodell für eine allgemeine Materialzusammensetzung. Die *IDTA-02035-6: Digital Battery Passport – Part 6: Material Composition* kann als geeignete Blaupause dienen und durch folgende Ersetzungen in ein neutrales *Product Material Composition*- oder *Asset Material Composition*-Submodell verallgemeinert werden:

- *Battery* → *Product* oder *Asset*
- *batteryChemistry* → *materialChemistry*
- *batteryMaterials* → *componentMaterials*
- Batteriespezifische Komponenten (Kathode, Anode, Elektrolyt) → generische oder domänenspezifische Begriffe (z. B. Isolierung, Leiter, Abschirmung, Steckverbinder)
- *batteryMaterialLocation* → *componentLocation*

Das resultierende Submodell ermöglicht die direkte Zuordnung von KBL/VEC- und IMDS-Materialdaten und bleibt dabei vollständig konform mit bestehenden AAS-Strukturen. Es wird empfohlen, dieses als neue IDTA-02xxxx-Reihe als Vorlage zu veröffentlichen.

## 4.3 Datenqualität

Robuste Datenqualität und eindeutige semantische Identifikation sind für die Interoperabilität unerlässlich. Engineering-Werkzeuge sollten einen direkten IMDS-Import sowie eine proaktive, automatisierte Validierung aller semantischen Referenzen und Bezeichner von frühen Phasen des Produktlebenszyklus an implementieren. Vor der Freigabe eines KBL- oder VEC-Engineering-Modells sollten sofortiges Benutzerfeedback und kontextbezogene Hinweise für fehlende oder ungültige Referenzen bereitgestellt werden. Die VEC-Ontologie soll konsistent als primäres Referenzrahmenwerk verwendet werden. Wo keine web-auflösbaren Bezeichner existieren, werden folgende Standards empfohlen:

- Leiter: IEC 61360-4
- Isolierung: ISO 1043 und ISO 6722

## 4.4 Handhabung der Datenkomplexität

Um die Einstiegshürde für Zulieferer zu senken, sollte das Catena-X PCF-Modell klare Fallback-Mechanismen, abgestufte Datenqualitätsstufen, geführte Validierung und sinnvolle Standardwerte einführen, wenn keine Primärdaten verfügbar sind.

## 4.5 Komponentendatenerfassung

Da vielen Tier-1- und niedrigeren Zulieferern die Expertise fehlt, PCF-Daten in AAS zu generieren und zu modellieren, wird eine benutzerfreundliche webbasierte Schnittstelle innerhalb des Catena-X-Ökosystems vorgeschlagen. Dieses Front-End sollte OEMs ermöglichen, PCF-Daten systematisch direkt von Komponentenherstellern anzufordern und zu erfassen.

## 4.6 Produktionsdatenerfassung

Um Energieverbrauch, Materialeinsatz und Ausschussraten auf Prozessebene mit vertretbarem Aufwand zu erfassen, wird ein hybrider Ansatz empfohlen: Basislinienwerte auf Prozessebene werden während des Vorserien-Engineerings definiert. Selektive Echtzeitmessungen werden nur an kritischen oder hochwirksamen Prozessschritten durchgeführt und dazu verwendet, die Basisdaten kontinuierlich zu kalibrieren und zu verbessern. Diese stufenweise Methode balanciert die Genauigkeitsanforderungen für DPP und PCF mit der praktischen Umsetzbarkeit.

---

# 5. Fazit

Die Analyse des aktuellen Stands der Technik für die DPP-Erstellung in der Leitungssatzindustrie hat gezeigt, dass die primären Hindernisse für eine wirksame Implementierung *Datenqualität* und *Datenkomplexität* sind. Diese Herausforderungen resultieren aus fragmentierten Datenquellen, inkonsistenten Darstellungen entlang der Lieferkette und dem hohen technischen Detailgrad, der für umfassende DPPs erforderlich ist. Um diese Hindernisse zu überwinden und eine skalierbare DPP-Einführung zu ermöglichen, empfehlen wir folgende Schlüsselmaßnahmen:

1. **Datenraum-Interoperabilität sicherstellen** von Leitungssatz-Artefakten durch das Vorschreiben webbasierter, global eindeutiger Objektbezeichner innerhalb von KBL- und VEC-Beschreibungen. Dies lässt sich am besten durch die direkte Integration von Engineering-Werkzeugen mit dem jeweiligen Datenraum erreichen.

2. **Umfassende Werkzeugunterstützung bereitstellen** für die nahtlose Integration von IMDS, automatisierte Datenvalidierung und geführte Datenerfassung ab den frühesten Phasen des Produktlebenszyklus.

3. **Catena-X PCF-Berechnungsstandard vereinfachen**, insbesondere hinsichtlich hochanspruchsvoller Attribute (z. B. Infrastrukturemissionen der Stromerzeugung), die viele Zulieferer unter den aktuellen Bedingungen realistischerweise nicht bereitstellen können.

4. **Generalisierte SMTs entwickeln** für den Leitungssatz-DPP, aufbauend auf den bewährten Strukturen bestehender Batteriepass-SMTs.

Im Rahmen der *Robotik Challenge 2026*[^11] wurde ein erster Demonstrator-Prototyp auf dem Mnestix-Open-Source-Framework[^12] entwickelt. Dieser Prototyp eines webbasierten DPP-Generators und -Viewers[^13] wird in nachfolgenden Projektphasen kontinuierlich erweitert und verfeinert.

---

# Danksagung

Die Autoren danken dem *Bundesministerium für Wirtschaft und Energie* (BMWE) für die Unterstützung durch das Projekt „Transformationshub Leitungssatz" (Förderkennzeichen 16THB0003A). Darüber hinaus gilt der Dank den vielen aktiven Teilnehmern des Projekts und der Arbeitsgruppen der Plattform Industrie 4.0 und verwandter Initiativen.

---

## Fußnoten

[^1]: https://arena2036.de/digitain/
[^2]: https://ghgprotocol.org/
[^3]: https://docs.carbon-transparency.org/data-exchange-protocol/
[^4]: https://liusemweb.github.io/CEON/
[^5]: https://liusemweb.github.io/DPPO/
[^6]: https://catenax-ev.github.io/docs/standards/CX-0003-SAMMSemanticAspectMetaModel
[^7]: https://ecad-wiki.prostep.org/specifications/vec/v220/vec-2.2.0-ontology.ttl
[^8]: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Digital%20Battery%20Passport
[^9]: https://github.com/eclipse-basyx/basyx-aas-web-ui/tree/main/aas-web-ui/src/pages/modules/DPPDemo
[^10]: https://vws4ls.github.io/
[^11]: https://www.leitungssatz-hub.de/en/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/
[^12]: https://github.com/ARENA2036/THLS-DPP-mnestix-browser
[^13]: https://dpp-generator.arena2036.app
