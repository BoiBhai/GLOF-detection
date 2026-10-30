# Resources
1. https://ibm.github.io/terramind/
2. https://planetarycomputer.microsoft.com/


# GLOF

## Background

A type of outburst flood caused by the failure of a dam containing a glacial lake.

Failure can happen due to erosion, a buildup of water pressure, an avalanche of rock or heavy snow, an earthquake or cryoseism, volcanic eruptions under the ice, or massive displacement of water in a glacial lake when a large portion of an adjacent glacier collapses into it.

A 2023 study found 15 million people at risk from this hazard, mostly in China, India, Nepal, Pakistan, and Peru.

Target Listing: Glacial Lake Outburst Flood (GLOF) Project (CVPR Unit).   Core Objective: Monitor glacial lake boundary changes over time using remote sensing data and predict outburst susceptibility.What to Build:Data Pipeline: Use Python libraries (rasterio, geopandas, google-earth-engine-api) to download multi-spectral satellite imagery (e.g., Sentinel-2 or Landsat) of a Himalayan glacial region over a multi-year span.Feature Extraction & Processing: Implement Normalized Difference Water Index (NDWI) and Normalized Difference Snow Index (NDSI) calculations to automatically segment lake area expansions.Predictive Modeling: Train a spatial-temporal model (such as a ConvLSTM or Gradient Boosting framework like XGBoost combined with spatial features) using topographical variables, meteorological time-series, and historical lake area growth rates to classify high-risk flood zones.