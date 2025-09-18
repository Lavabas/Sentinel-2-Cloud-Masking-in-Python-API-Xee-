# Cloud-Free Vegetation Monitoring with Sentinel-2 and Xee in Trincomalee

## Overview
Satellite-based vegetation monitoring often faces challenges due to frequent cloud cover, especially in tropical regions like Sri Lanka. This project demonstrates a cloud masking and vegetation index workflow using Sentinel-2 imagery within the Google Earth Engine Python API, enhanced with the xee engine for seamless integration into xarray. By linking Sentinel-2 surface reflectance with cloud probability data, the workflow effectively masks cloudy pixels, computes the Normalized Difference Vegetation Index (NDVI), and generates weekly composites to capture vegetation dynamics over time. 

A rolling mean filter is then applied to smooth temporal fluctuations, producing cleaner NDVI signals that highlight long-term vegetation patterns. Applied to a selected region in Trincomalee, this workflow showcases how cloud-free vegetation indices can be derived and analyzed at scale for agricultural monitoring, forestry, and environmental change studies.

### Weekly NDVI Composites (Cloud-Masked)
<img width="2291" height="2090" alt="image" src="https://github.com/user-attachments/assets/4d1f46d8-a83e-456e-bb97-4debb1eaa24f" />

Spatiotemporal NDVI maps at weekly intervals, showing vegetation greenness across Trincomalee after removing cloud contamination.

### Smoothed NDVI Time Series (Rolling Mean)
<img width="2291" height="2090" alt="image" src="https://github.com/user-attachments/assets/9f2918c7-d954-4c10-ad2e-febc5f09dd69" />

Weekly NDVI composites averaged using a rolling mean filter, reducing noise from residual cloud artifacts and highlighting consistent vegetation trends.

## Tools and Libraries
1. Google Earth Engine
 – Scalable geospatial processing platform
2. geemap
 – Interactive map drawing and visualization for GEE
3. xarray
 – For multi-dimensional array handling
4. xee
 – Bridge between GEE image collections and xarray datasets

## Datasets
1. Sentinel-2 Surface Reflectance (COPERNICUS/S2_SR_HARMONIZED)
- Bands: B2–B12 (visible, NIR, SWIR)
2. Sentinel-2 Cloud Probability (COPERNICUS/S2_CLOUD_PROBABILITY)
- Cloud likelihood scores (0–100) used for masking

Study Area: Trincomalee District, Sri Lanka (ROI drawn interactively with geemap), Time Period: 2024–2025

## Notes
- ROI is user-drawn in the notebook (Trincomalee is an example).
- Cloud threshold (probability < 20) can be adjusted depending on tolerance.
- Results depend on Sentinel-2 revisit frequency (~5 days) and cloud conditions.
- Scale parameter (scale = 0.0003) should be adapted for resolution needs.

