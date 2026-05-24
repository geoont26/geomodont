# GeoMod Ontology (geomodont)

GeoMod (`geomodont`) is an OWL/RDF ontology designed to define and propose **conceptual validation rules for geomodels**. 

Geological models often suffer from structural inconsistencies or physical impossibilities. GeoMod addresses this by formalizing structural constraints and validation rules, describing geo-model components across both their **physical** and **geological** dimensions.

## 🏗️ Architecture & Foundations

To ensure semantic interoperability and robust domain logic, GeoMod is structurally aligned with established upper and domain ontologies:
* **Basic Formal Ontology (BFO):** Acts as the foundational top-level ontology, providing standard categories (such as continuants and occurrents).
* **GeoCore Ontology:** Serves as the core geological domain ontology, inheriting foundational definitions for architectural geological objects.



---

## 🛠️ Current Scope & Limitations
* **Isolated Knowledge Base:** This repository contains *only* the semantic code (the ontology itself). 
* **Future System Integration:** While GeoMod is architected to be integrated into broader geomodelling software and automated verification pipelines down the line, it currently operates as a standalone reference model. No software integrations or plugins are active in this version.

---

## ⚙️ Technical Details & Requirements

* **Format:** RDF/XML (`.owl` or `.rdf`)
* **Primary Tool:** Designed and tested for use with [Protégé](https://protege.stanford.edu/), the open-source ontology editor.

### How to open the ontology:
1. Download and install **Protégé** (v5.5.0 or higher recommended).
2. Clone or download this repository to your local machine.
3. Open Protégé, select **File -> Open...** and navigate to the `geomodont` RDF/XML file (e.g., `geomodont.owl`).
4. (Optional) Fire up the **HermiT** or **Pellet** reasoner inside Protégé to execute and review the conceptual validation rules.

---
### synthetic test
The file test.owl presents a simple example on how to use geomodont to verify inforamtion of a geological model.

If:
- G is an Intrusive Magmatic Unit
- Outer G is Magmatic Intrusive Outer Surface  
- Outer G  is Boundary-of  G

- E is an Erosion Surface
- Outer G interrupts E (Boundary/Boundary Topological Relation)

- U is an Elementary Depositional Unit  
- H is a Stratigraphic Horizon
- H is ChronoTop of U

Then:
- G is younger than U  (Unit/Unit Age Relation)

## 📂 Repository Structure
```text
├── LICENSE                 # Full text of the CC BY-SA 4.0 license
├── README.md               # This documentation file
├──geomodont.owl           # The primary RDF/XML ontology code
├── source_ontologies       # a folder with the geomodont importing BFO and geocore
└── test.owl                # a simple test file

