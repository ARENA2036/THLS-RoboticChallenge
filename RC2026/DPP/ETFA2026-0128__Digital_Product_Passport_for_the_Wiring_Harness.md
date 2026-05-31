# Digital Product Passport with Product Carbon Footprint Calculation for the Wiring Harness

**Jann Warnecke**
*Friedrich-Alexander-Universität*
Nuremberg, Germany
jann.warnecke@faps.fau.de

**Markus Rentschler**
*ARENA2036 e.V.*
Stuttgart, Germany
markus.rentschler@arena2036.de

**Yanni Sandro Astono**
*Ludwig-Bölkow-Systemtechnik GmbH*
Ottobrunn, Germany
Yanni.Astono@LBST.de

**Johannes Becker**
*4Soft GmbH*
Munich, Germany
becker@4soft.de

**Uwe Prüfer**
*smartCable GmbH*
Erlangen, Germany
uwe.pruefer@smartcable.de

**Klaus Falkenberg**
*SEI Automotive Europe GmbH*
Wiesbaden, Germany
Klaus.Falkenberg@sei-ae.com

## Abstract

This work researches the current state of standardized methods for creation of the Digital Product Passport (DPP) and calculation of the Product Carbon Footprint (PCF) for automotive wiring harnesses. Focus is on defining a template with standardized data models for materials, processes and emissions to enable transparent, automatable, and cross-company exchangeable $CO_2$ balances. The aim is to enable the industry to fulfill forthcoming legislation for DPP creation with automated PCF calculation, provide guidance in PCF calculation method selection, proposing a generic data template for both Asset Administrations Shell (AAS) and Catena-X ecosystems as well as highlighting the challenges for the producing industry regarding data requirements and IT infrastructure. 

---
<div class="IEEEkeywords">

Keywords: AAS, Catena-X, DPP, PCF, KBL, VEC

</div>

# Introduction

In December 2025, the EU Council and Parliament reached a provisional
agreement on the new End-of-Life Vehicles (ELV) Regulation, marking a
decisive step toward a circular automotive economy. The regulation
mandates increasing shares of recycled plastics in new vehicles: at
least 15 % within 6 years after entry into force, rising to 25 % within
10 years, with 20 % of the recycled content required to come from
closed-loop recycling (materials recovered from ELVs).(Council of the
European Union 2025)

In order to reach and measure these goals, a central innovation is the
mandatory **Circularity Vehicle Passport**. This Digital Product
Passport (DPP) provides detailed, up-to-date data on material
composition, recycled content percentages, and exact dismantling
instructions, thus also fundamentally impacting how wiring harness
systems are constructed, documented, disassembled, and recycled.

Extended Producer Responsibility (EPR) now holds OEMs financially and
organizationally accountable for the full vehicle lifecycle, including
net costs of collection and treatment. For the wiring harness industry —
characterized by complex plastic insulation and multi-material designs —
this creates new challenges regarding the creation and management of
digital product passports, demanding a dedicated IT infrastructure for
this purpose.

The principles of *Life Cycle Assessment*, particularly in the context
of product-level assessments are applied to quantify *Product Carbon
Footprint* (PCF) as the total direct and indirect greenhouse gas
emissions associated with a product’s life cycle stages. Emissions are
typically expressed in tons of equivalent *C**O*<sub>2</sub> (t
*C**O*<sub>2</sub> -eq), which includes carbon dioxide and other
greenhouse gasses.

To structure this investigation, the following research questions are
addressed:

-   **RQ1**: What data standards and models are relevant for creating a
    Digital Product Passport for automotive wiring harnesses?
    (Sections <a href="#sec:relatedWork" data-reference-type="ref"
    data-reference="sec:relatedWork">2</a>
    and <a href="#sec:analysis" data-reference-type="ref"
    data-reference="sec:analysis">[sec:analysis]</a>)

-   **RQ2**: Which methods and data models should be applied for PCF
    calculation in the wiring harness domain?
    (Sections <a href="#sec:analysis" data-reference-type="ref"
    data-reference="sec:analysis">[sec:analysis]</a>
    and <a href="#sec:solution" data-reference-type="ref"
    data-reference="sec:solution">4</a>)

-   **RQ3**: How can existing standardized submodel templates be adapted
    to enable a generic, interoperable DPP with integrated PCF data for
    wiring harnesses?
    (Section <a href="#sec:solution" data-reference-type="ref"
    data-reference="sec:solution">4</a>)

The scope of this paper is limited to the DPP during the engineering and
production phases. The handling of the wiring harness DPP during product
operation, i.e., while the harness is installed in the vehicle, is out
of scope.

# Related Work

This section surveys the existing standards, data models, and frameworks
relevant to DPP creation and PCF calculation for automotive wiring
harnesses, thereby establishing the foundation for answering **RQ1**.
The research project *DigiTain* (Digitalization for Sustainability)[^1]
developed processes, methods, and models for the fully digital product
development and certification of sustainable electric drive
architectures. A central objective of DigiTain was the integration of
ecological and economical sustainability criteria from the early
development phase. This included the use of digital technologies such as
the Asset Administration Shell (AAS), Catena-X data spaces, and Digital
Product Passports (DPP) to enable seamless lifecycle data exchange,
transparent Product Carbon Footprint (PCF) calculation, and traceability
along the automotive value chain. The concepts were validated using a
technology carrier for electric drive components(Haenel, Hedemann, and
Huschka 2026).

## ISO 14067

ISO 14067:2018 (International Organization for Standardization 2018)
specifies principles, requirements, and guidelines for the
quantification and reporting of the carbon footprint of products,
generally known as Product Carbon Footprints (PCF). The standard is
based on the life cycle assessment (LCA) framework defined in ISO 14040
and ISO 14044 and focuses exclusively on the impact category climate
change, expressed in carbon dioxide equivalents
(*C**O*<sub>2</sub>*e**q*). A PCF according to ISO 14067 requires a goal
and scope definition, a life cycle inventory (LCI) analysis, a life
cycle impact assessment (LCIA) and an interpretation of the results. The
standard is not specific for any product or sector and results are
highly dependent on the defined system boundaries, modeling choices, and
impact assessment methods. This limits comparability of PCF results
reported from different companies.

## GHG Protocol

The GHG Protocol represents an international framework for the
quantification and management of greenhouse gas (GHG)
emissions(Greenhouse Gas Protocol 2025)[^2]. It was jointly developed by
the World Resources Institute (WRI) and the World Business Council for
Sustainable Development (WBCSD) to provide standardized methodologies
that ensure transparency, consistency, and comparability of emissions
data across organizations and products. The GHG Protocol provides
multiple standards primarily focusing on Corporate Carbon Footprints
(CCF). Within CCF, emissions are classified into Scope 1 (direct
emissions), Scope 2 (indirect energy emissions) and Scope 3 (value chain
emissions). Besides CCF standards, a Product Lifecycle standard is
provided, which is closely related to ISO 14067. In 2025, ISO and GHG
Protocol announced a partnership to develop unified global standards for
GHG emissions accounting(International Organization for Standardization
(ISO) 2025). The PACT Network provides an actual specification of the
GHG data exchange protocol[^3].

## LCA Study on automotive wiring harnesses

The *Transformations-Hub Leitungssatz* (Wiring Harness Transformation
Hub) published a study in April 2025 with the full title *LCA-Studie zur
Untersuchung der Umweltauswirkungen von Kfz-Leitungssätzen
konventioneller und elektrischer Fahrzeuge* (LCA Study on the
Environmental Impacts of Wiring Harnesses in Conventional and Electric
Vehicles)(Transformations-Hub Leitungssatz 2025). The study provides a
comparative cradle-to-cradle LCA of partial wiring harnesses in
conventional internal combustion engine vehicles versus battery-electric
vehicles to quantify environmental impacts, identify hotspots, reveal
data gaps, and derive levers for impact reduction (e.g. material
optimization and recycling). It supports sustainability in the
automotive supply chain, ecodesign, closed-loop recycling and EU
regulations (e.g. regarding critical raw materials).

## DIN DKE SPEC 99100

DIN DKE SPEC 99100 (DIN and DKE 2025) defines data attributes for the
digital battery passport required by the EU Battery Regulation
(Regulation (EU) 2023/1542). The standard is specifically tailored to
batteries and cannot be applied directly to wiring harnesses. However,
adaptation as a structural template for other product groups like
electronics, vehicles and so on is promising. The structured approach
with mandatory and recommended attributes, machine-readable format,
QR-code linkage etc. can serve as a blueprint for a wiring harness
passport by creating a modular extension rather.

## Ontologies

Research-driven ontologies for circular ecomomy (CEON)[^4] (Blomqvist et
al. 2023) and DPP (DPPO)[^5] (Jansen et al. 2024) have been defined and
published as open-source to provide a general framework for creating and
sharing data in product lifecycle management.

## Catena-X

The Catena-X automotive data ecosystem (“Catena-x Automotive Network”
2026) provides a collaborative, sovereign data infrastructure for
resilient supply chain management. It has significantly advanced PCF
standardization in the automotive industry through its PCF Rulebook
(“Catena-x Product Carbon Footprint Rulebook (CX-PCF Rules)” 2025) and
the associated semantic data model.

The *“Product (Carbon) Footprint”* aspect model
`(io.catenax.pcf/9.0.0)`(Eclipse Tractus-X 2025) is a SAMM-based [^6]
ontology designed for interoperable, machine-readable exchange of PCF
data across the supply chain. It supports primary-data-driven PCF
sharing via Eclipse Dataspace Components (EDC), digital twins, and APIs,
while aligning with the Catena-X PCF Rulebook. The rulebook defines
calculation rules, data quality requirements, allocation methods, and a
cradle-to-gate focus, incorporating standards such as ISO 14067 and the
GHG Protocol.

Key features include PCF values in *k**g* *C**O*<sub>2</sub>*e**q* per
declared unit, product and company identifiers, traceability
information, BOM references, and support for multi-tier aggregation. The
model is part of the Catena-X Use Case PCF (CX-0136) and integrates with
other aspect models, including those for Digital Product Passports.

## IMDS

The *International Material Data System* (IMDS) is the globally
established platform for collecting and exchanging material composition
data in the automotive industry. It serves as the central database for
documenting the material and substance composition of components,
semi-finished products, and raw materials to ensure compliance with
regulations such as ELV, REACH, and GADSL, while supporting
recyclability assessments.

IMDS captures sustainability-related information, including:

-   Detailed material composition and substance declarations,

-   Recycled content (post-industrial and post-consumer),

-   Plastic identifiers for sorting and recycling.

All materials must be classified according to VDA 231-106. The
“Norms/Standards” field should preferably reference public standards
(DIN, EN, ISO, ASTM, etc.).
TABLE <a href="#tab:imds-material-model" data-reference-type="ref"
data-reference="tab:imds-material-model">1</a> summarizes the main
fields of the IMDS material data model.

<div id="tab:imds-material-model">

| **Field**                           | **Necessity**                         | **Semantics / Rules / Naming Conventions**                                                                                                |
|:------------------------------------|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------|
| Name                                | Mandatory                             | Must describe the material itself (not trade name). Prefer public standards (EN, ISO, etc.). English mandatory; other languages optional. |
| Trade Name                          | Mandatory when specified on drawings. | Manufacturer’s commercial name (e.g., "Teflon").                                                                                          |
| Internal Mat.-No.                   | Optional                              | Supplier-internal identifier (for internal use only).                                                                                     |
| Std. Mat.-No.                       | Mandatory for metals\>5g              | Standard material number/symbol from public norms. Only for classes 1–4.                                                                  |
| Symbol                              | Mandatory for polymers Class 5.x      | ISO-based symbol (e.g., PE-LD, PA6-GF30)                                                                                                  |
| Classification                      | Mandatory                             | VDA 231-106 based (Annex I to Rec. 001).                                                                                                  |
| SCIP Material Category              | Optional                              | EU SCIP database category (REACH).                                                                                                        |
| Additional Material Characteristics | Optional                              | Free-text when no standard category fits.                                                                                                 |
| Norms / Standards                   | Mandatory (most cases\>5g or Class 5) | Public or published in-house standards                                                                                                    |
| Supplier                            | Optional                              | Manufacturer of the material.                                                                                                             |
| Remark                              | Optional                              | Free-text comments.                                                                                                                       |
| Contains Recycled?                  | Mandatory                             | Yes/No (per Rec. 025).                                                                                                                    |
| Recyclate Content                   | Mandatory if Yes                      | Inorganic/fossil-based recyclate content.                                                                                                 |
| Bio-based Content                   | Mandatory for applicable classes      | Primary + secondary bio-based breakdown.                                                                                                  |
| Composition (Substances)            | Mandatory                             | Substances + jokers (max 9). Must sum exactly to 100% in final cured state.                                                               |

TABLE: IMDS Material Data Model Fields

</div>

For the upcoming EU ELV Regulation, IMDS provides a strong foundation
for proving recycled plastic quotas. However, it lacks support for
closed-loop verification, dynamic lifecycle updates, and detailed
dismantling instructions required for the mandatory Circularity Vehicle
Passport.

Since the release of IMDS version 15.0, PCF data can be entered directly
into material and component datasets according to Recommendation 027,
which is aligned with the Catena-X PCF Rulebook. This enables consistent
reporting of product- and transport-related carbon footprints in
*k**g* *C**O*<sub>2</sub>*e**q* while maintaining data sovereignty. IMDS
is expected to remain the primary system for supplier material
declarations, but must be complemented by additional digital tools such
as Catena-X and Digital Product Passports for full lifecycle
transparency and future ESG/CSRD requirements.

## KBL and VEC

KBL (*KAbelBaumListe* (Harness Description List), VDA-4964) and VEC
(Vehicle Electric Container, VDA-4968) are engineering data standards
for automotive electrical systems. Both are XML-based and support
extensions via custom properties. The VEC model is also published as
OWL2 Ontology for semantic web applications. They are widely used in the
engineering process to describe the design of a wiring harness and in
addition detailed technical component data in the case of the VEC. From
a PCF perspective, the most relevant information they provide is the
complete BOM hierarchy of the wiring harness, which is often omitted in
classic PDM systems due to the complexity of the product. To limited
extent, they also provide the materials involved and their weights.

The **KBL** arranges parts in a hierarchical BOM (Harness, Modules,
Assemblies, Components) to attach variant management methods. The
material can be defined for each part via a tuple composed of a
reference system and a key. The reference system (e.g. IMDS or some
standard) defines the semantic of the key. The primary focus of the KBL
is to provide a build-to-print definition of the wiring harness.
Therefore, substance-level details are delibertely omitted and delegated
to external reference systems (e.g. IMDS).

The **VEC** provides the same capabilities as the KBL. In addition, it
enables referencing material definitions from different reference
systems simultaneously. It also comes with a formally defined and
web-referencable ontology[^7]. Furthermore, it allows the specification
of material compositions, including mass fractions. However, for the
identification of specific materials and substances, the VEC does not
define its own reference system, but instead relies on external
standards.

## Asset Administration Shell (AAS)

The *Asset Administration Shell* (AAS) is the central standardized
framework of Industry 4.0 for semantic modeling and interoperable
exchange of asset-related data across the entire lifecycle. As the core
implementation of the digital twin, it provides a modular,
machine-readable information model consisting of submodels that describe
properties, capabilities, states, services, and lifecycle information of
physical or logical assets. Its standardized interfaces and
serialization formats enable seamless data integration and automated
consumption across heterogeneous systems and organizational boundaries.

Several AAS Submodel Templates (SMTs) are particularly relevant for
Digital Product Passports in the automotive domain:

The SMT series *IDTA-02035-x: Digital Battery Passport*[^8] defines data
structures compliant with DIN DKE SPEC 99100 and the EU Battery
Regulation (EU) 2023/1542. It comprises seven parts, many of which can
be adapted for a Wiring Harness DPP.

The SMT *IDTA-02023: Carbon Footprint*(“IDTA-02023-1-0 Submodel
Template: Carbon Footprint” 2024) provides a standardized, extensible
model for exchanging asset-related carbon footprint data along value
chains. It combines a generic high-level footprint structure with
sector-specific calculation rules, ensuring compatibility with ISO
14067, ISO 14040/14044, the GHG Protocol, and Catena-X PCF conventions.
A calculation wizard for this submodel has been developed within the
BaSyx framework [^9].

The SMT *IDTA-02011: Hierarchical Structures enabling Bills of
Material*(“<span class="nocase">IDTA-02011-1-1 Submodel Template:
Hierarchical Structures enabling Bills of Material</span>” 2025) defines
a standardized representation of complex multi-level asset hierarchies,
making it particularly suitable for modeling the multi-level Bill of
Materials (BoM) and distributed asset structures of wiring harnesses.

## DIN 182xx

The recently published DIN EN 182xx series is a suite of specifications
on the technical infrastructure for DPP’s, thus data handling, security
and access for, but not on the actual content of the digital product
passport, which comes from product-specific delegated acts.

These specifications are coordinated under DIN standards committee *NA
043-02-06 GA* and work together as a complete technical framework:

-   DIN EN 18216 — Protocols for data exchange (secure formats and
    protocols for moving DPP data).

-   DIN EN 18219 — Unique identifiers (rules for product IDs, economic
    operator IDs, and facility IDs).

-   DIN EN 18220 — Data carrier (requirements for QR codes, RFID, etc.,
    that link to a DPP).

-   DIN EN 18221 — Data storage, archiving, and data persistence
    (decentralised storage rules and long-term durability).

-   DIN EN 18222 — APIs for lifecycle management and searchability.

-   DIN EN 18223 — System interoperability (overarching rules so
    different DPP systems can talk to each other).

-   DIN EN 18239 — Management of user rights, IT security, and business
    secrets (access control, data protection, and responsibility
    transfer).

-   DIN EN 18246 — Data authentication, reliability, and integrity (for
    tamper-proof and trustworthy data).

The goal is a secure, interoperable, decentralized, machine-readable,
and future-proof DPP.

# Analysis

Building on the standards and data models presented in
Section <a href="#sec:relatedWork" data-reference-type="ref"
data-reference="sec:relatedWork">2</a>, this section examines the
practical challenges of applying them in the wiring harness domain. It
addresses **RQ1** by analyzing material data representation across
existing systems and **RQ2** by investigating PCF calculation methods,
data exchange mechanisms, and the difficulties arising along the supply
and production chains. <span id="sec:analysis"
label="sec:analysis"></span>

## Fragmented Identity Management

The wiring harness supply chain is highly decentralized, with
stakeholders maintaining separate part numbering schemes and data
repositories. The absence of a continuous cross-organizational identity
management system results in data silos and inconsistent, poorly
machine-readable product models[^10].

## Material Attributes in IMDS, KBL, VEC and AAS

KBL and VEC provide limited support for material attributes, while IMDS
is commonly used for regulatory compliance (e.g., REACH, ELV) although
not mandated by the standards. Neither KBL nor VEC natively stores
substance-level information such as CAS numbers. IMDS integration in VEC
can be achieved by setting *referenceSystem* to
“https://public.mdsystem.com/” and using the *key* field for the IMDS
MDS ID. For richer material data, VEC allows custom properties on
*GeneralTechnicalPartSpecification*. An generalized AAS Submodel based
on *IDTA-02035-6: Digital Battery Passport – Part 6: Material
Composition*(IDTA 2025) can leverage IMDS as a bridge, using its
explicit support for IMDS references in KBL and VEC. This approach
enables semantic alignment via CAS numbers and material hierarchies
while minimizing custom extensions. However, inconsistent application of
standards (primarily VDA 231-106 and ISO 1043) in IMDS often leads to
semantic identification issues and must be dealt with.

## PCF Calculation

PCF calculation according to ISO 14067 (International Organization for
Standardization 2018) involves multiple methodological choices,
including functional unit definition, system boundaries, allocation
rules, and impact assessment methods. In addition, results are affected
by data quality and the use of secondary datasets, making the process
complex and requiring strong LCA expertise, especially for smaller
suppliers.

To address this, the Catena-X PCF Rulebook introduces sector-specific
calculation rules that reduce methodological freedom and improve
comparability across automotive supply chains. Complementary mechanisms
such as Primary Data Share (PDS), Data Quality Ratings (DQR), and
Product Verification Share (PVS) enhance transparency and trust in
reported results while maintaining a standardized calculation approach.
The PVS is determined according to the PCF Verification Framework (“PCF
Verification and PCF Program Certification Framework” 2025).      

---
<figure>
<img src="https://github.com/user-attachments/assets/55e12e52-8621-4035-a5da-7d4222bfdd30" id="fig:1"
alt="PCF calculation example for wire crimping process" />
<figcaption aria-hidden="true">PCF calculation example for wire crimping
process</figcaption>
</figure>     

---

Figure <a href="#fig:1" data-reference-type="ref" data-reference="fig:1">1</a> presents a simple PCF calculation example for the process of *crimping*,
where a *wire* and a *terminal* provide material inputs for the crimping
process. All inputs and outputs are based on a unit of 1 piece of
crimped cable (known as declared unit). The PCF of each flow is
calculated as follows:
*P**C**F*<sub>*i*</sub> = ActivityData<sub>*i*</sub> × EmissionFactor<sub>*i*</sub>
In the Catena-X ecosystem, the suppliers of the products are responsible
for providing the respective PCF data to be used for the calculation.
This example assumes that the suppliers are responsible in economic or
operative terms for the outbound logistics. Emissions from
transportation of the cable and terminal must be accounted by the
suppliers in this case. The emission factor for the crimping process is
derived from the electricity bill of the producer in this case. It must
be noted that the latest version of the Catena-X PCF Rulebook requires
infrastructure emissions from electricity generation to be included in
the PCF calculation. Once all inputs have been accounted for, the
emissions from outputs must be calculated. This example produces no
direct emissions, but a material flow resulting from the cutting of
cable insulation material. The treatment of this insulation waste
results in GHG emissions, which must be allocated to the product system
that generated the waste. In the example, the process of incinerating
plastic waste without energy recovery is assumed and an emission factor
from a secondary database is used.

This results in a total PCF of 1.0055 *k**g* *C**O*<sub>2</sub>*e**q*
for the produced crimped wire. The PCF of the wire crimping process
including incineration of insulation waste amounts to 0.0005
*k**g* *C**O*<sub>2</sub>*e**q*, which is only 0.05% of the final
result. The Catena-X PCF Rulebook allows for an exclusion of emissions
if their sum represents less than 3% of the total PCF. (“Catena-x
Product Carbon Footprint Rulebook (CX-PCF Rules)” 2025)This cut-off rule
may be applicable to a number of processes in the manufacturing of
wiring harnesses, as the majority of emissions in a wire harness life
cycle occur during material production according to the LCA study by the
Transformations-Hub Leitungssatz (Transformations-Hub Leitungssatz
2025).

A more detailed PCF calculation example according to the Catena-X PCF
Rulebook including a screening analysis and application of the cut-off
approach is available in (“Catena-x PCF Academy – 3. PCF Calculation”
2024). Processing more comprehensive data (e.g. activity data and
emission factors for a multitude of products) or complex calculations
(e.g. for multi-output-processes involving allocation) may require
dedicated PCF calculation software(“Catena-x Automotive Network
Certified PCF Calculation Apps Pitch Session” 2025).

## PCF Data Exchange

As described before, PCF calculations rely on activity data combined
with emission factors, typically derived from IMDS material data
supplemented by primary or database values. However, material
descriptions in IMDS are often inconsistent or missing, requiring manual
expert processing.

In Catena-X, PCF data is exchanged at component level. Each supplier
provides a PCF dataset for its products in AAS format. Upstream PCF
values from lower-tier suppliers are aggregated and added to the PCF of
the supplier’s own production processes.

This approach theoretically distributes the workload across the supply
chain, with every tier responsible for its own products and thereby
reducing gaps in LCI data and missing emission factors.

In practice, many Tier-1 and lower-tier suppliers still lack the
expertise to generate reliable PCF data. A key task is therefore the
systematic collection of standardized PCF datasets from component
manufacturers. These must fulfill a defined minimum scope and be
provided in JSON format according to the Catena-X PCF submodel (version
9.0.0).

TABLE <a href="#tab:PCF-submodel-properties" data-reference-type="ref"
data-reference="tab:PCF-submodel-properties">2</a> shows the relevant
properties under *productLifeCycleStagesandEmissions* –
*productionStage* for the wire crimping example. The *distributionStage*
and *packagingStage* follow the same structure. All values are given in
*k**g* *C**O*<sub>2</sub>*e**q* per declared unit. Additional details
and optional parameters are described in the official HTML documentation
of the submodel (Eclipse Tractus-X 2025). However, these descriptions
are often too technical for non-experts, highlighting the need to
improve user-friendliness.

<div id="tab:PCF-submodel-properties">

| **Property**                               | **Value** | **Necessity** |
|:-------------------------------------------|:----------|:--------------|
| pcfIncludingBiogenicUptake                 | 1.0055    | Mandatory     |
| pcfExcludingBiogenicUptake                 | 1.0055\*  | Mandatory     |
| fossilGhgEmissions                         | 1.0055\*  | Optional      |
| biogenicNonCO2Emissions                    | 0\*       | Optional      |
| biogenicCO2Uptake                          | 0\*       | Optional      |
| landUseChangeGhgEmissions                  | 0\*       | Optional      |
| landManagementBiogenicCO2Emissions         | 0\*       | Optional      |
| landManagementBiogenicCO2Removals          | 0\*       | Optional      |
| aircraftGhgEmissions                       | 0\*\*     | Optional      |
|                                            |           |               |
| \* No biogenic emissions in this example   |           |               |
| \*\* No aviation transport in this example |           |               |

TABLE: Catena-X PCF submodel properties under
*productLifeCycleStagesandEmissions* – *productionStage* for the wire
crimping example

</div>

Due to the high number of components and extreme variance in automotive
wiring harnesses (often customer-specific), several thousand harnesses
are produced daily in a single plant. This complexity demands fully
automated data processing. Current software solutions are still limited,
and a comprehensive, fully automated end-to-end solution is not yet
available.

## DPP during Engineering

In the engineering phase, relevant data must be provided in the
engineering models and associated systems for the later creation of a
DPP during the production process. In practice, there are often gaps,
rendering KBL and VEC engineering models largely unsuitable to be
properly transferred to data space environments. The engineering tools
and their capabilities are critical in this phase to ensure sufficient
data quality and connection to data spaces like Catena-X.

## DPP in the Supply Chain

Creating and continuously updating a DPP for wiring harnesses is highly
challenging due to the complexity of global multi-tier supply chains and
the high variability of product configurations. Key difficulties include
the integration of heterogeneous data sources (ERP, PLM, supplier
declarations, and material databases) that differ in structure,
granularity, and accessibility. Semantic inconsistencies — especially in
data from the IMDS — further complicate consistent interpretation, as
identical materials and substances are often described using varying
classification schemes and naming conventions. While standardization
efforts such as those by the IEC offer promising solutions for semantic
harmonization, practical adoption across the supply chain remains
limited. Additionally, retrieving reliable supplier-specific data for
PCF calculations is particularly difficult, as required information on
materials, processes, and energy usage is frequently incomplete,
proprietary, or unavailable at the necessary level of detail. Effective
DPP implementation for wiring harnesses therefore demands robust data
integration strategies, semantic alignment mechanisms, and incorporated
solutions for handling data gaps and uncertainties.

## DPP during the Production Process

Creating and continuously updating a Digital Product Passport (DPP)
during production presents several challenges, especially for highly
manual products such as wiring harnesses. Even though the continued
modularisation of wire harnesses indicates that each sub harness will
become smaller (Warnecke et al. 2026), hence easier to calculate a DPP
for, the overall workload for the entire product will remain high.

The first challenge is real-time data acquisition on the shop floor.
Wiring harness production involves numerous manual and semi-automated
steps (cutting, crimping, assembly on form boards), requiring the
capture of energy consumption, material usage, and scrap rates per
process step and their attribution to individual product
instances (Schnauffer et al. 2022). Dedicated identification and
traceability mechanisms are essential to maintain a clear link between
the physical product and its digital representation throughout the
entire production sequence (Jansen et al. 2023).

A second challenge is determining the appropriate data granularity.
Whether the Product Carbon Footprint (PCF) is calculated at lot, order,
or individual item level significantly influences the required
measurement infrastructure and data volume. For many small and
medium-sized enterprises in the wiring harness supply chain, item-level
tracking remains impractical due to insufficiently digitalized shop
floor systems (Informatica 2025). This is exacerbated by fragmented and
heterogeneous IT landscapes across ERP, PLM, MES, and quality management
systems, often lacking a single source of truth (Jansen et al. 2023).

The third challenge lies in the incremental enrichment of the DPP.
Unlike a static document, the DPP must be progressively updated as the
product moves through successive production stages. Especially if just
regular, marginal, changes in the product as proposed by e.g. (Lamprecht
et al. 2025), make it necessary to repeatedly update the wire harness
and its DPP. This demands robust update mechanisms capable of handling
rework, quality deviations, and component substitutions while preserving
data consistency. Although the Asset Administration Shell (AAS) provides
a standardised framework via modular submodels (Salinas Segura et al.
2024), its practical integration with existing manufacturing execution
systems remains a significant engineering challenge, particularly for
companies with legacy infrastructure (Schnauffer et al. 2022).

## Catena-X data models

Catena-X provides established data models for both the Digital Product
Passport (DPP) and Product Carbon Footprint (PCF). However, no dedicated
model currently exists for representing a wiring harness as a system of
components. Automotive wiring harnesses consist of numerous components
with highly customized configurations per vehicle. Given that several
thousand harnesses are produced daily in a single plant, fully automated
data processing is essential. Current software solutions remain basic,
with no clear path toward full automation.

The Catena-X PCF aspect model (version 9.0.0) is moderately to highly
complex. While its detailed structure supports high-quality, traceable,
and interoperable PCF data exchange in line with the PCF Rulebook V4,
this granularity creates significant practical challenges. Properties
such as *biogenicCarbonContent*, *biogenicNonCO2Emissions*, or
*landUseChangeEmissions* often demand information that is impossible or
extremely difficult to provide for many suppliers — especially
lower-tier and non-European ones. As a result, full compliance risks
leading to incomplete datasets, placeholder values, or the exclusion of
smaller actors from the supply chain.

# Solution

Based on the analysis in
Section <a href="#sec:analysis" data-reference-type="ref"
data-reference="sec:analysis">[sec:analysis]</a>, this section proposes
concrete measures to address the identified challenges in DPP creation
and PCF calculation for automotive wiring harnesses. It thereby
completes the answer to **RQ2** through targeted adaptations of the
Catena-X PCF data model and to **RQ3** by recommending AAS submodel
adaptations, data quality mechanisms, and a pragmatic staged approach
for production data collection.

## Adaptation of the Catena-X PCF Aspect Model in the AAS

The Catena-X PCF Aspect Model should be mapped as a
*SubmodelElementCollection* inside *ProductOrSectorSpecificRule* of the
SMT *IDTA-02023: Carbon Footprint*(“IDTA-02023-1-0 Submodel Template:
Carbon Footprint” 2024).

The Catena-X PCF Aspect Model (v4) should be integrated as a
*SubmodelElementCollection* within the *ProductOrSectorSpecificRule*
element of the IDTA-02023 Carbon Footprint Submodel Template. Older
Catena-X versions (v1–v3) are considered deprecated. A new entry for
*Catena-X v4* (`urn:samm:io.catenax.pcf:9.0.0`) must be added to the
*PcfCalculationMethod* value list. Native Catena-X semanticIds are
strongly preferred over ECLASS IRDIs to minimize external dependencies.

<div id="tab:PCF-value-list">

| **Value**        | **ECLASS IRDI**  | **Native *semanticId***       |
|:-----------------|:-----------------|:------------------------------|
| EN 15804         | 0173-1#07-ABU223 |                               |
| GHG Protocol     | 0173-1#07-ABU221 |                               |
| IEC TS 63058     | 0173-1#07-ABU222 |                               |
| IEC 63366        | 0173-1#07-ACA792 |                               |
| ISO 14040, 14044 | 0173-1#07-ABV505 |                               |
| ISO 14067        | 0173-1#07-ABU218 |                               |
| PEP Ecopassport  | 0173-1#07-ABU220 |                               |
| PACT v1.0.1      | 0173-1#07-ACC004 |                               |
| PACT v2.0.0      | 0173-1#07-ACC003 |                               |
| PACT v3.0.0      | 0173-1#07-ACC012 |                               |
| TFS v2           | 0173-1#07-ACC005 |                               |
| TFS v3           | 0173-1#07-ACC010 |                               |
| Catena-X v1      | 0173-1#07-ACC007 | urn:samm:io.catenax.pcf:2.0.0 |
| Catena-X v2      | 0173-1#07-ACC006 | urn:samm:io.catenax.pcf:4.0.0 |
| Catena-X v3      | 0173-1#07-ACC011 | urn:samm:io.catenax.pcf:7.0.0 |
| *Catena-X v*4    |                  | urn:samm:io.catenax.pcf:9.0.0 |
| BS PAS 2050      | 0173-1#07-ACC008 |                               |
| IEC 63372        | 0173-1#07-ACC019 |                               |

TABLE: Value List for *PcfCalculationMethod*

</div>

Since no official HTTP namespace exists for Catena-X SAMM models,
references shall use the `urn:samm:` scheme.

## Adaptation of AAS Submodels

No neutral IDTA submodel for general material composition currently
exists. The *IDTA-02035-6: Digital Battery Passport – Part 6: Material
Composition* can serve as a suitable blueprint and can be generalized
into a neutral *Product Material Composition* or *Asset Material
Composition* submodel by applying the following replacements:

-   *Battery* → *Product* or *Asset*

-   *batteryChemistry* → *materialChemistry*

-   *batteryMaterials* → *componentMaterials*

-   Battery-specific components (cathode, anode, electrolyte) → generic
    or domain-specific terms (e.g., insulation, conductor, shielding,
    connector)

-   *batteryMaterialLocation* → *componentLocation*

The resulting submodel enables direct mapping of KBL/VEC and IMDS
material data while remaining fully compliant with existing AAS
structures. It is recommended to publish this as a new IDTA-02xxxx
series template.

## Data Quality

Robust data quality and unambiguous semantic identification are
essential for interoperability. While the rise of AI-driven multisensor
quality inspection offers promissing new opportunites to track quality
parameters, the need for high quality data remains (Hartmann et al.
2026). Engineering tools should implement direct IMDS import and
proactive, automated validation of all semantic references and
identifiers from the early stages of the product lifecycle. Before
releasing an KBL or VEC engineering model, immediate user feedback and
inline guidance should be provided for missing or invalid references.
The VEC ontology shall be used consistently as the primary reference
framework. Where no web-resolvable identifiers exist, the following
standards are recommended:

-   Conductors: IEC 61360-4

-   Insulation: ISO 1043 and ISO 6722

## Handling Data Complexity

To lower the entry barrier for suppliers, the Catena-X PCF model should
introduce clear fallback mechanisms, tiered data quality levels, guided
validation, and sensible default values when primary data is
unavailable.

## Component Data Collection

Since many Tier-1 and lower-tier suppliers lack the expertise to
generate and model PCF data in AAS, a user-friendly web-based interface
within the Catena-X ecosystem is proposed. This front-end should allow
OEMs to systematically request and collect PCF data directly from
component manufacturers.

## Production Data Collection

To capture energy consumption, material usage, and scrap rates at
process level with acceptable effort, a hybrid approach is recommended:
Process-level baseline values are defined during pre-series engineering.
Selective real-time measurements are performed only on critical or
high-impact process steps and used to continuously calibrate and improve
the baseline data. This staged method balances accuracy requirements for
DPP and PCF with practical implementation feasibility.

# Conclusion

The analysis of the current state of the art for DPP creation in the
wiring harness industry has shown that the primary barriers to effective
implementation are *data quality* and *data complexity*. These
challenges arise from fragmented data sources, inconsistent
representations across the supply chain, and the high level of technical
detail required for comprehensive DPPs. To overcome these barriers and
enable scalable DPP adoption, we recommend the following key measures:

1.  **Ensure dataspace interoperability** of wire harness artefacts by
    mandating the use of web-based, globally unique object identifiers
    within KBL and VEC descriptions. This can best be achieved by direct
    integration of engineering tools with the respective dataspace.

2.  **Provide comprehensive tool support** for seamless integration of
    IMDS, automated data validation, and guided data collection starting
    from the earliest phases of the product lifecycle.

3.  **Simplify Catena-X PCF calculation standard**, particularly with
    respect to highly demanding attributes (e.g. infrastructure
    emissions of electricity generation) that many suppliers cannot
    realistically provide under current conditions.

4.  **Develop generalized SMTs** for the wiring harness DPP, building
    upon the proven structures of existing battery pass SMTs.

Within the framework of the *Robotik Challenge 2026*[^11], an initial
demonstrator prototype was developed on the Mnestix open-source
framework[^12]. This prototype of a web-based DPP-Generator and
-Viewer[^13] will be continuously extended and refined in subsequent
project phases.

# Acknowledgement

The authors appreciate the support from the *German Federal Ministry for
Economic Affairs and Energy* (BMWE) through the project
"Transformationshub Leitungssatz" (Grant No. 16THB0003A). In addition,
thanks are given to the many active participants in the project and the
working groups of the Industry 4.0 Platform and related initiatives.

<div id="refs" class="references csl-bib-body hanging-indent">

<div id="ref-blomqvist2023network" class="csl-entry">

Blomqvist, Eva, Huanyu Li, Robin Keskisärkkä, Mikael Lindecrantz, Mina
Abd Nikooie Pour, Ying Li, and Patrick Lambrix. 2023. “Cross-Domain
Modelling – a Network of Core Ontologies for the Circular Economy.” In
*Proceedings of the 14th Workshop on Ontology Design and Patterns (WOP
2023)*. <https://ceur-ws.org/Vol-3636/paper1.pdf>.

</div>

<div id="ref-CatenaX_Website" class="csl-entry">

“Catena-x Automotive Network.” 2026. Catena-X Automotive Network e.V.;
<https://catena-x.net/>.

</div>

<div id="ref-CatenaX_PCF_Calculation_Apps_Pitch_2025" class="csl-entry">

“Catena-x Automotive Network Certified PCF Calculation Apps Pitch
Session.” 2025. Catena-X Automotive Network e.V.;
<https://catena-x.net/wp-content/uploads/2025/11/Catena-X-PCF-Calculation-APPs-Pitch-Session-v2.pdf>.

</div>

<div id="ref-CatenaX_PCF_Academy_Calculation_2024" class="csl-entry">

“Catena-x PCF Academy – 3. PCF Calculation.” 2024. Catena-X Automotive
Network e.V.;
<https://catena-x.academy/index.php?gf-download=2024%2F11%2F2024-07-29_PCF-Calculation_V89428.pdf&form-id=1&field-id=5&hash=d235dd71bb2c49b8786bd13a5679be3b5017913726c541f1d0dc5904290d738a>.

</div>

<div id="ref-CatenaX2025" class="csl-entry">

“Catena-x Product Carbon Footprint Rulebook (CX-PCF Rules).” 2025.
Catena-X Automotive Network e.V.;
<https://catena-x.net/wp-content/uploads/2025/10/Catena-X-Product-Carbon-Footprint-Rulebook_v4-with-line-numbers.pdf>.

</div>

<div id="ref-EUCouncilELV2025" class="csl-entry">

Council of the European Union. 2025. “Circular Economy: Council and
Parliament Strike Deal on Rules for Vehicle Circularity and Management
of End-of-Life Vehicles.” December 2025.
<https://www.consilium.europa.eu/en/press/press-releases/2025/12/12/circular-economy-council-and-parliament-strike-deal-on-rules-for-vehicle-circularity-and-management-of-end-of-life-vehicles/>.

</div>

<div id="ref-din_dke_spec_99100" class="csl-entry">

DIN, and DKE. 2025. “DIN DKE SPEC 99100:2025-02 – <span
class="nocase">Anforderungen an Datenattribute des
Batteriepasses</span>.” Berlin, Germany: Beuth Verlag.
<https://www.dinmedia.de/de/umweltschutz/BVFR050>.

</div>

<div id="ref-TractusX_PCF_SemanticModel_9_0_0" class="csl-entry">

Eclipse Tractus-X. 2025. “Product Carbon Footprint (PCF) Semantic Data
Model, Version 9.0.0.”
<https://github.com/eclipse-tractusx/sldt-semantic-models/blob/main/io.catenax.pcf/9.0.0/gen/Pcf.html>.

</div>

<div id="ref-GHG_Protocol_Website" class="csl-entry">

Greenhouse Gas Protocol. 2025. “GHG Protocol – Greenhouse Gas Protocol.”
<https://ghgprotocol.org/>.

</div>

<div id="ref-Haenel2026_DigiTainWhitepaper" class="csl-entry">

Haenel, Frauke, Jan Hedemann, and Martin Huschka. 2026. “Digital Product
Passports: Enabling Sustainable Decisions in Early Product Development.”
Stuttgart, Germany: ARENA2036 e.V.
<https://arena2036.de/files/FinaleBilder/02_Projekte/DigiTain/20260327_digitain_whitepaper_v2_.pdf>.

</div>

<div id="ref-hartmann_ai-driven_2026" class="csl-entry">

Hartmann, Annalena, Zetong Liu, Simon Lamprecht, Patrick Bründl, and
Jörg Franke. 2026. “AI-Driven Multisensor Quality Inspection: A Focus
on Robotic Wire Harness Assembly.” In *Advances in Production Management
Systems. Cyber-Physical-Human Production Systems: Human-AI Collaboration
and Beyond*, edited by Hajime Mizuyama, Eiji Morinaga, Tomomi Nonaka,
Toshiya Kaihara, Gregor von Cieminski, and David Romero, 349–63. Cham:
Springer Nature Switzerland.
<https://doi.org/10.1007/978-3-032-03538-7_25>.

</div>

<div id="ref-idta020356materialcomposition" class="csl-entry">

IDTA. 2025. “IDTA 02035-6: Digital Battery Passport – Part 6: Material
Composition.” IDTA 02035-6. Industrial Digital Twin Association.
<https://github.com/admin-shell-io/submodel-templates/blob/main/published/Digital%20Battery%20Passport/6_Material%20Composition/1/0/IDTA%2002035-6_DBP-Part-6_MaterialComposition.pdf>.

</div>

<div id="ref-idta02011HierarchicalStructuresBoM_1_1" class="csl-entry">

“<span class="nocase">IDTA-02011-1-1 Submodel Template: Hierarchical
Structures enabling Bills of Material</span>.” 2025. Specification.
Industrial Digital Twin Association.
<https://github.com/admin-shell-io/submodel-templates/blob/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1/IDTA%2002011-1-1_Submodel_HierarchicalStructuresEnablingBoM.pdf>.

</div>

<div id="ref-idta02023CarbonFootprint_1_0" class="csl-entry">

“IDTA-02023-1-0 Submodel Template: Carbon Footprint.” 2024.
Specification. Industrial Digital Twin Association.
<https://github.com/admin-shell-io/submodel-templates/blob/main/published/Carbon%20Footprint/1/0/IDTA%2002023_Submodel_CarbonFootprint.pdf>.

</div>

<div id="ref-Informatica2025DPP" class="csl-entry">

Informatica. 2025. “Digital Product Passport & Battery Passport
Implementation Guide.” 2025.
<https://www.informatica.com/resources/articles/digital-product-passport-battery-passport-guide.html>.

</div>

<div id="ref-ISO14067_2018" class="csl-entry">

International Organization for Standardization. 2018. *Greenhouse Gases
– Carbon Footprint of Products – Requirements and Guidelines for
Quantification*. Geneva, Switzerland: ISO.
<https://www.iso.org/standard/71206.html>.

</div>

<div id="ref-ISO_GHGP_partnership_2025" class="csl-entry">

International Organization for Standardization (ISO). 2025. “ISO and GHG
Protocol Announce Strategic Partnership to Deliver Unified Global
Standards for Greenhouse Gas Emissions Accounting.”
<https://www.iso.org/news/2025/09/iso-and-ghgp-partnership>.

</div>

<div id="ref-jansen2024modelling" class="csl-entry">

Jansen, Maike, Eva Blomqvist, Robin Keskisärkkä, Huanyu Li, Mikael
Lindecrantz, Karin Wannerberg, André Pomp, Tobias Meisen, and Holger
Berg. 2024. “Modelling Digital Product Passports for the Circular
Economy.” In *Kg4s 2024: The 2nd International Workshop on Knowledge
Graphs for Sustainability*. <https://ceur-ws.org/Vol-3753/paper2.pdf>.

</div>

<div id="ref-Jansen2023DPPRequirements" class="csl-entry">

Jansen, Maike, Tobias Meisen, Christiane Plociennik, Holger Berg, André
Pomp, and Waldemar Windholz. 2023. “Stop Guessing in the Dark:
Identified Requirements for Digital Product Passport Systems.” *Systems*
11 (3): 123. <https://doi.org/10.3390/systems11030123>.

</div>

<div id="ref-Lamprecht_Connector_2025" class="csl-entry">

Lamprecht, S., A. Hartmann, D. Makwana, P. Bründl, and J. Franke. 2025.
“A Novel Connector-and-Gripper Design for Precision Robotic Peg-in-Hole
Operations in Automated Wire Harness Applications.” In *2025 IEEE
International Conference on Industrial Engineering and Engineering
Management (IEEM)*, 0932–39.
<https://doi.org/10.1109/IEEM63636.2025.11357806>.

</div>

<div id="ref-CatenaX_TfS_PCF_Verification_2025" class="csl-entry">

“PCF Verification and PCF Program Certification Framework.” 2025.
Catena-X Automotive Network; Together for Sustainability;
<https://catena-x.net/wp-content/uploads/2025/11/PCF-verification-v2-with-line-numbers.pdf>.

</div>

<div id="ref-Salinas2024AASProcess" class="csl-entry">

Salinas Segura, Alexander, M. Angos Mediavilla, L. Braun, M. Freund, C.
Kosel, and M. Rodriguez. 2024. “A Process Model for Deriving Asset
Administration Shells for Inter-Company Collaboration – a Practical
Approach.” In *Springer Lecture Notes*.
<https://doi.org/10.1007/978-3-031-71142-8_16>.

</div>

<div id="ref-Schnauffer2022AAS4WH" class="csl-entry">

Schnauffer, G., D. Görzig, C. Kosel, and J. Diemer. 2022. “Asset
Administration Shell for the Wiring Harness System.” In *Stuttgart
Conference on Automotive Production (SCAP 2022)*, 324–32. Arena2036.
Springer. <https://doi.org/10.1007/978-3-031-27933-1_30>.

</div>

<div id="ref-leitungssatz-hub-lca-2025" class="csl-entry">

Transformations-Hub Leitungssatz. 2025. “LCA-Studie Zur Untersuchung Der
Umweltauswirkungen von Kfz-Leitungssätzen Konventioneller Und
Elektrischer Fahrzeuge.” Transformations-Hub Leitungssatz.
<https://www.leitungssatz-hub.de/wp-content/uploads/LCA_Studie_2025_04.pdf>.

</div>

<div id="ref-warnecke_methods_2026" class="csl-entry">

Warnecke, Jann, Steffen Auchtor, Patrick Bründl, and Jörg Franke. 2026.
“Methods and Technologies for Modularising Wire Harness Designs in the
Automotive Industry.” In *Advances in Production Management Systems.
Cyber-Physical-Human Production Systems: Human-AI Collaboration and
Beyond*, edited by Hajime Mizuyama, Eiji Morinaga, Tomomi Nonaka,
Toshiya Kaihara, Gregor von Cieminski, and David Romero, 131–45. Cham:
Springer Nature Switzerland.
<https://doi.org/10.1007/978-3-032-03538-7_10>.

</div>

</div>

[^1]: <https://arena2036.de/digitain/>

[^2]: https://ghgprotocol.org/

[^3]: https://docs.carbon-transparency.org/data-exchange-protocol/

[^4]: https://liusemweb.github.io/CEON/

[^5]: https://liusemweb.github.io/DPPO/

[^6]: https://catenax-ev.github.io/docs/standards/CX-0003-SAMMSemanticAspectMetaModel

[^7]: <https://ecad-wiki.prostep.org/specifications/vec/v220/vec-2.2.0-ontology.ttl>

[^8]: <https://github.com/admin-shell-io/submodel-templates/tree/main/published/Digital%20Battery%20Passport>

[^9]: https://github.com/eclipse-basyx/basyx-aas-web-ui/tree/main/aas-web-ui/src/pages/modules/DPPDemo

[^10]: <https://vws4ls.github.io/>

[^11]: <https://www.leitungssatz-hub.de/en/robotik-challenge/robotik-challenge-2026/begleitforschungs-und-digitalisierungsmodul/>

[^12]: <https://github.com/ARENA2036/THLS-DPP-mnestix-browser>

[^13]: <https://dpp-generator.arena2036.app>
