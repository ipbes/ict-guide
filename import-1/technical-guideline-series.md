# Technical Guideline Series

### The IPBES Ontology

**Prepared by Maral Dadvar - resource person for the IPBES task force on knowledge and data**

**Reviewed by Aidin Niamir - Head of the Technical Support Unit of Knowledge and Data**

_For any inquires please contact_ [_aidin.niamir@senckenberg.de_](mailto:aidin.niamir@senckenberg.de)

Version: 1.0\
Last Updated: December 19th, 2023

DOI: [10.5281/zenodo.10404414](https://doi.org/10.5281/zenodo.10404414)

### Abstract

The ontology developed for representing intergovernmental reports and the broad topics and information that they cover.

### Table of content

1. Introduction
2. Namespace Declarations
3. The IPBES Ontology Visualisation
4. The IPBES Ontology Description
5. Classes and Attributes
6. References

### 1. Introduction

The Intergovernmental Science-Policy Platform on Biodiversity and Ecosystem Services (IPBES) is the intergovernmental body which assesses the state of biodiversity and of the ecosystem services it provides to society, in response to requests from decision makers. To this end, it produces regular regional, national and global assessment reports in collaborations with many experts, scientists and politicians from a wide range of expertise, nationalities and backgrounds. To our knowledge, there is no existing ontology for representation of intergovernmental reports and the broad topics and information that they cover. To this end, we have created the IPBES ontology as the stepping stone for representing these types of data as LOD and make them accessible for further exploration.

### 3. The IPBES Ontology Visualisation

Figure visualising the IPBES ontology

### 4. The IPBES Ontology Description

The classes and properties used in IPBES ontology are created on the fly based on the information that we encounter and the concepts that we aimed to represent. However, the usage of the properties consistent and the coined URI’s are stable and unique. Currently our ontology consists of 6 classes, each representing a specific part of the data along with their corresponding properties.

### 5. Classes and Attributes

| Classes                    |                             |                                |                                |                               |                            |
| -------------------------- | --------------------------- | ------------------------------ | ------------------------------ | ----------------------------- | -------------------------- |
| [Report](broken-reference) | [Chapter](broken-reference) | [Subchapter](broken-reference) | [KeyMessage](broken-reference) | [Reference](broken-reference) | [Person](broken-reference) |

**Report**

| Class          |                                                                              |
| -------------- | ---------------------------------------------------------------------------- |
| _ipbes.Report_ | [http://www.ontology.ipbes.net/report](http://www.ontology.ipbes.net/report) |

| Properties       |                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------ |
| _skos:prefLabel_ | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| _Skos:altLabel_  | Alternative writing format or language of the preferred label                        |
| _ipbes:year_     | The publication year                                                                 |
| _ipbes:hasDoi_   | The DOI number                                                                       |

**Chapter**

| Class           |                                                                                      |
| --------------- | ------------------------------------------------------------------------------------ |
| _ipbes.Chapter_ | [http://www.ontology.ipbes.net/report/ch/](http://www.ontology.ipbes.net/report/ch/) |

| Properties         |                                                                                      |
| ------------------ | ------------------------------------------------------------------------------------ |
| _skos:prefLabel_   | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| _ipbes:Report_     | Link to the class Report of the chapter                                              |
| _ipbes:hasDoi_     | The DOI number                                                                       |
| _ipbes:identifier_ | The identifier of the chapter or sub-chapter or key message in the report            |
| _foaf.Person_      | The list of persons who have a role in this chapter                                  |

**Subchapter**

| Class              |                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------- |
| _ipbes.SubChapter_ | [http://www.ontology.ipbes.net/report/sch/](http://www.ontology.ipbes.net/report/sch/) |

| Properties             |                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------ |
| _ipbes:identifier_     | The identifier of the chapter or sub-chapter or key message in the report            |
| _ipbes:Chapter_        | Link to the class Chapter of the sub-chapter                                         |
| _ipbes:Report_         | Link to the class Report of the sub-chapter                                          |
| _ipbes:KeyMessage_     | Link to the class KeyMessage for which the sub-chapter has been referred to          |
| _ipbes:reference_      | Link to the class reference for the citations used in each subchapter                |
| _skos:prefLabel_       | The label that is preferred to be used for a chapter, sub-chapter , report or person |
| _ipbes:hasDescription_ | The text that further describes the content                                          |

**Key message**

| Class              |                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------- |
| _ipbes.KeyMessage_ | [http://www.ontology.ipbes.net/report/key/](http://www.ontology.ipbes.net/report/key/) |

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

**Reference**

| Class             |                                                                                        |
| ----------------- | -------------------------------------------------------------------------------------- |
| _ipbes.Reference_ | [http://www.ontology.ipbes.net/report/ref/](http://www.ontology.ipbes.net/report/ref/) |

| Properties             |                                                                   |
| ---------------------- | ----------------------------------------------------------------- |
| _ipbes:Chapter_        | Link to the class Chapter in which the reference has been used    |
| _ipbes:Report_         | Link to the class Report                                          |
| _ipbes:SubChapter_     | Link to the class SubChapter in which the reference has been used |
| _ipbes:zotero_         | Link to the zotero repository of the reference                    |
| _ipbes:hasDescription_ | The text that further describes the content                       |
| _ipbes:hasDoi_         | The DOI number                                                    |

**Person**

| Class         |                                                                                              |
| ------------- | -------------------------------------------------------------------------------------------- |
| _foaf.Person_ | [http://www.ontology.ipbes.net/report/person/](http://www.ontology.ipbes.net/report/person/) |

| Properties       |                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------- |
| _foaf:firstName_ | First name of the person                                                            |
| _foaf:lastName_  | Family name of the person                                                           |
| _skos:prefLabel_ | The label that is preferred to be used for a chapter, sub-chapter, report or person |
| _ipbes:orcID_    | ORCID identifier of the person                                                      |
| _ipbes:country_  | Country of residence of the person                                                  |
| _ipbes:ca_       | Contributing authors in the stated chapter and report                               |
| _ipbes:cl_       | Coordinating lead authors in the stated chapter and report                          |
| _ipbes:fl_       | Fellows in the stated chapter and report                                            |
| _ipbes:cs_       | Co-chairs in the stated chapter and report                                          |
| _ipbes:la_       | Lead authors in the stated chapter and report                                       |
| _ipbes:re_       | Review editors in the stated chapter and report                                     |
