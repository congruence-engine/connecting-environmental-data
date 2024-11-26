# Bradford Becks and Millponds Datasets, 1848-1909

These datasets consist of GeoJSON files produced as part of the Congruence Engine Project (2021-25) at the Science Museum Group. 

## Introduction
The datasets were produced in collaboration with the local campaign group [Friends of Bradford's Becks](https://bradford-beck.org/) and Robert Hellawell from the [Aire Rivers Trust](https://aireriverstrust.org.uk/). 

The purpose of the datasets was to produce a more accurate picture of how Bradford's watercourses have changed over time, with particular attention being paid to the connections between the textile industry and river pollution in the late 19th and early 20th centuries. The datasets are intended to be of use to historians, environmental activists, and other people interested in the changes to Bradford's natural environment in the nineteenth and twentieth centuries.

The maps were created using QGIS as well as Felt, with historic tile layers loaded from the [National Library of Scotland's collection of Maps](https://maps.nls.uk/). Some are provided directly by the NLS, while others can be accessed via [MapTiler](https://www.maptiler.com/). 

## A word of caution
Maps are never 'objective' or impartial depictions of the lay of the land at a given point in time. They are highly ideological representations of space created from a particular vantage point. The Ordnance Survey (OS) maps used for most of these datasets were the product of a long-term, state-sponsored project of geographical surveying in the nineteenth century. As such, cartography was a tool of governance which helped to standardise administrative boundaries, delimit the bounds of private and public property, as well as raise taxes. 

The representation of natural features like rivers in the OS maps used here varies in both form and level of detail. The extent to which natural features, and artificial features for the exploitation of natural resources like water, appear in these maps is to some degree an illustration of their economic significance. 

The varying cartographical representation of these features has meant that we have often had to make judgements and educated guesses. For instance, in some of the maps streams and becks are sometimes represented by single lines that are difficult to distinguish from property and other boundaries. Comparison between different maps has helped us to reach judgements about these and other ambiguities, but the resulting datasets will no doubt contain flaws of their own. 

These datasets, then, represent a modern *interpretation* of this earlier 19th cartographical project, driven by the desire to better understand the changing shape of Bradford's water infrastructure from the perspective of environmental history and industrial heritage. While they aim to document in as much detail as possible the watercourses, millponds, reservoirs and ponds depicted on publicly-available maps of Bradford between 1852 and 1909, they will no doubt contain ocassional errors or inconsistencies.

## Description
Each folder refers to an individual series of map layers from the National Library of Scotland's collection. Below you can find more information about the corresponding maps:

*   **1852 (Town Plan)**: [Ordnance Survey Town Plans of England and Wales, 1840s-1890s: Bradford, 1:1,056, Surveyed: 1848, Published: 1852](https://maps.nls.uk/os/townplans-england/bradford-1056.html)
*   **1852 (6 inch)**: [Ordnance Survey Maps - Six-inch England and Wales, First Edition, Yorkshire, Surveyed: 1847-50, Published: 1852](https://maps.nls.uk/os/6inch-england-and-wales/)
*   **1873**: [Walker & Virr, Plan of the Borough of Bradford, 1873](https://maps.nls.uk/towns/rec/11845)
*   **1880**: [John Hart, Block plan of the town of Bradford, c. 1880](https://maps.nls.uk/towns/rec/11846)
*   **1891**:  [Ordnance Survey Town Plans of England and Wales, 1840s-1890s: Bradford, 1:500, Surveyed: 1889-91, Published: 1891](https://maps.nls.uk/os/townplans-england/bradford.html)
*   **1908**: [Ordnance Survey Maps - 25 inch England and Wales, 1841-1952, Revised: 1905-6, Published: 1908](https://maps.nls.uk/os/25inch-england-and-wales/)
*   **1909**: [Ordnance Survey Maps - Six-inch England and Wales, Second Edition, Revised: 1905-6, Published: 1909](https://maps.nls.uk/os/6inch-england-and-wales/)

Each folder contains two GEOJSON files:


*   **Watercourses**: This file contains vector line features for watercourses identified on the relevant basemap. These include rivers, becks, drains, canals and other watercourses. Each line has the following attributes:
      1.   ***fid***: identifier. 
      2.   ***name***: the name of the watercourse as identified on the map. Where no name if visible, we have used 'Other'. 
      3. ***length***: the length of the vector line, in metres. 
      4. ***tributary_of_***: where one river or beck is a tributary of another, the latter's name. For mill streams, we have chosen the most likely downstream watercourse. For canals, drains, and ambiguous cases, we have used 'NULL'. 


*   **Millponds**: This file contains polygon features for millponds, reservoirs, ponds, and other bodies of water identified on the relevant basemap. Each polygon has the following attributes: 

    1.   ***id***: identifier. 
    2.   ***map-label***: label assigned to the body of water in the original map, where present. Otherwise NULL. 
    3.   ***type***: classification of each body of water according to likely use. The principal classification is as follows: 
        *   'mill pond': artificial body of water used for industrial purposes.
        *   'reservoir': artificial body of water used 
        *   'pond': body of water used for ornament, or naturally ocurring body of water.
        *   'undetermined': where no clear type is identifiable.

## Usage & Tile Links
The datasets are intended for use with corresponding basemap tiles. The table below provides links to these tyles, which can be loaded in GIS desktop software like QGIS, or via online services like Felt. Most can be used a TileJSON, WMTS, or XYZ layers. The 1873 and 1880 maps have been georeferenced using AllMaps, and are available as XYZ tiles via the links provided. 

| Year | Scale | Tile Link |
|------|-------|-----------|
|1852 (Town Plan) | 1:1,056 | [NLS](https://mapseries-tilesets.s3.amazonaws.com/os/town-england/Bradford/index.html#Bradford/ol3.) |
|1852 (6 inch) | 6-inch (1:10,560) | [NLS](https://www.google.com/url?q=https%3A%2F%2Fmapseries-tilesets.s3.amazonaws.com%2Fos%2Fsix-inch-yorkshire%2Findex.html%23six-inch-yorkshireN-new%2Fol3)|
|1873 | 1:10,560 | [NLS via AllMaps](https://allmaps.xyz/maps/682c0c5a6a17c868/{z}/{x}/{y}.png)|
|1880 | 1:4,281 | [NLS via AllMaps](https://allmaps.xyz/maps/20b4442417495cda/{z}/{x}/{y}.png)|
|1891 | 1:500 | [NLS](https://www.google.com/url?q=https%3A%2F%2Fmapseries-tilesets.s3.amazonaws.com%2Fos%2Ftown-england%2FNorth%2Findex.html%23North_new%2Fol3)|
| 1908 | 25-inch (1:2,500) | [NLS](https://www.google.com/url?q=https%3A%2F%2Fmapseries-tilesets.s3.amazonaws.com%2F25_inch%2Fyorkshire%2Findex.html%23yorkshire_new%2Fol3) |
| 1909 | 6-inch (1:10,560) | [NLS via MapTiler](https://www.google.com/url?q=https%3A%2F%2Fcloud.maptiler.com%2Ftiles%2Fuk-osgb10k1888%2F)|

## Example Maps

You can view these datasets [deployed in Felt](https://felt.com/map/Bradford-Becks-1848-1909-RfbqXAYYSRicW8wMDe6EWA?loc=53.79168,-1.7383,14.05z&share=1. ), arranged by year. 

![Image of a Felt map created using Congruence Engine datasets, showing Bradford Beck as it passes by several millponds and Brownroyd reservoir](https://github.com/congruence-engine/connecting-environmental-data/blob/main/images/felt_map.png?raw=true)

## License
This work is licensed under a [Creative Commons Attribution 4.0 License - CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
