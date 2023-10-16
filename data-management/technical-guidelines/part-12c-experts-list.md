---
description: Technical Guideline Series
---

# Part 12C - Experts list

**Prepared by Renske Gudde - IPBES Technical Support Unit (TSU) for Knowledge and Data and Rainer M. Krug - IPBES Task Force on Knowledge and Data.**\
**Reviewed by Aidin Niamir and Yanina V. Sica - IPBES Technical Support Unit for Knowledge and Data and the IPBES Task Force on Knowledge and Data (Hanno Seebens and Xubin Pan)**

_For any inquires please contact_ [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)

Version: 1.0 \
Last Updated: 16 October 2023

DOI: [10.5281/zenodo.10004410](https://doi.org/10.5281/zenodo.6882518)

Benefit sharing, by giving credit to those who contribute by properly acknowledging them, is important within IPBES. It is therefore important that the technical support units for assessments compile accurate information on the experts and maintain such information in a transparent and comprehensive manner.

#### The General Data Protection Regulation (GDPR)&#x20;

The [GDPR is a regulation on data protection and privacy in the EU](https://eur-lex.europa.eu/eli/reg/2016/679/oj), which protects the privacy and personal data of all EU citizens. It is rooted in seven principles for privacy: lawfulness, fairness and transparency (gathering data with a valid legal basis in the best interest of the people data is collected from, and transparent in a way that it is clear what, how and why data is collected); purpose limitation (using the data only for the initially stated purpose); data minimisation (not gathering more data than is necessary); accuracy (data must be correct and up to date); storage limitations (deleting personal data when it is not needed anymore); integrity and confidentiality (ensuring that the data cannot be manipulated by others and making sure that the only people with access to personal data are the ones processing it); and accountability (taking responsibility for proper processing of personal data and compliance with the rules of the GDPR).

There are [comparable rights and laws for other countries and regions](https://insights.comforte.com/countries-with-gdpr-like-data-privacy-laws), such as the Data Protection Act 2018 in the UK, the Privacy Amendment to Australia’s Privacy Act, the Personal Information Protection Law in China, the Nigeria Data Protection Regulation, the South Africa’s Protection of Personal Information Act, and the Digital Charter Implementation Act in Canada. Personal data can be sensitive, and it is therefore important that these data are collected and stored with the consent of the experts.

In compliance with the GDPR, IPBES ensures to collect the minimum personal data that is required to guarantee that each expert and contributor is properly and sufficiently acknowledged. The information required is therefore: full name; preferred name which will be used in the citation or acknowledgement; title; gender; country of nationality and country of residence (if different); email address, and, optional, an ORCID iD.

* **Name**: Last name; first name; full name and preferred spelling of name (if different from the full name, for example, when Peter John Smith prefers to be called John Smith, or when authors prefer their names without the original accent marks).
* **Country**: Both the country of nationality and the country of residence, if different. The country names have to follow the [UN recommendations](https://www.un.org/en/about-us/member-states).
* **Affiliation**: The complete affiliation(s) of the expert that are relevant to their IPBES contribution. For example, when an experts works for a specific lab or department at the School of Biological Sciences of the University of Edinburgh, the affiliation would be: University of Edinburgh, Edinburgh, United Kingdom. If an expert has more than one affiliation, these should all be added.
* **Email**: Any email address, work related or private (preferably both), which is the preferred way of IPBES and/or assessment related communication
* **ORCID iD**: Optional. An [ORCID iD](https://orcid.org/) is a personal digital identifier, which is often used by researchers to increase findability of their work and the distinguishing from other researchers with the same or a similar name. It is highly recommended for all contributors to obtain an ORCID iD to make them uniquely attributable, even if they are not publishing in the academic sector. The tsu for data can help with any problems encountered during the registration process.

The assessment technical support unit has to submit the list of experts to the secretariat to add them to the internal expert database and avoid duplication and different personal details. To ensure data protection and privacy protection, each assessment should have their own expert dataset, containing only the experts involved in that assessment.

### Roles and responsibilities

**Secretariat**:

* assigns the expert id to the experts upon their first role within IPBES
* keeps the experts database up to date and available to the technical support units for the assessments
* answer any questions that may arise about data protection

**Assessment TSU**:

* Before each submission of a draft, confirm with the authors that all details are still correct.

**Lead Authors**:&#x20;

* make sure that all authors and new contributing authors and other contributors are communicated to the Assessment TSU

**TSU for data**:&#x20;

* include a section on the GDPR and the way that personal data is collected, handled and stored in the IPBES data and knowledge management policy, and making sure that this information is regularly updated with any updates on the GDPR

**Authors / Experts**:&#x20;

* ensure that all your information is correct and complete, and that any updates and changes are communicated as soon as possible. **It is in their interest that the information is up to date and correct.**

### Required experts' information

<table><thead><tr><th>Item</th><th>Name</th><th width="200">Type</th><th>Description</th><th>Obtained from/provided by</th></tr></thead><tbody><tr><td>Expert_id</td><td>Expert id</td><td>[LongText]</td><td>The unique expert id used within IPBES</td><td>Secretariat</td></tr><tr><td>Chapter</td><td>Chapter</td><td>[Numerical]</td><td>Chapter in which the expert is involved</td><td>Assessment tsu</td></tr><tr><td>Role</td><td>Role in the assessment</td><td>[ShortText]</td><td>Role of the expert within the assessment</td><td>Assessment tsu</td></tr><tr><td>First name</td><td>First name</td><td>[LongText]</td><td>Official spelling of the first name of the expert</td><td>Authors and other contributors</td></tr><tr><td>Additional name(s) (if applicable)</td><td>Additional names</td><td>[LongText]</td><td>Middle names of the expert, if applicable</td><td>Authors and other contributors</td></tr><tr><td>Last name</td><td>Last name</td><td>[LongText]</td><td>Official spelling of the last name of the expert</td><td>Authors and other contributors</td></tr><tr><td>Citation name</td><td>Citation name</td><td>[LongText]</td><td>The preferred spelling of the complete name of the expert (which will be used in the citation of the assessment/chapter)</td><td>Authors and other contributors</td></tr><tr><td>Citation name in UTF-8</td><td>Citation name <br>(UTF-8)</td><td>[LongText]</td><td>The preferred spelling of the complete name of the expert converted into UTF-8</td><td>Assessment tsu</td></tr><tr><td>Country(ies) of citizenship</td><td>Country of citizenship</td><td>[ShortText]</td><td>The country of citizenship of the expert (the nationality of the expert at birth)</td><td>Authors and other contributors</td></tr><tr><td>The ISO 3166-1 alpha 3 code of the country of citizenship</td><td>ISO code for the country of citizenship</td><td>[ShortText]</td><td>The ISO 3166-1 alpha 3 code of the country of nationality</td><td>Assessment tsu</td></tr><tr><td>Country(ies) of affiliation</td><td>Country of affiliation</td><td>[ShortText]</td><td>Country(ies) of affiliation</td><td>Authors and other contributors</td></tr><tr><td>The ISO 3166-1 alpha 3 code of the country of affiliation</td><td>ISO code for the country of affiliation</td><td>[ShortText]</td><td>The ISO 3166-1 alpha 3 code of the country(ies) of affiliation</td><td>Assessment tsu</td></tr><tr><td>Complete affiliations</td><td>Complete affiliations</td><td>[LongText]</td><td>The complete affiliations of the expert</td><td>Authors and other contributors</td></tr></tbody></table>

[The excel template (CSV with UTF-8 formatting) for the experts list](https://docs.google.com/spreadsheets/d/1jyfP8FWgV3iPv1aw4bKaxjXkDr8jWmmBJqG7TDFV6Z0/edit?usp=sharing), including example information of a fictional expert called John Smith.

<figure><img src="../../.gitbook/assets/Experts_list_figure (2).png" alt=""><figcaption><p>Example figure of the expert database and the specific assessment expert database, that are linked through the expert id. From the complete personal information, the email address can be added to the assessment expert database.</p></figcaption></figure>
