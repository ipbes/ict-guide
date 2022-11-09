---
description: Technical Guideline Series
---

# Part 6 - How to Upload to and Download from Zenodo

**Prepared by Joy Kumagai - Technical Support Unit (TSU) of Knowledge and Data**

**Reviewed by the Task Force on Knowledge and Data and Benedict Omare - Information Management Officer**

_For any inquires please contact_ [_tsu.data@ipbes.net_](mailto:tsu.data@ipbes.net)

Version: 1.1 \
Last Updated: 14 July 2022

DOI: [10.5281/zenodo.6834336](https://doi.org/10.5281/zenodo.6834336)

Within this guideline, we cover how to upload, share, and download to Zenodo both manually and programmatically. This technical guideline is intended for IPBES technical support units and provides useful tips and options, but does not seek to be comprehensive. The material presented here incorporates and builds upon the guide available here: [https://ict.ipbes.net/repositories/zenodo](https://ict.ipbes.net/repositories/zenodo).

## I. Zenodo overview

[Zenodo](https://zenodo.org/) is a general-purpose free and open-access repository operated by the European Organization for Nuclear Research (CERN). It allows researchers in any subject area to deposit data sets, research software, reports, and any other research related digital artifacts.

Zenodo provides the following services:

* A persistent Digital Object identifier (DOI) is assigned for each upload to make it citable, traceable and findable
* Metadata of each record is sent to DataCite servers during DOI registration and indexed there
* Data and metadata will be retained for the lifetime of the repository. This is defined as the lifetime of the host laboratory CERN, which currently has an experimental programme defined for the next 20 years
* Storage of large file sizes of up to 50 GB
* Versioning of data
* Integration with GitHub
* All data and metadata uploaded is traceable to a registered Zenodo user

For IPEBS, [Zenodo](https://zenodo.org/) is the repository for long term storage of all IPBES products, including milestones, data deposit packages and associated data management reports.

The IPBES secretariat has created and is maintaining one single community on Zenodo for IPBES ([https://zenodo.org/communities/ipbes/](https://zenodo.org/communities/ipbes/)) where the goal is to provide:

1. Access to IPBES products
2. A digital object identifier (DOI) to enable citation of the product or deposit including direct access to its digital representation
3. Search functionality in numerous platforms (e.g. CrossRef, DataCite, PubMed, RefBank, GNUB and Mendeley)

Uploads to the IPBES community on Zenodo must be material that has been prepared for IPBES.

## II. How to upload to Zenodo manually

The purpose of this section is to provide helpful guidance on specific aspects as opposed to going into detail on each part of the form for manual upload.

### A. Some important things to mention

1. Descriptive metadata can be modified after publishing without changing the DOI. Files can also be re-uploaded but all data uploads are permanently stored and issued with unique version numbers and DOIs. Therefore, extra care should be used when uploading files.
2. [Zenodo sandbox](https://sandbox.zenodo.org/) can be used to become familiar with the interface and practice without permanently uploading files
3. A DOI can be reserved by creating a new Zenodo upload draft, selecting "Reserve DOI" under the basic information section, and saving the draft. The identifier can now be added to any documentation, including a data management report for the same upload
4. ORCIDs should be provided whenever possible
5. Please add your entry to the IPBES community, by searching **IPBES secretariat** within the upload form in the second section. The submission has to be approved by secretariat before it appears in the community

### B. How to reserve a DOI

To obtain a digital object identifier for an entry on Zenodo, please first log into your account and start [a new upload on Zenodo](https://zenodo.org/deposit/new). Note that the account should be affiliated with your IPBES email address if available.

Under the section _Basic information_, the first field asks for a digital object identifier and directly below the descriptive text there is a box named "Reserve DOI" (see figure 1). Once this button is pressed, the text box then automatically fills in with the assigned DOI. Once you save the draft entry, which requires filling in sections with a red asterisk next to them (which can be changed at a later date), this is the corresponding DOI to the draft upload.

![Figure 1: Reserving a DOI on Zenodo](<../../.gitbook/assets/Figure1 (1)>)

If creating a data management report, please include this reserved DOI at the top of the report and use the same drafted Zenodo entry for the data deposit package.

### C. Authors versus contributors

The upload form for Zenodo has two explicit places where people can be attributed for their work. One can specify author names in the _Basic information_ section, and other contributor names under the _Contributors_ section further down the form.

Each Zenodo entry requires that at least one author name is listed per repository item. The author names then appear on the repository web page directly underneath the title and are added to the citation. The contributor names appear one line below the authors on the website and are categorized according to their specific role, but these names are not listed within the citation. An example of this can be found within the [IPBES Data Management Tutorials](https://doi.org/10.5281/zenodo.4020373) upload where the author is listed as the IPBES task force on knowledge and data, but editors, project leaders, and project members are specified to acknowledge the specific contributions of the members.

Within the form, the role of each contributor can be specified. There are many options which provide valuable information, such as contact person or research group. Some of the options are pictured in Figure 2.

![Figure 2: Options of some available roles for names listed under the Contributors section.](<../../.gitbook/assets/Figure3 (1)>)

### D. Related identifiers

Related identifiers are an incredibly useful tool that can help users understand the connections between products and easily navigate between them. For example, if one is interested in a data management report and finds the Zenodo upload, they can easily click on the related chapter and see how the analysis appears within the actual assessment chapter.

For data management reports associated with IPBES assessments, adding the DOI to the associated assessment chapter on Zenodo is important to maintain the relationship between the products.

There are a variety of options to specify relationships between products, such as the following:

* "is supplemented by this upload" / "is a supplement to this upload"
* "describes this upload" / "is described by this upload"
* "continues this upload" / "is continued by this upload"

Additionally, ISBNs, URLs, and other identifiers can be used in addition to DOIs.

An example of how these related identifiers work can be found on the IPBES Data Management Tutorials Zenodo page pictured below.

![Figure 3: Example of related identifiers specified on the overarching IPBES Data Management Tutorials Zenodo upload (https://doi.org/10.5281/zenodo.4020373)](../../.gitbook/assets/Figure4\_related\_identifier)

### E. Access and licenses

Uploads related to IPBES assessments should be set to open access at the latest one calendar month following the adoption of the assessment by Plenary, unless a longer embargo period is approved by the task force on knowledge and data. Please see the IPBES data and knowledge management policy for more information.

Restricted access:\
If you select restricted access, you will need to specify the conditions under which you grant users access to the files in your upload. A user requesting access will be asked to justify how they fulfill the conditions. Based on the justification, you decide who to grant/deny access. You are not allowed to charge users for granting access to data hosted on Zenodo.

The following licenses can be specified on Zenodo:

* Creative Commons Attribution 4.0 International **- Recommended**
* Creative Commons Attribution 1.0 Generic
* Creative Commons Attribution 2.0 Generic
* Creative Commons Attribution 3.0 Unported
* Creative Commons Attribution 3.0 Austria
* Creative Commons Attribution 3.0 Germany
* Creative Commons Attribution 3.0 Netherlands
* Creative Commons Attribution 3.0 United States

### F. Versioning and Keywords:

Please add version numbers to all entries. If the entry is updated, the version number and date can be used to keep track of which version was available and used.

To aid in discoverability, it can be helpful to add keywords to your upload that describe the deliverable, document type, and/or descriptive term.

For example:

* Deliverable: global assessment; values assessment; invasive alien species assessment
* Document Type: Full assessment report; Summary for Policymakers; Supplementation material; data management report
* Descriptive term: Data policy

## III. How to upload to Zenodo using GitHub

Zenodo and GitHub have the possibility of being linked so that a new release on GitHub can create a new or an update to an existing Zenodo repository. Here we will discuss the context-specific considerations for IPBES and give a overview of the process.

One case where it would be helpful to have this link established would be if one has a project which utilizes a set of codes for and analysis with associated figures. The code, resulting figures, and data management report (perhaps in markdown format) could be included in the GitHub repository, and each release for a milestone draft could automatically have the associated Zenodo page updated.

Unfortunately, your repository on GitHub needs to be public for it to be published on Zenodo. Also, the access is automatically set to public on the Zenodo entry. Thus, the access would need to be adjusted after the release to restricted instead. IPBES products stemming from assessments need to be set to restricted access until the assessment is approved by Plenary.

To link your GitHub repository to a Zenodo page, follow the these steps:

1. Log in and choose your repository on GitHub and ensure it is publicly available
2. Log into your Zenodo account
3. Now, next to your email at the top right of the Zenodo page, there is a little drop down menu, select GitHub and select authorize application to give Zenodo the permissions it needs. Once this occurs, you should see a list of repositories, toggle the button next to your chosen repository into the ON position (see figure 4)
4. Back on GitHub, under settings click "Webhooks" in the left-hand menu. There should be a webook configured to Zenodo
5. Create a new [release](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) on your GitHub repository. Click publish
6. Back on Zenodo under the Upload tab, there should now be a new draft upload where you can reserve a DOI for your repository, edit the information and publish

Each new release should create a new version of the Zenodo Upload, published automatically.

For a descriptive step by step guide on this process, please visit the available [GitHub Guide on this topic here.](https://guides.github.com/activities/citable-code/) [This resource](https://genr.eu/wp/cite/#Release) is also helpful to understand how to create a new release that is synced between GitHub and Zenodo.

![Figure 4: The Zenodo interface when your GitHub account is linked. The bottom of the image shows a repository and corresponding toggle switch](../../.gitbook/assets/Figure6\_GitHubLink)

## IV. How to share Zenodo entries

One of the key benefits of Zenodo is that when you create an upload it provides a DOI for the entry. One can then find the Zenodo webpage by typing the following into a browser.

* https://doi.org/ \[add DOI of the upload]

For example, see the Zenodo upload of this technical guideline here: [https://doi.org/10.5281/zenodo.5713976](https://doi.org/10.5281/zenodo.5713976)

Diving deeper, Zenodo actually issues two DOI’s. One DOI refers to the specific version, while there is an additional DOI created which cites all versions and resolves to the latest one. For instance, if a data management report is updated between one of the milestone drafts and the final version for an assessment, include the DOI that cites all versions in the assessment, thus ensuring anyone who clicks on the URL will be automatically sent to the most recent version.

Generally, when sharing your Zenodo uploads please use the DOI that cites a specific version unless you only want to refer the newest version.

One can find this additional DOI in the versions section of the published webpage of the upload. For example, when referring to the IPBES data management policy (figure 5) we use this doi: [10.5281/zenodo.3551078](https://doi.org/10.5281/zenodo.3551078)

![Figure 5: Screen shot capturing the area of the Zenodo upload which specifies the DOI to use to cite all versions of the IPBES data management policy](../../.gitbook/assets/figure5\_cite\_all\_versions)

## V. How to download from Zenodo

### A. Manually

To download files from Zenodo, all one needs to do is to navigate to the entry they would like to download, scroll down to the _Files_ section on the webpage, and press the button _download_ next to each of the files they would like to download (highlighted in Figure 6). This functionality can be very useful to quickly check files or to save locally and quickly. Resources uploaded to the IPBES community can be found on https://zenodo.org/communities/ipbes.

![Figure 6: Example of available files and the download option from the IPBES Data Management Tutorials Zenodo record (https://doi.org/10.5281/zenodo.4020373)](../../.gitbook/assets/Figure2)

### B. Programmatically using R

For other applications, such as downloading a dataset to be used in a script, one may want to have the script download the files, so that the most recent version is always used and the source is explicit.

Within Python, there's a package available on GitHub [here](https://github.com/dvolgyes/zenodo\_get) which allows one to download from Zenodo using the function `zenodo_get`.

Within R, there's a handy function called [`download_zenodo`](https://rdrr.io/github/inbo/inborutils/man/download\_zenodo.html) from the package [`inborutils`](https://inbo.github.io/inborutils/) that allows one to download from Zenodo easily.

To illustrate this in R, all of the files associated with the Zenodo repository [IPBES regions and subregions](https://doi.org/10.5281/zenodo.3923633) can be downloaded programmatically at once with the following code:

```
# Install the package inborutis and load into library
library(inborutils)

doi <- "10.5281/zenodo.3923633"
local_path <- "data"
inborutils::download_zenodo(doi, local_path, quiet = TRUE)
list.files(local_path)
```

The shapefile for the ipbes regions and subregions is within the zipped folder called "ipbes\_regions\_subregions\_shape\_1.1.zip". Once these files are downloaded, one can unzip the shapefile, call it into memory, and begin to use it as shown here:

```
# Install these packages and then load them into library
library(magrittr)             # Package for the pipe function 
library(sf)                   # Package to read the vector data

path <- "data/ipbes_regions_subregions_shape_1.1.zip"
unzip(path,                   # pathname of the zip file 
      exdir = local_path)     # pathname to extract files to

file <- list.files(path = local_path, pattern = "\\.shp$", full.names = T)
data <- sf::st_read(file, quiet = T)

# Plot some data
Mexico <- data %>% filter(ISO_3 == "MEX")
plot(Mexico[,1], main = "Mexico")
```

For any questions please feel free to contact us at [tsu.data@ipbes.net](mailto:tsu.data@ipbes.net). If you have any Zenodo specific questions they may be answered on their [frequently asked question page](https://help.zenodo.org/).
