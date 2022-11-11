---
description: Technical Guideline Series
---

# Part 3 - Cartographic Guidelines

**Prepared by Joy Kumagai - Technical Support Unit (TSU) of Knowledge and Data**\
**Reviewed by Aidin Niamir - Head of the Technical Support Unit of Knowledge and Data**\
_For any inquires please contact_ [_tsu.data@ipbes.net_](mailto:tsu.data@ipbes.net)

Version: 3.0\
Last Updated: 15 August 2022

DOI: [10.5281/zenodo.6992222](https://doi.org/10.5281/zenodo.6992222)

This technical guideline will review the necessary and suggested cartographic elements for maps produced as part of IPBES assessments. The guide is split into four sections, cartographic elements, disclaimers, country borders, and general suggestions and have examples of maps and the code behind them throughout. This guideline is intended for anyone involved in the process of creating maps within IPBES assessments.

Begin by loading the following packages.

```
library(sf) 
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

* Map with frame and legend
* Graticules (North arrow and scale are not needed when graticules are included)
* References for each of the layers used to make the map are required within each data deposit package associated with the map

Generally these elements do not need to be included with each map for assessments:

* North arrow and scale bar - do not need to be included when graticules are present
* Titles - should not be included within the map’s frame, but rather included in the caption.

Here is an example of creating a world map with these elements. The following code downloads land and ocean polygons from rnaturalearth package, creates latitude and longitude labels and graticules, and then plots a global map in robinson projection.

```
robin <- "+proj=robin +lon_0=0 +x_0=0 +y_0=0 +datum=WGS84 +units=m +no_defs"

# Land polygons from rnaturalearth pckage
world <- rnaturalearth::ne_download(scale = 10, type = 'land', category = 'physical', returnclass = "sf") # sf mulitpologyon 

## OGR data source with driver: ESRI Shapefile 
## Source: "C:\Users\jkumagai\AppData\Local\Temp\Rtmp8GjHuK", layer: "ne_10m_land"
## with 11 features
## It has 3 fields

world_robin <- sf::st_transform(world, crs = robin) # changes the projection

# ocean from rnaturalearth package
ocean <- rnaturalearth::ne_download(scale = 10, type = 'ocean', category = 'physical', returnclass = "sf")

## OGR data source with driver: ESRI Shapefile 
## Source: "C:\Users\jkumagai\AppData\Local\Temp\Rtmp8GjHuK", layer: "ne_10m_ocean"
## with 1 features
## It has 3 fields

ocean <- sf::st_transform(ocean, crs = robin) # changes the projection
ocean <- ocean[,1]
```

The messages describe the data and where it is downloaded locally.

```
# Creates latitude and longitude labels and graticules
lat <- c(-90, -60, -30, 0, 30, 60, 90)
long <- c(-180, -120, -60, 0, 60, 120, 180)
labs <- graticule::graticule_labels(lons = long, lats = lat, xline = -180, yline = 90, proj = robin) # labels for the graticules 
lines <- graticule::graticule(lons = long, lats = lat, proj = robin) # graticules 
```

The warnings of discarding the datum can be safetly ignored in this case\*.

Now we set up the plotting frame, and plot the graticules, ocean, land, and latitude and longitude lines.

```
# Global Map 
par(mar = c(0,3,0,2)) # Adjusts the edges of the frame 
plot(lines, lty = 5, col = "lightgrey") # plots graticules 
plot(ocean, col = alpha("lightskyblue", 0.3), add = TRUE) # plots ocean polygons
plot(world_robin[,1], col = "white", add = TRUE) # plots Land boundaries
text(subset(labs, labs$islon), lab = parse(text = labs$lab[labs$islon]), pos = 3, cex = 0.7, xpd = NA) # plots longitude labels
text(subset(labs, !labs$islon), lab = parse(text = labs$lab[!labs$islon]), pos = 2, cex = 0.7, xpd = NA) # plots latitude labels
box(which = "plot", lty = "solid") # Map frame 
```

![](<../../.gitbook/assets/unnamed chunk 4 1 (1) (1)>)

We can also use the ggplot package, with some additional functionality added with ggspatial, to map sf objects in R Studio such as in the following example:

```
ggplot() + 
  geom_sf(data = world, color = "black", fill = "lightgrey") + # plots the land polygons
  coord_sf(xlim = c(-117.5, -86.5), ylim = c(14.5, 33.0)) + # sets the maps extent
  theme(panel.grid.major = element_line(color = gray(.5), # sets latitude and longitude lines 
                                        linetype = "dashed", size = 0.5),
        panel.background = element_rect(fill = "#b3e5fc"), # sets background panel color 
        panel.border = element_rect(colour = "black", fill=NA, size=0.5)) + # sets panel border 
   ggspatial::annotation_north_arrow(location = "bl", which_north = "true", # sets north arrow 
                          style = north_arrow_minimal,
        pad_x = unit(-0.1, "in"), pad_y = unit(0.45, "in")) +
  ggspatial::annotation_scale(location = "bl") # sets scale bar
```

![](<../../.gitbook/assets/unnamed chunk 5 1 (2) (2)>)

### _B. Projections_

IPBES has adopted the Robinson projection for all global scale maps.

The Robinson projection balances distortions in area, direction, distance, and distortions near the poles. We encourage the use of Pacific centered maps when focused on marine or Pacific themes. The `pacificCentric` function within the `envirem` package can reneter a raster on the Pacific.

For maps of countries or regions, national or appropriate regional projections are recommended. If there is no specific country projection available, the relevant Universal Transverse Mercator zone projection is suggested.

### _C. Color Considerations_

Color is a critical key to communicating information to viewers within a map. Colors need to be used consistently in maps and figures. Often incorrect or inconsistent color schemes are used that either make it difficult for people to understand the map or bias the interpretation. For more information, please refer to the next technical guideline, [Guidelines for Colour.](https://ict.ipbes.net/ipbes-ict-guide/data-management/technical-guidelines/guidelines-for-colour)

## II. Disclaimers:

The standard disclaimers that should appear on all maps within IPBES assessments are the following:

Short form

_The boundaries and names shown, and the designations used on the maps shown here do not imply official endorsement or acceptance by IPBES._

Long form

_The designations employed and the presentation of material on the maps used in the assessment do not imply the expression of any opinion whatsoever on the part of IPBES concerning the legal status of any country, territory, city or area or of its authorities, or concerning the delimitation of its frontiers or boundaries. These maps have been prepared or used for the sole purpose of facilitating the assessment of the broad biogeographical areas represented therein and for purposes of representing scientific data spatially._

For more information on how to display disputed or contentious boundary lines and territories, please contact the TSU on knowledge and data ([tsu.data@ipbes.net](mailto:tsu.data@ipbes.net))

## III. Country Borders

If a map displays data at the country-level, special consideration needs to be taken when drawing country borders. IPBES follows current UN guidance on country borders for original global-scale maps. To assist with following the UN guidance, the technical support unit on knowledge and data and the secretariat have created a package of resources, including shapefiles, to use when displaying country borders.

To access the full guidance and associated files, please go to this website: [https://doi.org/10.5281/zenodo.5883632](https://doi.org/10.5281/zenodo.5883632) and request access. Once you have access, download all files and read the full instructions.

Before you begin, please double check that the data is displayed at the country level and not the territory level. If your data is at the territory level ensure this is reflected in the caption and text and it is not required to follow these guidelines.

In summary, there are five layers that need to be added to the map in this order: grey areas, solid borders, dashed borders, dotted borders, and major lakes. The major lakes are used to represent cross-border waterbodies serving as a border between countries.

First, load all shapefiles into the R session and project each into the Robinson projection. The function, `st_wrap_dateline()`, is used to correct borders that cross the dateline.

```
# Loading data 
grey_areas <- read_sf("country_borders/grey_areas.shp")
solid_borders <- read_sf("country_borders/solid_borders.shp")
dashed_borders <- read_sf("country_borders/dashed_borders.shp")
dotted_borders <- read_sf("country_borders/dotted_borders.shp")
major_lakes <- read_sf("country_borders/Major_Lakes.shp")

# Project data
grey_areas <- st_transform(grey_areas, robin)
solid_borders <- st_wrap_dateline(solid_borders) # corrects borders that cross the dateline
solid_borders <- st_transform(solid_borders, robin)
dashed_borders <- st_transform(dashed_borders, robin)
dotted_borders <- st_transform(dotted_borders, robin)
major_lakes <- st_transform(major_lakes, robin)
```

Now, the next section of code can be split into three categories, plotting the base global map used earlier (section IA), plotting the borders in the correct order, and finally adding the graticule lables to the map.

A line width of 0.1 (`lwd = 0.2`) is used throughout. `Lty` controls the type of line, while `border` controls the color of the border for polygon data and can be set to transparent by using `border = NA`. Besides the grey areas, which should be slightly darker, the same grey shade is used for all borders (`col = "grey40"`).

Finally, in your maps check that the colors within the map match UN guidance paying particular attention to Taiwan, Falkland Islands (Malvinas), and Arunachal Pradesh.

```
# Global Map from earlier 
par(mar = c(0,3,0,2)) # Adjusts the edges of the frame 
plot(lines, lty = 5, col = "lightgrey") # plots graticules 
plot(ocean, col = alpha("lightskyblue", 0.3), lwd = 0.2, add = TRUE) # plots ocean polygons
plot(world_robin[,1], col = "white", border = NA, lwd = 0.2, add = TRUE) # plots land boundaries

# Plot borders 
plot(grey_areas, col = "grey30", border = NA, add = TRUE) # plot grey areas 
plot(solid_borders, col = "grey40", lwd = 0.2, add = TRUE) # plot solid borders 
plot(dashed_borders, col = "grey40", lwd = 0.2, lty = "dashed", add = TRUE) # plot dashed borders 
plot(dotted_borders, col = "grey40", lwd = 0.2, lty = "dotted", add = TRUE) # plot dotted borders 
plot(major_lakes, col = "lightblue2", lwd = 0.2, border = "grey40", add = TRUE) # plot major lakes 

# Add lables to graticules 
text(subset(labs, labs$islon), lab = parse(text = labs$lab[labs$islon]), pos = 3, cex = 0.7, xpd = NA) # plots longitude labels
text(subset(labs, !labs$islon), lab = parse(text = labs$lab[!labs$islon]), pos = 2, cex = 0.7, xpd = NA) # plots latitude labels
box(which = "plot", lty = "solid") # Map frame 
```

![](<../../.gitbook/assets/unnamed chunk 7 1>)

## IV. Suggestions:

Streamlining the design of maps allows for better comparison and integration. Therefore, to facilitate the standardization of maps within IPBES, we recommend the following:

* Avoid country borders, if needed country borders are black, continuous, and 0.2 in size and follow the guidance available on Zenodo ([https://doi.org/10.5281/zenodo.5883632](https://doi.org/10.5281/zenodo.5883632))
* Include all continents in global maps, including Antarctica
* Use color schemes and projections consistently throughout the chapter, if possible throughout the assessment.
* Color schemes should be consistent with the ones used for figures.
* No data is symbolized with the color grey (BBBBBB; RGB:187, 187, 187)
* White or light sky blue (87CEFA; RGB: 135, 206, 250) is used for the ocean
* Do not add excessive labels which interfere with interpretation of the map as a whole

Here we also include some popular resources for global and country scale spatial data:

* Administrative borders: [https://gadm.org/data.html](https://gadm.org/data.html)
* Standardizing country names:
  * ISO 3166-1 alpha 3 ([https://www.iso.org/iso-3166-country-codes.html](https://www.iso.org/iso-3166-country-codes.html)) codes should be used
  * The package [`countrycode`](https://rdrr.io/cran/countrycode/) can be used to convert between different country codes or names
* Marine regions: [https://www.marineregions.org/downloads.php](https://www.marineregions.org/downloads.php)
* Coast lines, land, and ocean boundaries: [https://www.naturalearthdata.com/downloads/](https://www.naturalearthdata.com/downloads/)

Your feeback on this content is welcome. Let us know what other useful material would you like to see here by emailing [tsu.data@ipbes.net](mailto:tsu.data@ipbes.net)

\*The warnings of discarding the datum but preserving the `+towgs1984 = values` stem from an update from PROJ4 to PRROJ6 but is not worriesome in this case. The `+datum=` part is depreciated from GDAL >3 and sf, rgdal, and raster packages use GDAL to read files. There is a stackoverflow thread with more information [here](https://stackoverflow.com/questions/63727886/proj4-to-proj6-upgrade-and-discarded-datum-warnings)
