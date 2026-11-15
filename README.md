# Bengaluru in 15 m

An interactive map for exploring Google's **GEM-15** 15 m elevation model over Bengaluru. It shows low-lying ground, building heights and land cover, and lets you raise water or run rainfall flood scenarios. Everything runs in the browser; no server or API key is needed.

**Open the app:** https://rajasivaranjan.github.io/bengaluru-15m-dem/

## What you can do

- **Base maps:** Esri satellite (with or without labels) or OpenStreetMap. Google base maps work if you add your own key with the Map Tiles API enabled. Enter it in the page; it is stored only in your browser.
- **Flood simulation:**
  - *Rainstorm:* a 2D shallow-water model on the 15 m grid for storms of 25–200 mm in 3 h, peaking after 1 hour. It includes OpenStreetMap drains, Microsoft buildings as obstacles, and spare storage in lakes. It plays back over 6 hours, with water depth shown in five classes.
  - *Quick screen:* floods land below a chosen height above the nearest stream or lake (HAND).
- **Layers:** Microsoft building footprints with GEM-15 heights, high-rise cells (≥ 15 m, National Building Code of India 2016), height above ground, low-lying ground (purple), ESA WorldCover land cover, and bare-earth elevation.
- **Click anywhere** for ground and surface elevation, height above ground and height above the nearest drain. Click a building to see its footprint area, estimated height and whether it is under water.

## Limitations

These are screening-level models, not flood forecasts:

- The rainstorm model has not been calibrated against observed floods.
- Drain sizes are assumed from OpenStreetMap types, not surveyed, and culvert capacity is not limited.
- Lakes get 1 m of spare storage, and rain is uniform across the city.
- Building heights are sampled from a 15 m surface model. They are approximate, and tall trees beside small buildings can inflate them.

## Data and credits

| Data | Source | Licence |
|---|---|---|
| Elevation (DSM + DTM, 15 m) | [GEM-15 v1](https://developers.google.com/earth-engine/datasets/catalog/projects_climate-and-sustainability_assets_gem-15_v1). This dataset is produced by Google. | CC BY 4.0 |
| Building footprints | [Microsoft Global ML Building Footprints](https://github.com/microsoft/GlobalMLBuildingFootprints) | ODbL 1.0 |
| Land cover | [ESA WorldCover 2021 v200](https://esa-worldcover.org) | CC BY 4.0 |
| Drains and streams | © OpenStreetMap contributors (via Geofabrik) | ODbL 1.0 |
| Base maps | Esri World Imagery, © OpenStreetMap contributors | Provider terms |

The building data in `buildings.bin` is a derived database of the Microsoft footprints. It is made available under the **Open Database License (ODbL 1.0)**.

Built with [Leaflet](https://leafletjs.com). Map data runs entirely in the browser.
