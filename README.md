# ACTO — Acupuncture Clinical Trial Ontology

This repository contains the datasets and ontology resources accompanying the paper:

**"ACTO: An Acupuncture Clinical Trial Ontology for Knowledge Organization and Evidence Synthesis"**

---

## Repository Contents

| File | Description |
|------|-------------|
| `随机对照试验知识图谱.rdf` | Main RDF knowledge graph (16,870 acupuncture RCTs, 1966–2024) |
| `随机对照试验知识图谱_aligned.rdf` | Ontology-aligned version with ICD-11 and WHO-RA mappings |
| `随机对照试验知识图谱_english.rdf` | English-language version of the knowledge graph |
| `疾病_ICD-11_映射表.csv` | Disease entity to ICD-11 chapter/block code mapping table (2,594 entities) |
| `穴位_WHO-RA_映射表.csv` | Acupoint entity to WHO-RA standard code mapping table (823 aligned points) |

---

## Dataset Statistics

- **Total trials**: 16,870 RCTs (42 countries, 1966–2024)
- **Languages**: Chinese (87%) and English (13%)
- **Disease coverage**: 28 ICD-11 chapters
- **Acupoints**: 2,505 unique entities; 823 (32.9%) aligned to WHO-RA
- **Knowledge graph instances**: 16,464 Trial instances, 14,708 Literature instances

---

## Usage

The RDF files can be loaded into any SPARQL-compatible triple store (e.g., Apache Jena, GraphDB, Stardog).

```sparql
# Example: Query all trials targeting musculoskeletal disorders
SELECT ?trial ?disease WHERE {
  ?trial a acto:AcupunctureTrial ;
         acto:treatsDisease ?disease .
  ?disease acto:hasICD11Code ?code .
  FILTER(STRSTARTS(?code, "FA"))
}
```

---

## License

This dataset is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

## Contact

For questions or collaborations, please open an issue or contact the corresponding author.
