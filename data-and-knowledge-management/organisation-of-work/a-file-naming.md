# A - File naming

**Prepared by Renske Gudde - IPBES Technical Support Unit (TSU) for Knowledge and Data and Rainer M. Krug - IPBES Task Force on Knowledge and Data.**\
**Reviewed by Aidin Niamir and Yanina V. Sica - IPBES Technical Support Unit for Knowledge and Data and the IPBES Task Force on Knowledge and Data (Hanno Seebens and Xubin Pan)**

_For any inquires please contact_ [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)

Version: 1.1 \
Last Updated: 27 February 2024

DOI: [10.5281/zenodo.10004405](https://zenodo.org/doi/10.5281/zenodo.10004405)

The IPBES assessment process is a lengthy and complex process, spanning over multiple years and involving many contributors and products. It is therefore important to easily track and find files related to the assessment. Here, an IPBES specific file name scheme for the assessments is being proposed.

Files used in IPBES should be named in a consistent and standardised way, while simultaneously informing about the content of the file, to avoid file loss and increase findability of the files, transparency of the final assessments, and reusability. For example, using the filename `Fig3.8` or `ILK dialogue meeting Asia` seems to be informative, but when a user is interested in ILK dialogue meeting reports, it is unclear from which assessment the report comes and when the dialogue meeting took place, and when a user finds ‘Fig3.8’ in the download folder on their computer, the file name does not provide any indication of the contents and topic of that file. Having a standardised way to create file names improves the transparency and findability of information, and also avoids file names like `DMR_systematic_review_final_final_JS_final_approved`.

Apart from human understanding, the possibility to parse the file names automatically and deduce information about the file is an important second aspect of the naming conventions.

<figure><img src="../../.gitbook/assets/file_name_figure (1).png" alt=""><figcaption><p>Figure 'Piled higher and deeper' by Jorge Cham.</p></figcaption></figure>

The recommended naming of files is built up in a similar way as the IBAN codes used by banks, and the proposed file name convention for IPBES products is:

**IPBES\_\[assessment abbreviation]\_**_**\[chapter]\_**_**\[document type]\_**_**\[short description]\_**_**\[version]**

In detail: **All sections are required to be filled in**.

IPBES: The acronym IPBES should be always present (in capital letters)

\[assessment\_abbreviation]: the abbreviation of the assessment as was **approved during the scoping of the assessment**, e.g., IAS for invasive alien species, NXS for the Nexus, TCA for transformative change and BBA for business and biodiversity (in capital letters).

| Full Name                                                                                                                                                                    | Short Name                           | Abbreviation |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ | ------------ |
| Methodological assessment of integrated biodiversity-inclusive spatial planning and ecological connectivity                                                                  | Spatial planning assessment          | SPC          |
| Second global assessment of biodiversity and ecosystem services                                                                                                              | Second global assessment             | GA2          |
| Methodological assessment on monitoring biodiversity and nature’s contributions to people                                                                                    | Monitoring assessment                | MTA          |
| Methodological Assessment of the Impact and Dependence of Business on Biodiversity and Nature’s Contributions to People                                                      | Business and biodiversity assessment | BBA          |
| Thematic assessment of the interlinkages among biodiversity, water, food and health                                                                                          | Nexus assessment                     | NXS          |
| Thematic assessment of the underlying causes of biodiversity loss, determinants of transformative change and options for achieving the 2050 vision for biodiversity          | Transformative change assessment     | TCA          |
| Thematic assessment of invasive alien species and their control                                                                                                              | Invasive alien species assessment    | IAS          |
| Thematic assessment of the sustainable use of wild species                                                                                                                   | Sustainable use assessment           | SUA          |
| Methodological assessment regarding the diverse conceptualization of multiple values of nature and its benefits, including biodiversity and ecosystem functions and services | Values assessment                    | VA           |
| Global assessment report on biodiversity and ecosystem services of the Intergovernmental Science-Policy Platform on Biodiversity and Ecosystem Services                      | First global assessment              | GA1          |
| Assessment of land degradation and restoration                                                                                                                               | Land degradation assessment          | LDR          |
| Regional assessment report on biodiversity and ecosystem services for Africa                                                                                                 | Africa assessment                    | AFA          |
| Regional assessment report on biodiversity and ecosystem services for the Americas                                                                                           | Americas assessment                  | AMA          |
| Regional assessment report on biodiversity and ecosystem services for Asia and the Pacific                                                                                   | Asia and the Pacific assessment      | APA          |
| Regional assessment report on biodiversity and ecosystem services for Europe and Central Asia                                                                                | Europe and Central Asia assessment   | ECA          |
| Assessment report on pollinators, pollination and food production                                                                                                            | Pollinators assessment               | PPA          |
| Methodological assessment report on scenarios and models of biodiversity and ecosystem services                                                                              | Scenarios and models assessment      | SCM          |

\[chapter]: chapter and subchapter number or “SPM”, e.g. “Ch5.2”. This is an optional field; if there is no chapter, use “\_\_” (i.e. two underscores) to keep the file name machine readable.

\[document\_type] The kind of document it is (e.g., a meeting report, chapter or dataset). Suggested are the following types (a complete list is maintained by the data tsu):&#x20;

\- [figure ](a-file-naming.md#figure)

\- [table ](a-file-naming.md#table)

\- [data management report ](a-file-naming.md#data-management-report)

\- [meeting report ](a-file-naming.md#meeting-report)

\- [dialogue workshop report ](a-file-naming.md#dialogue-workshop-report)

\- [dataset](a-file-naming.md#dataset)

\[short\_description] should describe the document in preferably 1-5 words (e.g., “dialogue Asia”, “systematic review topic chapter”). Clear descriptions are much easier to use than ambiguous ones, so when it is not possible to add a description in 1-5 words, it is recommended to use more words.

\[version] Version in the format as described in the versioning scheme for IPBES products. The version number indicates at which state in the assessment a file was uploaded. It is therefore important to upload a new version (with updated version in the file name) at every milestone. Access to previous versions can be restricted in order to avoid confusion.

The sections are separated with “\_”, and multiple words within a section can be separated with “ ” (space).

## Examples

### Figure

The final, interoperable, version of figure 3.6 that will be submitted to the Plenary, the phylogeny of marine mammals, of the Sea life assessment:

| Sections                | Example                             |
| ----------------------- | ----------------------------------- |
| IPBES                   | IPBES                               |
| Assessment abbreviation | SLA                                 |
| Chapter                 | Ch3                                 |
| Document type           | figure                              |
| Short description       | Fig 3.6 Phylogeny of marine mammals |
| Version                 | v10.0.0                             |

→ **IPBES\_SLA\_Ch3\_figure\_fig 3.6\_Phylogeny of marine mammals\_v10.0.0.ai**



Figure 7.8 showing the biodiversity hotspots on a global map, that will be submitted for the second external review as part of chapter 7 of the Hotspots assessment:

| Sections                | Example                              |
| ----------------------- | ------------------------------------ |
| IPBES                   | IPBES                                |
| Assessment abbreviation | HA                                   |
| Chapter                 | Ch7                                  |
| Document type           | figure                               |
| Short description       | Fig 7.8 Global biodiversity hotspots |
| Version                 | v2.0.0                               |

**→ IPBES\_HA\_Ch7\_figure\_fig 7.8 Global biodiversity hotspots\_v2.0.0.png**



### Table

The final version of table 5.4 that will be submitted for the first order draft for the Sea life assessment, containing a list of endangered marine animals:

| Sections                | Example                             |
| ----------------------- | ----------------------------------- |
| IPBES                   | IPBES                               |
| Assessment abbreviation | SLA                                 |
| Chapter                 | Ch5                                 |
| Document type           | table                               |
| Short description       | Table 5.4 Endangered marine animals |
| Version                 | v1.0.0                              |

**→ IPBES\_SLA\_Ch5\_table\_Table 5.4 Endangered marine animals\_v1.0.0.docx**



Table 7.11 showing the number of endangered species in biodiversity hotspots, that will be submitted for the third external review as part of chapter 7 of the Hotspots assessment:

| Sections                | Example                                   |
| ----------------------- | ----------------------------------------- |
| IPBES                   | IPBES                                     |
| Assessment abbreviation | HA                                        |
| Chapter                 | Ch7                                       |
| Document type           | table                                     |
| Short description       | Table 7.11 Endangered species in hotspots |
| Version                 | v3.0.0                                    |

**→ IPBES\_HA\_Ch7\_table\_Table 7.11 Endangered species in hotspots\_v3.0.0.docx**



### Data Management Report

The first data management report for figure 4.1 of the invasive alien species assessment, uploaded to Zenodo before the submission for the first external review, would be:

| Sections                | Example                                   |
| ----------------------- | ----------------------------------------- |
| IPBES                   | IPBES                                     |
| Assessment abbreviation | IAS                                       |
| Chapter                 | Ch4                                       |
| Document type           | DMR                                       |
| Short description       | Fig 4.1 biodiversity versus water quality |
| Version                 | v0.0.0                                    |

**→ IPBES\_IAS\_Ch4\_DMR\_Fig4.1 biodiversity versus water quality\_v0.0.0.docx**



The version of the data management report for figure 7.8 on the biodiversity hotspots map for the Hotspots assessment that will be submitted for the second external review as part of chapter 7 of the Hotspots assessment:

| Sections                | Example                           |
| ----------------------- | --------------------------------- |
| IPBES                   | IPBES                             |
| Assessment abbreviation | HA                                |
| Chapter                 | Ch7                               |
| Document type           | DMR                               |
| Short description       | Fig 7.8 biodiversity hotspots map |
| Version                 | v2.0.0                            |

**→ IPBES\_HA\_Ch7\_DMR\_Fig7.8 biodiversity hotspots map\_v2.0.0.docx**



### Meeting report

Report about the third meeting to advance the summary for policymakers of the Sea life assessment:

| Sections                | Example           |
| ----------------------- | ----------------- |
| IPBES                   | IPBES             |
| Assessment abbreviation | SLA               |
| Chapter                 |                   |
| Document type           | Meeting report    |
| Short description       | Third SPM meeting |
| Version                 | v1                |

→ **IPBES\_SLA\_\_meeting report\_Third SPM meeting\_v1**



### Dialogue Workshop Report

The third version of a report on the dialogue meeting for Asia taking place after the second external review would be of the MR assessment:

| Sections                | Example                  |
| ----------------------- | ------------------------ |
| IPBES                   | IPBES                    |
| Assessment abbreviation | MR                       |
| Chapter                 |                          |
| Document type           | Dialogue workshop report |
| Short description       | Dialogue Asia            |
| Version                 | v2.0.3                   |

→ **IPBES\_MR\_dialogue\_\_dialogue report\_Asia\_v2.0.3.zip**



### Dataset

The references found during a systematic literature search on ILK and nature conservation for the Hotspots assessment:

| Sections                | Example                                                             |
| ----------------------- | ------------------------------------------------------------------- |
| IPBES                   | IPBES                                                               |
| Assessment abbreviation | HA                                                                  |
| Chapter                 |                                                                     |
| Document type           | Dataset                                                             |
| Short description       | References systematic literature search ILK and nature conservation |
| Version                 | v1                                                                  |

→ **IPBES\_HA\_\_Dataset\_References systematic literature search ILK and nature conservation\_v1**
