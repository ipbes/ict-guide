# IPBES Ontology

**Prepared by Maral Dadvar and Aidin Niamir**

**Contributors: Dave Thau, Benedict Omare and Renske Gudde**

_For any inquires please contact_ [_aidin.niamir@senckenberg.de_](mailto:aidin.niamir@senckenberg.de)

Version: 1.0\
Last Updated: January 22nd, 2024

DOI: [10.5281/zenodo.10404414](https://doi.org/10.5281/zenodo.10404414)

### Abstract

The ontology developed for representing intergovernmental reports and the broad topics and information that they cover.

### Table of content

1. [Introduction](ipbes-ontology.md#1.-introduction)
2. [Namespace Declarations](ipbes-ontology.md#2.-namespace-declarations)
3. [The IPBES Ontology Description](ipbes-ontology.md#3.-the-ipbes-ontology-description)
4. [Classes and Attributes](ipbes-ontology.md#4.-classes-and-attributes)
5. [References](ipbes-ontology.md#5.-references)

### 1. Introduction

The Intergovernmental Science-Policy Platform on Biodiversity and Ecosystem Services (IPBES) is the intergovernmental body which assesses the state of biodiversity and of the ecosystem services it provides to society, in response to requests from decision makers. To this end, it produces regular regional, national and global assessment reports in collaborations with many experts, scientists and politicians from a wide range of expertise, nationalities and backgrounds. To our knowledge, there is no existing ontology for representation of intergovernmental reports and the broad topics and information that they cover. To this end, we have created the IPBES ontology as the stepping stone for representing these types of data as LOD and make them accessible for further exploration.

### 2. Namespace Declarations

This is the list of the namesspaces used in this ontology.

<table><thead><tr><th width="282">Namespace prefix</th><th>Namespace URI</th></tr></thead><tbody><tr><td>ipbes</td><td><a href="https://ontology.ipbes.net/report">https://ontology.ipbes.net/report</a></td></tr><tr><td>foaf</td><td><a href="http://xmlns.com/foaf/0.1/">http://xmlns.com/foaf/0.1/</a></td></tr><tr><td>skos</td><td><a href="http://www.w3.org/2004/02/skos/core">http://www.w3.org/2004/02/skos/core#</a></td></tr></tbody></table>

### 3. The IPBES Ontology Description

The classes and properties used in IPBES ontology are created on the fly based on the information that we encounter and the concepts that we aimed to represent. However, the usage of the properties is consistent and the coined URI’s are stable and unique. Currently our ontology consists of 6 classes, each representing a specific part of the data along with their corresponding attributes.

### 4. Classes and Attributes

| Classes                            |                                      |                                            |                                             |                                          |                                    |
| ---------------------------------- | ------------------------------------ | ------------------------------------------ | ------------------------------------------- | ---------------------------------------- | ---------------------------------- |
| [Report](ipbes-ontology.md#report) | [Chapter](ipbes-ontology.md#chapter) | [Subchapter](ipbes-ontology.md#subchapter) | [KeyMessage](ipbes-ontology.md#key-message) | [Reference](ipbes-ontology.md#reference) | [Person](ipbes-ontology.md#person) |

#### **Report**

| Class          |                                                                      |
| -------------- | -------------------------------------------------------------------- |
| _ipbes.Report_ | [http://ontology.ipbes.net/report](http://ontology.ipbes.net/report) |

| Properties       |                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------ |
| _skos:prefLabel_ | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| _Skos:altLabel_  | Alternative writing format or language of the preferred label                        |
| _ipbes:year_     | The publication year                                                                 |
| _ipbes:hasDoi_   | The DOI number                                                                       |

#### **Chapter**

| Class           |                                                                              |
| --------------- | ---------------------------------------------------------------------------- |
| _ipbes.Chapter_ | [http://ontology.ipbes.net/report/ch/](http://ontology.ipbes.net/report/ch/) |

| Properties         |                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------- |
| _skos:prefLabel_   | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| _ipbes:Report_     | Link to the class Report of the chapter                                             |
| _ipbes:hasDoi_     | The DOI number                                                                      |
| _ipbes:identifier_ | The identifier of the chapter or sub-chapter or key message in the report           |
| _foaf.Person_      | The list of persons who have a role in this chapter                                 |

#### **Subchapter**

| Class              |                                                                                |
| ------------------ | ------------------------------------------------------------------------------ |
| _ipbes.SubChapter_ | [http://ontology.ipbes.net/report/sch/](http://ontology.ipbes.net/report/sch/) |

| Properties             |                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------ |
| _ipbes:identifier_     | The identifier of the chapter or sub-chapter or key message in the report            |
| _ipbes:Chapter_        | Link to the class Chapter of the sub-chapter                                         |
| _ipbes:Report_         | Link to the class Report of the sub-chapter                                          |
| _ipbes:KeyMessage_     | Link to the class KeyMessage for which the sub-chapter has been referred to          |
| _ipbes:Reference_      | Link to the class reference for the citations used in each subchapter                |
| _skos:prefLabel_       | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| _ipbes:hasDescription_ | The text that further describes the content                                          |

#### **Key message**

| Class              |                                                                                |
| ------------------ | ------------------------------------------------------------------------------ |
| _ipbes.KeyMessage_ | [http://ontology.ipbes.net/report/key/](http://ontology.ipbes.net/report/key/) |

| Properties                       |                                                                                     |
| -------------------------------- | ----------------------------------------------------------------------------------- |
| _ipbes:SubChapter_               | Link to the class SubChapter in which the key message has been referred to          |
| _ipbes:identifier_               | The identifier of the chapter or sub-chapter or key message in the report           |
| _ipbes:Report_                   | Link to the class Report of the key message                                         |
| _skos:prefLabel_                 | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| _ipbes:hasDescription_           | The text that further describes the content                                         |
| _ipbes:hasEstablishedIncomplete_ | Level of confidence                                                                 |
| _ipbes:hasWellestablished_       | Level of confidence                                                                 |
| _ipbes:hasUnresolved_            | Level of confidence                                                                 |
| _ipbes:hasInconclusive_          | Level of confidence                                                                 |

#### **Reference**

| Class             |                                                                                |
| ----------------- | ------------------------------------------------------------------------------ |
| _ipbes.Reference_ | [http://ontology.ipbes.net/report/ref/](http://ontology.ipbes.net/report/ref/) |

| Properties             |                                                                   |
| ---------------------- | ----------------------------------------------------------------- |
| _ipbes:Chapter_        | Link to the class Chapter in which the reference has been used    |
| _ipbes:Report_         | Link to the class Report                                          |
| _ipbes:SubChapter_     | Link to the class SubChapter in which the reference has been used |
| _ipbes:zotero_         | Link to the zotero repository of the reference                    |
| _ipbes:hasDescription_ | The text that further describes the content                       |
| _ipbes:hasDoi_         | The DOI number                                                    |

#### **Person**

| Class         |                                                                                      |
| ------------- | ------------------------------------------------------------------------------------ |
| _foaf.Person_ | [http://ontology.ipbes.net/report/person/](http://ontology.ipbes.net/report/person/) |

| Properties       |                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------- |
| _foaf:firstName_ | First name of the person                                                            |
| _foaf:lastName_  | Family name of the person                                                           |
| _ipbes:Chapter_  | Link to the class Chapter in which the person has a role                            |
| _ipbes:Report_   | Link to the class Report                                                            |
| _skos:prefLabel_ | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| _ipbes:orcID_    | ORCID identifier of the person                                                      |
| _ipbes:country_  | Country of residence of the person                                                  |
| _ipbes:ca_       | Contributing authors in the stated chapter and report                               |
| _ipbes:cl_       | Coordinating lead authors in the stated chapter and report                          |
| _ipbes:fl_       | Fellows in the stated chapter and report                                            |
| _ipbes:cs_       | Co-chairs in the stated chapter and report                                          |
| _ipbes:la_       | Lead authors in the stated chapter and report                                       |
| _ipbes:re_       | Review editors in the stated chapter and report                                     |

### 5. References

[https://www.w3.org/2009/08/skos-reference/skos.html](https://www.w3.org/2009/08/skos-reference/skos.html)

[http://xmlns.com/foaf/0.1/](http://xmlns.com/foaf/0.1/)
