---
description: Technical Guideline Series
---

# Part 4 - Guidelines for Colour

**Prepared by Joy Kumagai - Technical Support Unit (TSU) of Knowledge and Data**\
**Reviewed by Aidin Niamir - Head of the Technical Support Unit of Knowledge and Data**\
****_For any inquires please contact _[tsu.data@ipbes.net](mailto:tsu.data@ipbes.net)

Version: 1.0\
Last Updated: May 13th 2021

DOI: [10.5281/zenodo.4756596](https://doi.org/10.5281/zenodo.4756596)

This technical guidelines focuses on recommendations for the use of colour in maps and can be applied to other visualisations. We present some base considerations for colour paired with links to useful resources for further exploration.

Begin by loading the following packages:

```
library(RColorBrewer)
library(ggplot2)
library(sf)
library(rnaturalearth)
```

## I. Overview of Pallets:

### _A Types of Pallets:_

Colour is a critical key to communicating information to audiences. Often incorrect colour schemes are used that either make it difficult for people to understand the map or bias the interpretation. There are generally three types of palettes, qualitative, sequential, and diverging each corresponding to distinctive qualities of the data they represent.

Qualitative or categorical palettes have distinctive colours that are used to represent nominal or qualitative data with no presumed ordering, such as gender or cereal brands. Sequential palettes often represent continuous data such as temperature or height. These palettes are generally marked by even steps in value or intensity of a hue. Diverging palettes have two sets of sequential palettes meeting on a mutual colour which can represent continuous data with an obvious midpoint, such as data representing change from a baseline, or are often used to represent Likert scale survey responses.

### _B. Colour Blind Friendly Palettes_

When creating a map or figure, please choose colour schemes that are colour blind friendly. A very useful tool to visualise colours as someone with different types of colour blindness is available [here](https://davidmathlogic.com/colorblind/#%23D81B60-%231E88E5-%23FFC107-%23004D40).

[This article](https://personal.sron.nl/\~pault/) by Paul Tol provides extensive colour palettes to choose from that are colour blind friendly and for qualitative, diverging, and sequential data. The high contrast colour scheme is particularly useful as it has been optimized for high contrast that will appear well in a monochromatic printout. Additionally, the package colorBlindness has tools to visualise the colour vision deficiency and useful palettes to choose from as well. A guide to the package is available [here](https://cran.r-project.org/web/packages/colorBlindness/vignettes/colorBlindness.html)

### _C. No rainbow colour palettes_

Rainbow colour schemes are interpreted by humans to have sharp artificial boundaries that are not representative of the underlying data. [Crameri et al. 2020 covers](https://doi.org/10.1038/s41467-020-19160-7) in more detail the current problems involving the use of colour in science communication. An example of this is presented in the figure below taken from [this article](https://personal.sron.nl/\~pault/#) where geoid height is displayed using a sunset scheme and then a traditional rainbow scheme. Large jumps in the data are interpreted within the lines of light blue and yellow that are not inherent within the data.

![](<../../.gitbook/assets/color\_comparison\_figure (3).png>)

Figure 2: Map illustrating the differences of interpretation of data displayed with a sunset palette scheme and the traditional rainbow palette.

## II. RColorBrewer in R and Examples

### _A. RColorBrewer_

In R, one can use the RColorBrewer package which provides convenient qualitative, sequential, and diverging palettes.

To display all of the prepared palettes within the RColorBrewer package run this line of code:

```
RColorBrewer::display.brewer.all()
```

![](<../../.gitbook/assets/unnamed-chunk-3-1 (4).png>)

To display all of the colourblind friendly palettes run this:

```
RColorBrewer::display.brewer.all(colorblindFriendly = TRUE)
```

![](<../../.gitbook/assets/unnamed-chunk-4-1 (6).png>)

If you would like to visualise a specific palette, specify the number of colours and the palette name.

```
RColorBrewer::display.brewer.pal(n = 5, name = 'YlOrRd')
```

![](<../../.gitbook/assets/unnamed-chunk-5-1 (9).png>)

[This article](https://www.datanovia.com/en/blog/the-a-z-of-rcolorbrewer-palette/) provides a great overview on how to use the RColorBrewer package with these palettes integrated with ggplot with examples.

### _B. Hexadecimal_

R uses hexadecimal to represent colours. “Hexadecimal is a base-16 number system used to describe colour. Red, green, and blue are each represented by two characters (#rrggbb) that has 16 possible symbols.” - [R colour cheatsheet](https://www.nceas.ucsb.edu/sites/default/files/2020-04/colorPaletteCheatsheet.pdf)

These values can be used to specify specific colours for a plot. To return the hexadecimal colour code of a palette, use this code: brewer.pal(n, name)

For example:

```
RColorBrewer::brewer.pal(n = 5, name = "YlOrRd")

## [1] "#FFFFB2" "#FECC5C" "#FD8D3C" "#F03B20" "#BD0026"
```

We could then call those specific colours in a plot, as opposed to using general names like “blue” or pre-set palettes.

### _C. Examples_

The next two examples showcase how to use the package RColorBrewer to set palletes within maps. We will use the populated places dataset from R natural earth website available in the first example [here for free download](https://www.naturalearthdata.com/downloads/110m-cultural-vectors/110m-populated-places/). These are just example datasets whose accuracy has not been checked.

First run this code to download country data and the large cities dataset we will be working with. The code also projects both datasets to the Robinson Projection.

```
land <- ne_countries(scale = 110, returnclass = "sf") # Downloads land polygons 
cities <- read_sf("ne_110m_populated_places.shp") # Downloads the large cities points dataset

robin <- "+proj=robin +lon_0=0 +x_0=0 +y_0=0 +datum=WGS84 +units=m +no_defs"# Defines Projection 

# Converts to Robinson
land <- st_transform(land, crs = robin)
cities <- st_transform(cities, crs = robin)
```

**Example 1: Continuous Data**\
We will use population information contained in the large cities dataset, which is a continuous variable. The function scale\_color\_gradient() is used for the continuous data. The hex values were obtained from the brewer.pal function shown in the last section.

```
ggplot(cities) +
  geom_sf(data = land, # adds land for reference
          col = NA,
          fill = "gray60") +
  geom_sf(aes(color = POP_MIN/1000000)) + # Assigns the colour of the large cities to their minimum population size
  scale_color_gradient( # used with continuous data
    low = "#FFFFB2", 
    high = "#BD0026") +
  labs(color = "Population (millions)") +
  theme(legend.position = "bottom", # Places legend on the bottom 
        panel.background = element_blank(), # controls the background panel colour 
        panel.grid.major = element_line(color = "grey80")) # controls the grid line colour 
```

![](<../../.gitbook/assets/unnamed-chunk-8-1 (4).png>)

**Example 2: Categorical Data**\
We now will use the land dataset and function scale\_fill\_brewer() to set the colour of the continents according to one of the qualitative palettes included in the RColorBrewer package.

```
ggplot(land) +
  geom_sf(aes(fill = continent, color = continent)) + # Fill and colour are the same to effective remove borders
  scale_color_brewer(palette = "Dark2") + # Uses a RColorBrewer palette
  scale_fill_brewer(palette = "Dark2") +
   theme(legend.position = "bottom", 
        legend.title = element_blank(),
         panel.background = element_blank(), 
        panel.grid.major = element_line(color = "grey80")) 
```

![](<../../.gitbook/assets/unnamed-chunk-9-1 (4).png>)

## III. Suggestions

* Use colour schemes and projections consistently throughout the chapter, if possible throughout the assessment.
* No data is symbolized with the colour grey (BBBBBB; RGB:187, 187, 187)
* White or light sky blue (87CEFA; RGB: 135, 206, 250) is used for the ocean in maps
* Don’t overload colour - avoid colour when not necessary - use it to highlight important information
* Grey normally represents NA data in a map, but can be very useful in other plots to focus your audience’s attention on key parts of your visualisation that have colour

## IV. Additional Resources

* R Colour Sheet: [https://www.nceas.ucsb.edu/sites/default/files/2020-04/colorPaletteCheatsheet.pdf](https://www.nceas.ucsb.edu/sites/default/files/2020-04/colorPaletteCheatsheet.pdf)
* Useful tool to assist in picking palettes and colours: [https://colorbrewer2.org/](https://colorbrewer2.org)
* Tool to visualise colours as someone with different types of colour blindness: [https://davidmathlogic.com/colorblind/#%23D81B60-%231E88E5-%23FFC107-%23004D40](https://davidmathlogic.com/colorblind/#%23D81B60-%231E88E5-%23FFC107-%23004D40)
* colourBlindness Package guide: [https://cran.r-project.org/web/packages/colorBlindness/vignettes/colorBlindness.html](https://cran.r-project.org/web/packages/colorBlindness/vignettes/colorBlindness.html)

Your feedback on this content is welcome. Let us know what other useful material would you like to see here by emailing [tsu.data@ipbes.net](mailto:tsu.data@ipbes.net)
