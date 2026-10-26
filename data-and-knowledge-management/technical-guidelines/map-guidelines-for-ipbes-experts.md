---
description: Technical Guideline Series
---

# Map guidelines for IPBES experts

**Developed by Annabell Macphee and Renske Gudde**

**Reviewed by Aidin Niamir - Head of the Technical Support Unit of Data and Knowledge Management**

_For any inquiries, please contact_ [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)

Version 1.0

Last updated: 26 October 2026

DOI:

#### Use(fulness) of maps

Maps are a good way to visualize data. For example, the global biodiversity hotspots can be clearly shown on a map, instead of writing a list of all the locations, or the occurrence data of a single or group of species. Maps can often show patterns and provide information that can be easily assessed, rather than be written out in possibly long descriptions or lists of information. Maps are therefore commonly used in IPBES assessments, for example to show how many documented alien taxa in terrestrial (including freshwater) and marine environment occur (IAS Assessment, Figure 1.4) or a map illustrating that social movements play a crucial role in challenging drivers of biodiversity loss and fostering transformative change (TCA Assessment, Figure SPM.11).

On Friday the 4<sup>th</sup> of September 2026, the UN voted for the use of the Equal Earth projection. This projection reflects the true size of the continents more accurately than the most commonly used Mercator projection. In IPBES, it was already recommended to use the Robinson projection, which is very close to the Equal Earth projection. Since the vote, it is recommended to use the Equal Earth projection for all maps related to IPBES products.

#### Disclaimers

Generally, disclaimers on the use of maps are included on the information page of the assessment, and for each of the individual chapters and Summary for Policymakers. Most commonly, the long form is used:

_The designations employed and the presentation of material on the maps used in the assessment do not imply the expression of any opinion whatsoever on the part of IPBES concerning the legal status of any country, territory, city or area or of its authorities, or concerning the delimitation of its frontiers or boundaries. These maps have been prepared or used for the sole purpose of facilitating the assessment of the broad biogeographical areas represented therein and for purposes of representing scientific data spatially._

But there is also a short form:

_The boundaries and names shown, and the designations used on the maps shown here do not imply official endorsement or acceptance by IPBES._

#### Country borders

If possible, maps should be shown without country borders. Sometimes the use of country borders is sensitive or unclear. Borrowed maps can include country borders, but it should be made clear in the caption of the figure that it was borrowed.

When country borders are necessary, please contact the data tsu for advice ([aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)).

#### &#x20;R and RStudio

To use the script developed to create maps for IPBES products, R and RStudio are needed. They can be downloaded at [https://cran.r-project.org/bin/windows/base/](https://cran.r-project.org/bin/windows/base/) or [https://posit.co/downloads](https://posit.co/downloads)\
R and RStudio are commonly used for statistical analysis and are free to download. Once downloaded, a tutorial script on basic map creation can be downloaded here. Default options are included in the script, such as the use of the Equal Earth projection, the inclusion of all continents including Antarctica and a colour blind-friendly colour scheme. The script can be adjusted to work with any relevant vector or raster data and can be updated to suit any personal preferences.

#### _A. Cartographic Elements_

The following cartographic elements should be included within each map:

* Map with frame and legend
* Grid lines (graticules) (the coordinate lines on a map)

The north arrow and a scale bar are not needed on a map when grid lines are shown. The title of the map should not be included in the map, but should rather be included in the caption of the figure. Additionally, all information on how the map was made, including the layers used to make the map and program and packages that were used, should be either included in the caption, or can be written in a data management report.

#### _B. Projections_

IPBES follows the UN and adopted the Equal Earth projection for all global maps. For maps of countries or regions, national or appropriate regional projections are recommended. When focusing on marine or Pacific themes, Pacific centered maps are recommended. If there is no specific country projection available, the relevant Universal Transverse Mercator zone projection is suggested.

#### _C. Colour Considerations_

Colours are a useful tool within maps to communicate specific information to readers. Incorrect or inconsistent colour schemes can make it difficult for readers to understand the map. The colour schemes should take the most common types of colour blindness into account, so that the maps are as accessible as possible. Additionally, maps should still be clearly understandable when they are printed in greyscale. To avoid any confusion, areas without any information should not be shown in grey, but in a dashed pattern. For the ocean, either white or light sky blue can be used (#87CEFA; RGB: 135, 206, 250). More information can be found in the [Guidelines for Colour](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/guidelines-for-colour).

&#x20;

Feedback on this guideline is welcome, please send any comments or questions to [aidin.niamir@senckenberg.de](mailto:aidin.niamir@senckenberg.de)
