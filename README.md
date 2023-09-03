# Impact of Climate Change on Birds

Data from the UK Met Office and Global Biodiversity Information Facility (GBIF).
Predict where bird species of interest is likely to occur in the future - information that is invaluable to conservation organization working on the ground to preserve these species and save them from extinction!
In this project we model the Scottish crossbill (Loxia scotica), which is a small bird that inhabits the Scottish forests and feeds on pine seeds. Only ~ 20,000 individuals of this species are alive today.

1. Use `tidyverse`, `raster`, `sf`, `rgbif` (rOpenSci) packages, read data from `climate_raster.rds`
2. Monthly average minimum temperature heatmap
3. `occ_search`: species occurrence records based on taxonomic information, geographic location, date
4. Nest data by decades
5. Project spatial data to represent earth's 3D sphere in 2D: use Coordinate Reference System (CRS) strings. GBIF hosts data from around the world and uses a global projection (WGS84). The Met Office is a UK organization and provides data in the British National Grid projection (BNG)
6. Generate pseudo-absences to mitigate information asymmetry presences (easier to get) and absences. Assume our species does not occur in random locations outside of its presence
7. `glmnet`: fits generalized logistic regression with elastic net regularization. `caret` uses tuning grid to find an optimal set of hyperparametres by using cross-validation to evalutate different combinations
8. Predict and visualize (colored map) probability of occurrence for crossbill across UK based on climate: `min` and `max` temperature, rainfall, wind speed, snow lying, air frost, `x`, `y`
