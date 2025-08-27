# OklahomaLakesPhytoAnalysis
This project includes all the raw data and R scripts used for the analyses and data visualization for the manuscript Stovall et al. "Spatial distribution of rare and common phytoplankton taxa is controlled by geospatial and physiochemical variables". Briefly, it uses phytoplankton biovolume data in addition to landscape, watershed, and physiochemical data among multiple lakes to explare various relationships between each of these factors and other metrics of biodiversity. It also contains the R script used to create the site map for the manuscript. This can be used for community data analysis across spatial scales.

##Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [License](#license)
- [Authors and Acknowledgments](#authors-and-acknowledgments)
- [Contact Information](#contact-information)

## Installation
To run this project, all that is necessary to be installed is the most recent version of R and R studio and also the capability to download and read CSV files.

```bash
# Clone the repository
git clone https://github.com/jkstovall/OklahomaLakesPhytoAnalysis.git

# Navigate to the project directory
cd OklahomaLakesPhytoAnalysis

# Install dependencies
npm install
```
##Usage
```
# Run the project
npm start
```

##Features
109rvalues.csv --> This CSV file contains the r2 and r values of regional vectors representing the strength of correlation between the regional variables and patterns in the community composition NMDS ordination of 109 lakes.
Measured variables include: 
Order: ranking r values from largest to smallest (for plotting purposes)
Variable: regional variables where UL: urban land; PR: precipitation; FR: forest; LN: longitude; LT: latitude; WL: watershed area:land area; AG: agriculture; GS: grassland/shrub
r2: r squared value
r: r value
See manuscript text for methods used to measure each variable.

72rvalues.csv --> This CSV file contains the r2 and r values of local and regional vectors representing the strength of correlation between the regional and local variables and patterns in the community composition NMDS ordination of 72 lakes.
Measured variables include: 
Order: ranking r values from largest to smallest (for plotting purposes)
Variable: local and regional variables where TB: turbidity; CL: chlorophyll a; PS: total phosphorus; pH:pH; CN: electrical conductivity; TM: temperature; UL: urban land; DO: dissolved oxygen; PR: precipitation; FR: forest; NOx: nitrate + nitrite; LN: longitude; LT: latitude; WL: watershed area:land area; AG: agriculture; GS: grassland/shrub
r2: r squared value
r: r value
See manuscript text for methods used to measure each variable.

Create_OK-map.rmd --> This R Markdown file includes the script used to create the site map (Figure 1)

Diversity_Correlation_Analysis.csv --> This CSV file contains raw land use/regional, physiochemical/local, phytoplankton community, and biovolume data as well as the total biovolume, genus richness, and calculated Shannon Diversity Index by sample. This raw data is to be used to derive the standardized means for further analysis. See manuscript text for more information.
Measured variables include: 
Month: month sample was collected
Lake: sample lake name
%_Developed: % of urban land in watershed
%_Forest: % of forested land in watershed 
%_Grassland_Shrub: % grassland/shrub in watershed
%_Agriculture: % agriculture in watershed
Watershed_Area:Lake_Area: watershed area to lake area ratio
Mean_Annual_Precip_cm: mean annual precipitation within watershed (cm)
Latitude: latitude coordinate of the lake
Longitude: longitude coordinate of the lake
Chla_corr_ug.L: chlorophyll a corrected for pheophytin (ug/L)
Phosphorus_mg.L: total phosphorus (mg/L)
Turbidity_NTU: turbidity (NTU)
Conductivity_uS.cm: electrical conductivity (uS/cm)
DO_mg.L: dissolved oxygen (mg/L)
pH: pH
Temperature_degC: water temperature (C)
NOx_mg.L: nitrate + nitrite (mg/L)
All phytoplankton taxa nomenclature columns to be read as Kingdom_Phylum_Class_Order_Family_Genus (mm^3/L)
Total_BV: total biovolume of the sample (mm^3/L)
Richness: genus richness (total number of unique taxa observed in the sample)
Shannon_Diversity: Shannon Diversity Index

Lake_Names.csv ---> This CSV file contains a list of the specific lake names used for the Lakes of Oklahoma database search query

Stovall et al. OWRB Analysis.rmd --> This R Markdown file includes all of the code used to perform the statistical analyses and produce the figures for Stovall et al. "Regional and local drivers of phytoplankton community composition and biodiversity in Oklahoma lakes".

bv_total.csv --> This CSV file contains phytoplankton community and biovolume data by genus for the entire lake dataset (n=109)
All phytoplankton taxa nomenclature columns to be read as Kingdom_Phylum_Class_Order_Family_Genus (mm^3/L)
See manuscript text for methods used to measure, calculate, and consolidate biovolume data.

bv_total_no_na.csv --> This CSV file contains phytoplankton community and biovolume data by genus for the subset (n=72) of lakes
All phytoplankton taxa nomenclature columns to be read as Kingdom_Phylum_Class_Order_Family_Genus (mm^3/L)
See manuscript text for methods used to measure, calculate, and consolidate biovolume data.

chl_turb_bv2.csv --> This CSV file contains chlorophyll a, turbidity, and biovolume data for all samples with complete observations of all 3 variables to be used in the chlorophyll, turbidity, biovolume analysis.
Measured variables include: 
Chla_corr_ug.L: chlorophyll a corrected for pheophytin (ug/L)
Turbidity_NTU: turbidity (NTU)
TOTAL_BV: total sample biovolume (mm^3/L)

class_total109.csv --> This CSV file contains discrete classification data by lake for the entire lake dataset (n=109) 
Measured variables include: 
Ecoregion: lake ecoregion
EcoregionA: abbreviated lake ecoregion (for plotting purposes)
Soil_Infiltration_Rate: soil inflitration rate
E_W: categorizes each lake by location east (E) or west (W)

class_total72.csv --> This CSV file contains discrete classification data as well as precipitation and average total biovolume by lake for the subset (n=72) of lakes with complete observations.
Measured variables include: 
Ecoregion: lake ecoregion
EcoregionA: abbreviated lake ecoregion (for plotting purposes)
Soil_Infiltration_Rate: soil inflitration rate
E_W: categorizes each lake by location east (E) or west (W)
PRECIP: mean annual precipitation within watershed (cm)
AVG_TOTAL_BV: average total biovolume (mm^3/L)

env_total_no_na.csv --> This CSV file contains physiochemical/local water quality and regional (land use, geographic, and precipitation) data for all variables for the subset (n=72) of lakes with complete observations.
Measured variables include: 
Pheophytin_a_ug.L: pheophytin a (ug/L)
Secchi_Depth_cm: secchi depth (cm)
Lake_Area_mi2: lake area (mi^2)
Watershed_Area_km2: watershed area (km^2)
%_Open_Water: % of open water in watershed
%_Developed: % of urban land in watershed
%_Barren_Land: % of barren land in watershed
%_Forest: % of forested land in watershed 
%_Grassland_Shrub: % grassland/shrub in watershed
%_Agriculture: % agriculture in watershed
%_Wetland: % wetlands in watershed
See related files for all other variable abbreviations.

landuse_total109.csv --> This CSV file contains land use/regional data for all variables for the entire (n=109) lake dataset.
Measured variables include: 
OW: % of open water in watershed
UL: % of urban land in watershed
BL: % of barren land in watershed
FOREST: % of forested land in watershed 
GRASS: % grassland/shrub in watershed
AG: % agriculture in watershed
WETL: % wetlands in watershed
LA: lake area (km^2)
WA: watershed area (km^2)
WA:LA: watershed area to lake area ratio
LAT: latitude coordinate of the lake
LONG: longitude coordinate of the lake
SL: shoreline length (km)
SDR: shoreline development ratio
AVGSL: average percent slope
MAXDEPTH: maximum depth of lake (m)
ELEV: normal X elevation (m)
CAP: normal capactiy (ac-ft)
PRECIP: mean annual precipitation within watershed (cm)

new_means_resid.csv --> This CSV file contains raw land use/regional, physiochemical/local, phytoplankton community, and biovolume data as well as the total biovolume, genus richness, and calculated Shannon Diversity Index by sample (n=419; excludes cases missing chlorophyll value). This CSV file also contains the standardized means of the physiochemical/local variables used in the linear mixed-effects model to account for missing data and the calculated residuals from the chlorophyll a vs. biovolume linear regression.
Measured variables include: 
Month: month sample was collected
Lake: sample lake name
X._Developed: % of urban land in watershed
X._Forest: % of forested land in watershed 
X._Grassland_Shrub: % grassland/shrub in watershed
X._Agriculture: % agriculture in watershed
Watershed_Area.Lake_Area: watershed area to lake area ratio
Mean_Annual_Precip_cm: mean annual precipitation within watershed (cm)
Latitude: latitude coordinate of the lake
Longitude: longitude coordinate of the lake
Chla_corr_ug.L*: chlorophyll a corrected for pheophytin (ug/L)
Phosphorus_mg.L*: total phosphorus (mg/L)
Turbidity_NTU*: turbidity (NTU)
Conductivity_uS.cm*: electrical conductivity (uS/cm)
DO_mg.L*: dissolved oxygen (mg/L)
pH*: pH
Temperature_degC*: water temperature (C)
NOx_mg.L*: nitrate + nitrite (mg/L)
All phytoplankton taxa nomenclature columns to be read as Kingdom_Phylum_Class_Order_Family_Genus (mm^3/L)
Total_BV: total biovolume of the sample (mm^3/L)
Richness: genus richness (total number of unique taxa observed in the sample)
Shannon_Diversity: Shannon Diversity Index
Residuals: chlorophyll a vs. biovolume linear regression residuals 
*: '_new' indicates the standardized mean of a given physiochemical variable

percentcomp_group.csv --> This CSV file contains the percentage of the total bivolume on average of each phytoplankton group for all 109 lakes
PHYTOPLANKTON_GROUP: Cyanobacteria, Chlorophyta, Bacillariophyta, Charophyta, Cryptophyta, Haptophyta, Ochrophyta, Euglenozoa, and Miozoa
Measured variables include: 
PERCENT_TOTAL_BV: % of the total biovolume each group comrpises by lake

phytogroup_land109.csv --> This CSV file contains land use/regional data for the entire (n=109) lake dataset as well as average total biovolume of each phytoplankton group by lake.
Measured variables include: 
UL: % of urban land in watershed
FR: % of forested land in watershed 
GS: % grassland/shrub in watershed
AG: % agriculture in watershed
WL: watershed area to lake area ratio
LT: latitude coordinate of the lake
LN: longitude coordinate of the lake
PR: mean annual precipitation within watershed (cm)
Biovolume expressed in mm^3/L. See manuscript text for methods used to measure each variable.

phytogroup_wq72.csv --> This CSV file contains physiochemical/local water quality data for the subset (n=72) of lakes with complete observations as well as average total biovolume of each phytoplankton group by lake.
Measured variables include: 
CL: chlorophyll a corrected for pheophytin (ug/L)
PS: total phosphorus (mg/L)
TB: turbidity (NTU)
CN: electrical conductivity (uS/cm)
DO: dissolved oxygen (mg/L)
pH: pH
TM: water temperature (C)
NOx: nitrate + nitrite (mg/L)
Biovolume expressed in mm^3/L. See manuscript text for methods used to measure each variable.

sublanduse_total109.csv --> This CSV file contains land use/regional data for each variable retained after minimizing covariates for further analysis for the entire (n=109) lake dataset.
Measured variables include: 
UL: % of urban land in watershed
FOREST: % of forested land in watershed 
GRASS: % grassland/shrub in watershed
AG: % agriculture in watershed
WA_LA: watershed area to lake area ratio
LAT: latitude coordinate of the lake
LONG: longitude coordinate of the lake
PRECIP: mean annual precipitation within watershed (cm)
See manuscript text for methods used to measure each variable.

wq_total_no_na.csv --> This CSV file contains physiochemical/local water quality and regional (land use, geographic, and precipitation) data for the subset (n=72) of lakes with complete observations. 
Measured variables include: 
Chla_corr_ug.L: chlorophyll a corrected for pheophytin (ug/L)
Phosphorus_mg.L: total phosphorus (mg/L)
Turbidity_NTU: turbidity (NTU)
Conductivity_uS.cm: electrical conductivity (uS/cm)
DO_mg.L: dissolved oxygen (mg/L)
pH_XX: pH
Temperature_degC: water temperature (C)
NOx_mg.L: nitrate + nitrite (mg/L)
UL_XX: % of urban land in watershed
FOREST: % of forested land in watershed 
GRASS: % grassland/shrub in watershed
AG: % agriculture in watershed
WA_LA: watershed area to lake area ratio
LAT: latitude coordinate of the lake
LONG: longitude coordinate of the lake
PRECIP: mean annual precipitation within watershed (cm)
See manuscript text for methods used to measure each variable.

##License
This project is licensed under the MIT License - see the LICENSE file for details.

##Authors and Acknowledgments
Jasmine Stovall - Initial work - https://github.com/jkstovall
Caleb Robbins - data wrangling and site map - https://github.com/robbinscalebj

##Contact Information
For any inquiries, please contact jasmine.stovall92@gmail.com.
