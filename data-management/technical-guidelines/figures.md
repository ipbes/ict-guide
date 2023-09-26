---
description: Technical Guideline Series
---

# Part 8 - Guidelines for the delivery of figures

**Prepared by Joy Kumagai - IPBES Technical Support Unit (TSU) of Knowledge and Data**\
**Reviewed by the Task Force on Knowledge and Data (Hanno Seebens, Rainer Krug, András Báldi, Xubin Pan, and Aidin Niamir)**

_For any inquires please contact_ [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)

Version: 1.1 \
Last Updated: 14 July 2022

DOI: [10.5281/zenodo.6833989](https://doi.org/10.5281/zenodo.6833989)

This technical guideline provides guidance on figures within IPBES assessments, with particular emphasis on long-term storage in repositories. The guideline is intended for IPBES assessment technical support units or anyone storing figures within IPBES assessments.

## I. Overarching guidance

* All figures, except for those borrowed (i.e. not modified) from external sources, are stored on Zenodo. Figures can then be accessed in the long-term, enabling reuse by others and future IPBES experts.
* When uploading a figure to a repository, please specify which chapter it belongs to and the figure number. Additionally, please include the related identifiers, specifically the DOI of the assessment chapter and/or the associated data management report it appears in. At a quick glance, viewers should be able to track where a figure appears within the assessment.
* Please provide editable, high resolution figures in vector format which enables graphic designers to edit the figure. Vector formats could be pdf, eps, or others as specified in the [file formats guideline](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/file-formats). If the graphic designer needs to edit a figure, the new version should be uploaded to the same repository as an additional file.
* It is incredibly important that permission for any borrowed or adapted figures is granted and documented as early as possible. If permission can not be secured, then the figure can not be used in the assessment.

## II. Double check these items

Please double check the following items to ensure the figures are in line with IPBES guidance.

* If there are country borders displayed, there are certain rules for borders and a few regions that need to be adhered to ([https://doi.org/10.5281/zenodo.5883632](https://doi.org/10.5281/zenodo.5883632)).
* World maps are in the [robinson projection](https://epsg.io/54030).
* Country names are in [ISO 3166-1 alpha 3 code](https://www.iso.org/iso-3166-country-codes.html) within figures. If full names are needed in captions for clarity, they are fully spelt out according to current UN guidance. Names can be double checked with the interactive map on [this UN website](https://www.un.org/geospatial/mapsgeo/webservices).
* Colors used in figures are color blind friendly.
* Licenses behind IPBES original figures are [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/) or [CC-BY](https://creativecommons.org/licenses/by/4.0/).

## III. What to include in each repository

Depending on the type of figure, there are different items that need to be part of the repository and checked. Please go through the following lists for each figure in the assessment.

### A. Created by IPBES experts

* **Schematic figures**
  * Upload the native/original file of the figure (e.g. powerpoint file).
  * Upload the figure in an open format and high resolution (600 dpi).
  * Assign the license ([CC0](https://creativecommons.org/share-your-work/public-domain/cc0/) or [CC BY](https://creativecommons.org/licenses/by/4.0/)). Divergent licenses need to be approved by TSU K\&D.
  * Upload the caption in a separate text file together with the figure. The caption should contain the DOI of the figure and [disclaimer](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/cartographic-guidelines#ii.-disclaimers) where necessary. Please see [our guidance](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/Zenodo#b.-how-to-reserve-a-doi) on how to reserve a DOI before publishing.\

* **Data driven figures**
  * Upload the workflows/scripts that were used to create the figure.
  * Upload the data sources themselves or specify the references to the data sources underlying the figure in the associated data management report, which can be included in the same repository.
  * Upload the figure in an [open format](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/file-formats) and in high resolution (600 dpi or vector format).
  * Assign the license ([CC0](https://creativecommons.org/share-your-work/public-domain/cc0/) or [CC BY](https://creativecommons.org/licenses/by/4.0/)). Divergent licenses need to be approved by TSU K\&D.
  * Upload the caption in a separate text file together with the figure. The caption should contain the DOI of the figure and [disclaimer](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/cartographic-guidelines#ii.-disclaimers) where necessary. Please see [our guidance](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/Zenodo#b.-how-to-reserve-a-doi) on how to reserve a DOI before publishing.
  * Please also check that country names in **the data** follow the [ISO 3166 1 alpha 3 code](https://www.iso.org/iso-3166-country-codes.html).

### B. Created by an external source

* **Borrowed figures (unmodified)**
  * These figures do not need to be uploaded to Zenodo, but please check the following:
    * Permission to reuse the figure has been granted and recorded.
    * The source of the figure is cited properly in the Zotero library.
    * The figure has been reviewed for compliance with the IPBES guidelines, specifically the figure is color-blind friendly and if country borders are included, they follow [UN guidance](https://doi.org/10.5281/zenodo.5883632). If the figure is not compliant, options are explored to adapt the figure.
    * The figure is in high resolution (600 dpi or vector format).
    * The caption has a [disclaimer](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/cartographic-guidelines#ii.-disclaimers) where necessary.\

* **Adapted figures (modified)**
  * Upload the figure in an [open format](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/file-formats) and in high resolution (600 dpi or vector format).
  * Upload the caption in a separate text file together with the figure. The caption should contain the DOI of the figure and [disclaimer](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/cartographic-guidelines#ii.-disclaimers) where necessary. Please see [our guidance](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/Zenodo#b.-how-to-reserve-a-doi) on how to reserve a DOI before publishing.
  * Specify the usage rights.
  * Please also check:
    * Permission to reuse and adapt the figure has been granted and recorded.
    * The source of the figure is cited properly in the Zotero library.
    * The figure has been reviewed for compliance with the IPBES guidelines, specifically the figure is color-blind friendly and if country borders are included, they follow [UN guidance](https://doi.org/10.5281/zenodo.5883632). If the figure is not compliant, options are explored to adapt the figure.

## IV. Examples

In this section, examples for each type of figure are provided with links to the associated data deposit pacakge, except for borrowed figures which do not need a data deposit package.

### Original schematic figure

![Chapter 5 of the Values Assessment - Figure 5.4](../../.gitbook/assets/VA\_figure5.4)

The data deposit package associated with this figure can be found here: [https://doi.org/10.5281/zenodo.4359655](https://doi.org/10.5281/zenodo.4359655)

### **Original data driven figure**

![Chapter 4 of the Values Assessment - Figure 4.15](../../.gitbook/assets/VA\_figure4.15)

The data deposit package associated with this figure can be found here: [https://doi.org/10.5281/zenodo.6468917](https://doi.org/10.5281/zenodo.6468917)

### **Adapted figure**

![Chapter 3 of the Sustainable Use Assessment - Figure 3.21](../../.gitbook/assets/SU\_figure3.21)

The data deposit package associated with this figure can be found here: [https://doi.org/10.5281/zenodo.6453019](https://doi.org/10.5281/zenodo.6453019)
