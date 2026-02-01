# Mapping Barcelona Neighborhoods Using Python
## Overview

This project demonstrates geospatial visualization and spatial context building using Python. The analysis focuses on neighborhood-level administrative boundaries (“barris”) in Barcelona, Spain, with an emphasis on layering geographic data over a base map to improve spatial interpretation.

The project was originally developed in Google Colab and later exported for version control and portfolio presentation.

---

## Study Area

The study area is Barcelona, Spain, with neighborhood boundary data representing official administrative divisions used by the city.
The visualization highlights how individual neighborhoods are spatially distributed across the urban landscape and relative to surrounding geographic features.

## Data

The neighborhood boundary data was provided as part of a university course. While the original public source was not explicitly specified, the data appears to be derived from publicly available municipal GIS datasets provided by the City of Barcelona.

The dataset is used strictly for educational and portfolio purposes.

## Methods

This project uses layered geospatial visualization, where multiple map components are combined to provide spatial context:
- Vector polygon data (GeoJSON) representing neighborhood boundaries
- A base map providing geographic reference features such as roads, terrain, and coastlines
- Coordinate reference system alignment to ensure accurate overlay
- Neighborhood boundaries are overlaid on top of the base map to allow for interpretation of regions within the city.

## Tools & Libraries
- Python
- GeoPandas – spatial data handling and analysis
- Contextily – base map tiles
- Matplotlib – visualization
- Shapely – geometric operations
- Results

The resulting map provides a clear visual representation of Barcelona’s neighborhood boundaries within their geographic context. Overlaying administrative polygons on a base map allows spatial patterns and regional relationships to be interpreted more effectively than boundary plots alone.

## Notes

This project focuses on spatial visualization and context, not statistical modeling. It demonstrates the ability to work with geospatial data formats, coordinate systems, and layered cartographic design in Python.

---

## Author
Olivia Rueschhoff
M.S. Mathematics (in progress)
B.S. Mathematics, emphasis in Data Science & Statistics
