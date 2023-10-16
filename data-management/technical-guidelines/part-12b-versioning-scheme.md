---
description: Technical Guideline Series
---

# Part 12B - Versioning scheme

**Prepared by Renske Gudde - IPBES Technical Support Unit (TSU) for Knowledge and Data and Rainer M. Krug - IPBES Task Force on Knowledge and Data.**\
**Reviewed by Aidin Niamir and Yanina V. Sica - IPBES Technical Support Unit for Knowledge and Data and the IPBES Task Force on Knowledge and Data (Hanno Seebens and Xubin Pan)**

_For any inquires please contact_ [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)

Version: 1.0 \
Last Updated: 16 October 2023

DOI: [10.5281/zenodo.10004408](https://doi.org/10.5281/zenodo.6882518)

The IPBES assessment process is a lengthy and complex process, spanning over multiple years and involving many contributors. It is therefore important to track the versions of all files related to the assessment. Here, an IPBES specific versioning scheme for its assessments is being proposed.

There are usually five milestones during an IPBES assessment process; the first, second, and third order drafts, followed by the version submitted to the Plenary and the final approved version. Fast-track assessments have four milestones; they do not have a third order draft.

The suggested versioning scheme builds on the Semantic Versioning 2.0.0 used in software development ([https://semver.org](https://semver.org)), and is adapted for the usage in the context of IPBES.

The IPBES versioning scheme consists of 3 parts separated by a dot (`.`):

vDRAFT.MAJOR.MINOR.

The DRAFT follows the following scheme:

&#x20; 0\.  [for versions leading up to the first order draft](part-12b-versioning-scheme.md#draft-0)

1. [for final version of FOD and for versions leading up to the SOD](part-12b-versioning-scheme.md#draft-1)\

2. [for final version of SOD and for version leading up to the TOD\
   ](part-12b-versioning-scheme.md#draft-2)
3. [for final version of TOD and for versions leading up to the Plenary\
   ](part-12b-versioning-scheme.md#draft-3)
4. [for final versions as submitted to the Plenary for approval and for requested edits](part-12b-versioning-scheme.md#draft-4)

&#x20; _Drafts 5 - 9 are reserved for any potential versions between the version submitted to the Plenary_ \
&#x20; _and the final approved version for production._&#x20;

&#x20; 10\. [final approved version for production](part-12b-versioning-scheme.md#final-version)&#x20;



The **MAJOR** version starts with 0, going up one number for each new major revision, for example after the addition or removal of paragraphs, figures and/or data.

The **MINOR** version starts usually with 0 and is not often used (but needs to be specified). Minor versions are used for small changes in the text and/or data that do not lead to changes in the results, such as the addition of a reference or correcting of a spelling mistake. Similar to the major versions, for each new minor revision the number goes up by one.



### Draft 0

Before the final draft of the first order draft:

| Description                                                                      | Version |
| -------------------------------------------------------------------------------- | ------- |
| Very first version of a file                                                     | v0.0.0  |
| After making small changes in the text and adding a new reference (minor change) | v0.0.1  |
| After adding another new reference (minor change)                                | v0.0.2  |
| After adding new figures and more text (major change)                            | v0.1.0  |

### Draft 1

Final version of the first order draft and every version before the final version of the second order draft:

| Description                                                          | Version |
| -------------------------------------------------------------------- | ------- |
| File submitted for the first order draft                             | v1.0.0  |
| First version of a file that was created after the FOD was submitted | v1.0.0  |
| After adding another new reference (minor change)                    | v1.0.1  |
| After adding new figures and more text (major change)                | v1.1.0  |

### Draft 2

Final version of the first order draft and every version before the final version of the second order draft:

| Description                                                          | Version |
| -------------------------------------------------------------------- | ------- |
| File submitted for the second order draft                            | v2.0.0  |
| First version of a file that was created after the SOD was submitted | v2.0.0  |
| After adding another new reference (minor change)                    | v2.0.1  |
| After adding new figures and more text (major change)                | v2.1.0  |

### Draft 3

Final version of the third order draft and every version before the final version submitted for the Plenary:

| Description                                                          | Version |
| -------------------------------------------------------------------- | ------- |
| File submitted for the third order draft                             | v3.0.0  |
| First version of a file that was created after the TOD was submitted | v3.0.0  |
| After adding another new reference (minor change)                    | v3.0.1  |
| After adding new figures and more text (major change)                | v3.1.0  |

### Draft 4

Final version to be submitted to the Plenary:

| Description                   | Version |
| ----------------------------- | ------- |
| File submitted to the Plenary | v4.0.0  |

### Final version

Final version that has been approved by the Plenary and is ready for publication:

| Description                    | Version |
| ------------------------------ | ------- |
| File submitted for publication | v10.0.0 |
