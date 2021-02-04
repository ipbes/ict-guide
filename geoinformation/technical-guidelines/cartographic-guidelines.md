---
description: Technical Guideline Series
---

# Part 3 - Cartographic Guidelines

**Prepared by Joy Kumagai - Technical Support Unit \(TSU\) of Knowledge and Data**  
**Reviewed by Aidin Niamir - Head of the Technical Support Unit of Knowledge and Data**  
_For any inquires please contact_ [_tsu.data@ipbes.net_](mailto:tsu.data@ipbes.net)

Version: 1.0  
Last Updated: February 4th 2021

This technical guideline will review the necessary and suggested cartographic elements for maps produced as part of IPBES assessments. The guide is split into three components, cartographic elements, disclaimers, and general suggestions and have examples of maps and the code behind them throughout.

Begin by loading the following packages.

```text
library(sf) 
library(sp)
library(dplyr)
library(magrittr)
library(rnaturalearth)
library(graticule)
library(ggplot2)
library(ggspatial)
```

## I. Cartographic Elements and considerations for IPBES assessments:

### _A. Cartographic Elements_

Generally the following cartographic elements should be included within each map:

* Map with frame
* Legend as a separate file
* Graticules \(North arrow and scale are not needed when graticules are included\)
* References for each of the layers used to make the map are required within each data deposit package associated with the map

Generally these elements do not need to be included with each map for assessments:

* North arrow and scale bar - do not need to be included when graticules are present
* Titles - should not be included within the map’s frame, but rather included in the caption.

Here is an example of creating a world map with these elements. The following code downloads land and ocean polygons from rnaturalearth package, creates latitude and longitude labels and graticules, and then plots a global map in robinson projection.

```text
robin <- sp::CRS("+proj=robin +lon_0=0 +x_0=0 +y_0=0 +datum=WGS84 +units=m +no_defs")

# Land polygons from rnaturalearth pckage
world <- rnaturalearth::ne_download(scale = 10, type = 'land', category = 'physical', returnclass = "sf") # sf mulitpologyon 

## OGR data source with driver: ESRI Shapefile 
## Source: "C:\Users\jkumagai\AppData\Local\Temp\RtmpQF1MCO", layer: "ne_10m_land"
## with 10 features
## It has 3 fields

world_robin <- sf::st_transform(world, crs = robin) # changes the projection

# ocean from rnaturalearth package
ocean <- rnaturalearth::ne_download(scale = 10, type = 'ocean', category = 'physical', returnclass = "sf")

## OGR data source with driver: ESRI Shapefile 
## Source: "C:\Users\jkumagai\AppData\Local\Temp\RtmpQF1MCO", layer: "ne_10m_ocean"
## with 1 features
## It has 3 fields

ocean <- sf::st_transform(ocean, crs = robin) # changes the projection
ocean <- ocean[,1]
```

The messages describe the data and where it is downloaded locally.

```text
# Creates latitude and longitude labels and graticules
lat <- c(-90, -60, -30, 0, 30, 60, 90)
long <- c(-180, -120, -60, 0, 60, 120, 180)
labs <- graticule::graticule_labels(lons = long, lats = lat, xline = -180, yline = 90, proj = robin) # labels for the graticules 
lines <- graticule::graticule(lons = long, lats = lat, proj = robin) # graticules 
```

The warnings of discarding the datum can be safely ignored in this case \(more info at the bottom of the page\).

Now we set up the plotting frame, and plot the graticules, ocean, land, and latitude and longitude lines.

```text
# Global Map 
par(mar = c(0,3,0,2)) # Adjusts the edges of the frame 
plot(lines, lty = 5, col = "lightgrey") # plots graticules 
plot(ocean, col = alpha("lightskyblue", 0.3), add = TRUE) # plots ocean polygons
plot(world_robin[,1], col = "lightgrey", add = TRUE) # plots Land boundarys
text(subset(labs, labs$islon), lab = parse(text = labs$lab[labs$islon]), pos = 3, xpd = NA) # plots longitude labels
text(subset(labs, !labs$islon), lab = parse(text = labs$lab[!labs$islon]), pos = 2, xpd = NA) # plots latitude labels
box(which = "plot", lty = "solid") # Map frame 
```

![](../../.gitbook/assets/unnamed-chunk-4-1%20%283%29.png)

We can also use the ggplot package, with some additional functionality added with ggspatial, to map sf objects in R Studio such as in the following example:

```text
ggplot() + 
  geom_sf(data = world, color = "black", fill = "lightgrey") + # plots the land polygons
  coord_sf(xlim = c(-117.5, -86.5), ylim = c(14.5, 33.0)) + # sets the maps extent
  theme(panel.grid.major = element_line(color = gray(.5), # sets latitude and longitude lines 
                                        linetype = "dashed", size = 0.5),
        panel.background = element_rect(fill = "lightblue1"), # sets background panel color 
        panel.border = element_rect(colour = "black", fill=NA, size=0.5)) + # sets panel border 
   ggspatial::annotation_north_arrow(location = "bl", which_north = "true", # sets north arrow 
                          style = north_arrow_minimal,
        pad_x = unit(-0.1, "in"), pad_y = unit(0.45, "in")) +
  ggspatial::annotation_scale(location = "bl") # sets scale bar

## Scale on map varies by more than 10%, scale bar may be inaccurate
```

![](../../.gitbook/assets/unnamed-chunk-5-1%20%284%29.png)

The warning of the inaccurate scale bar is due to the map using unprojected data in longitude/latitude. Maps of smaller areas will often have more accurate scale bars. It is recommended to use graticules instead of scale bars when displaying larger areas.

### _B. Projections_

IPBES has adopted the Robinson projection for all global scale maps.

The Robinson projection balances distortions in area, direction, distance, and distorations near the poles. We encourage the use of Pacific centered maps when focused on marine or Pacific themes.

For maps of countries or regions, national or appropriate regional projections are recommended. If there is no specific country projection available, the relevant Universal Transverse Mercator zone projection is suggested.

### _C. Color Considerations_

Color is a critical key to communicating information to viewers within a map. Colors need to be used consistently in maps and figures. Often incorrect or inconsistent color schemes are used that either make it difficult for people to understand the map or bias the interpretation.

When creating a map, please choose color schemes that are color blindness friendly and are not rainbow colored. A very useful tool to visualize colors as someone with different types of color blindness is available [here](https://davidmathlogic.com/colorblind/#%23D81B60-%231E88E5-%23FFC107-%23004D40).

The code below showcases some of the available options for color blind friendly palettes through the RColorBrewer package.

```text
RColorBrewer::display.brewer.all(colorblindFriendly = T)
```

![](../../.gitbook/assets/unnamed-chunk-6-1%20%283%29.png)

Additionally, to display no data we recommend using the color grey \(BBBBBB; RGB:187, 187, 187\).

Rainbow color schemes are interpreted by humans to have sharp artificial boundaries that are not representative of the underlying data. [Crameri et al. 2020](https://doi.org/10.1038/s41467-020-19160-7) covers in more detail the current problems involving the use of color in science communication. An example of this is presented in the figure below \(Figure 2\) taken from [this article](https://personal.sron.nl/~pault/#good_amd_bad_colour_schemes_compared) where geoid height is displayed using a sunset scheme and then a traditional rainbow scheme. Large jumps in the data are interpreted within the lines of light blue and yellow that are not inherent within the data.

![Figure 2: Map illustrating the differences of interpretation of data displayed with a sunset palette scheme and the traditional rainbow palette.](../../.gitbook/assets/color_comparison_figure%20%282%29.png)

[This article](https://personal.sron.nl/~pault/) by Paul Tol provides extensive color palettes to choose from that are color blind friendly and for qualitative, diverging, and sequential data. The high contrast color scheme is particularly useful as it has been optimized for high contrast that will appear well in a monochromatic printout.

## II. Disclaimers:

The standard disclaimers that should appear on all maps within IPBES assessments are the following:

Short form

_The boundaries and names shown, and the designations used on the maps shown here do not imply official endorsement or acceptance by IPBES._

Long form

_The designations employed and the presentation of material on the maps shown here do not imply the expression of any opinion whatsoever on the part of the IPBES concerning the legal status of any country, territory, city or area or of its authorities, or concerning the delimitation of its frontiers or boundaries._

For more information on how to display disputed or contentious boundary lines and territories, please contact the TSU on knowledge and data \([tsu.data@ipbes.net](mailto:tsu.data@ipbes.net)\)

If a map needs to be approved by the United Nations WESR unit, which has the responsibility of review and production of maps, please first contact the TSU on knowledge and data for their procedure.

## III. Suggestions:

Streamlining the design of maps allows for better comparison and integration. Therefore, to facilitate the standardization of maps within IPBES, we recommend the following:

* Avoid country borders, if needed country borders are black, continuous, and 0.2 in size
* Include all continents in global maps, including Antarctica
* Use color schemes and projections consistently throughout the chapter, if possible throughout the assessment.
* Color schemes should be consistent with the ones used for figures.
* No data is symbolized with the color grey \(BBBBBB; RGB:187, 187, 187\)
* White or light sky blue \(87CEFA; RGB: 135, 206, 250\) is used for the ocean
* Do not add excessive labels which interfere with interpretation of the map as a whole

Here we also include some popular resources for global scale spatial data:

* Administrative borders: [https://gadm.org/data.html](https://gadm.org/data.html)
* Marine regions: [https://www.marineregions.org/downloads.php](https://www.marineregions.org/downloads.php)
* Coast lines, land, and ocean boundaries: [https://www.naturalearthdata.com/downloads/](https://www.naturalearthdata.com/downloads/)

Your feedback on this content is welcome. Let us know what other useful material would you like to see here by emailing [tsu.data@ipbes.net](mailto:tsu.data@ipbes.net)

_The warnings of discarding the datum but preserving the `+towgs1984 = values` stem from an update from PROJ4 to PRROJ6 but is not worriesome in this case. The `+datum=` part is depreciated from GDAL &gt;3 and sf, rgdal, and raster packages use GDAL to read files. There is a stackoverflow thread with more information_ [_here_](https://stackoverflow.com/questions/63727886/proj4-to-proj6-upgrade-and-discarded-datum-warnings)\_\_

