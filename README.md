# The Green Effect: Investigating Green Gentrification

## 📖 Overview
This project investigates the **"Green Paradox"** in East London, a phenomenon where urban greening projects (parks, wetlands, "blandscaping") inadvertently drives up property values and displace the low-income residents they were intended to serve. 

Using geospatial data science, the project identifies statistically significant clusters where high structural deprivation intersects with high density of new green infrastructure, marking "ground zero" for ecological gentrification.

## 🚀 Key Technical Features

*   **Robust 2-Step API Pipeline:** Engineered a real-time data ingestion system combining **Nominatim** (geocoding) and **OSM Overpass API**.
    *   Implemented multiple endpoint fallback logic to ensure high availability.
    *   Automated the resolution of borough administrative boundaries to fetch precise local park data.
*   **Advanced Spatial Autocorrelation:** Conducted bivariate analysis (**Global Moran’s I** and **LISA**) using `libpysal` and `esda`.
    *   Utilized a **K-Nearest Neighbors (KNN)** spatial weight matrix to eliminate geometric "islands."
    *   Mapped 3-sigma statistical clusters to identify High-Deprivation/High-Greenery regimes at the LSOA level.
*   **Interactive Folium Visualization:** Developed a multi-layered interactive map using `Folium`.
    *   Integrated **MarkerCluster** logic for high-density point data.
    *   Layered IMD (Index of Multiple Deprivation) choropleths against park density.

## 📊 Critical Insight
The analysis revealed a stark spatial correlation: **77.2% of mapped parks** fall within the **40% most deprived LSOAs** across the 5 East London boroughs studied. This data-driven insight quantifies the immense displacement pressure currently facing these vulnerable communities.

## 🛠 Tech Stack
*   **Language:** Python
*   **Spatial Analysis:** GeoPandas, libpysal, esda, Shapely
*   **APIs:** Overpass (OpenStreetMap), Nominatim
*   **Visualization:** Folium (Leaflet.js), Matplotlib, Seaborn
*   **Data Sources:** UK Land Registry, ONS Index of Multiple Deprivation (IMD)

## 📂 Project Structure
*   `Green_Effect_Analysis.ipynb`: The full analytical workflow, from API calls to LISA cluster mapping.
*   `london_boundaries/`: Shapefiles for London Boroughs and LSOAs.
*   `outputs/`: Saved interactive HTML maps and statistical plots.

