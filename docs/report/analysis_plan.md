# A study of extreme flooding and primary care access in Te Matau-a-Māui, Aotearoa (Hawke's Bay, New Zealand)

### Authors

- Grace Sokolow\*, gracetsokolow@gmail.com, @gsokolow, Middlebury College

\* Corresponding author and creator

### Abstract

A month of heavy rainfall on the North Island in January 2023 saturated the soils and rivers of Te Matau-a-Māui Hawke's Bay. [1](https://disasterphilanthropy.org/disasters/2023-new-zealand-floods/) 
When Cyclone Gabrielle hit in February, the region experienced "widespread damage and flooding. [...] Over 70,000 residents were left without lifelines including health services, power, road connectivity (in every direction), waste water, drinking water, internet, and cellphone networks. [2](https://www.napier.govt.nz/our-council/cyclone-gabrielle/#:~:text=February%2014%202023%20is%20a,of%20extreme%20isolation%20and%20vulnerability.)
Cyclone Gabrielle was not simply a destructive anomaly. Climate change is increasing storm frequency and intensity worldwide. [3](https://www.oecd.org/climate-action/ipac/the-climate-action-monitor-2023-60e338a2/chapter-d1e1621) 
In order to prepare ourselves for the climate-altered future that is coming, and indeed, perhaps already here, it is essential that we understand the potential impacts of severe precipitation events and to whom they pose the greatest risks. In this study, I will investigate the health care access impacts of Cyclone Gabrielle by calculating the travel time from small scale statistical geometries in Te Matau-a-Maui, Hawkes Bay, to the nearest primary care provider, before and after cyclone-induced road closures. Results will be contextualized using population demographics, to better understand how the burden of disaster damage may be unevenly distributed along socioeconomic lines.


1. “2023 New Zealand Floods and Cyclone Gabrielle.” Center for Disaster Philanthropy. March 21, 2023. https://disasterphilanthropy.org/disasters/2023-new-zealand-floods/
2. “Cyclone Gabrielle” Napier City Council. 2023. https://www.napier.govt.nz/our-council/cyclone-gabrielle/#:~:text=February%2014%202023%20is%20a,of%20extreme%20isolation%20and%20vulnerability.
3. “The Climate Action Monitor 2023”. OECD. November 17, 2023. https://www.oecd.org/climate-action/ipac/the-climate-action-monitor-2023-60e338a2/chapter-d1e1621

### Study Metadata

- `Key words`: extreme weather, health care access, Te Matau-a-Maui, Aotearoa, Hawke's Bay, New Zealand, network-analysis, population demographics
- `Subject`: Social and Behavioral Sciences
- `Date created`: January 2024
- `Date modified`: date of most recent revision
- `Spatial Coverage`: Hastings District in Te Matau-a-Maui Hawke's Bay Aotearoa New Zealand. Wairoa and Taraua Districts are prime candidates for expanded analysis.
- `Spatial Resolution`: Statistical Area 1. Statistical Area 2 and meshblocks may be used in a study expansion.
- `Spatial Reference System`: NZTM2000
- `Temporal Coverage`: 2018-2023. Census data (including geometries) from 2018. Road closure data from 2023. When 2023 Census data becomes available in May 2024, it can be substituted in. 
- `Temporal Resolution`: Netowrk analysis to be repeated 3 months following the initial storm in february 2023. 
- `Funding Name`: N/A
- `Funding Title`: N/A
- `Award info URI`: N/A
- `Award number`: N/A

## Study design

This is an original, observational study. It investigates three research questions:
1. How long (on average) did it take a resident of Hastings District to get to their nearest primary healthcare provider prior to Cyclone Gabrielle?
2. How long (on average) did it take a resident of Hastings District to get to their nearest primary healthcare provider immediately following Cyclone Gabrielle? 3 months later? 6 months later?
3. What population groups were or continue to be most affected by the potential changes in primary healthcare access caused by the storm?

Questions 1 and 2 will be investigated using network analysis. 
Centroids will be created first based on the geometric centers of statistical area 1 geometries, but alternate population weighted centroids may be created for statistical area 2 geometries using meshblock population counts. 
Question 3 will be investigated by weighting the travel time from a given geometry by the proportion of people who are at a particular socioeconomic advantage or disadvantage.

## Materials and procedure

### Computational environment

Define the hardware, operating system, and software requirements for the research.
Include citations to important software projects, plugins or packages and their versions.

Python 3.9

### Data and variables

Describe the **data sources** and **variables** to be used.
Data sources may include plans for observing and recording **primary data** or descriptions of **secondary data**.
For secondary data sources with numerous variables, the analysis plan authors may focus on documenting only the variables intended for use in the study.

Primary data sources for the study are to include ... . HEALTHCARE DATASET?
Secondary data sources for the study are to include ... . CENSUS DATA
ALL SECONDARY?
NEXT; ADD IN THE GEOMETRY, WHICH HAS TO BE DOWNLOADED SEP. WE WILL USE MATCHING 2018 FOR EASE (?)
***IMPORTANT CODING NOTES FROM JOE FEB 13 AM
PININV DOES THE SAME THING THAT CREATING A NEW CONDA ENVIRONMENT DOES. DELETE THE FILES CREATED FOR IT AND STICK W CONDA, DOCUMENTING ALL DEPENDENCIES AND NEWLY IMPORTED BACKAGES IN THE REQUIREMENTS .TXT FILE.
GO TO OSM WEBSITE FOR INSTRUCTIONS ON CREATING A CLEAN CONDA ENVIRONMENT AND DOWNLOADING OSM AS THE FIRST PACKAGE TO AVOID HEADACHES DOWN THE LINE.
MAYBE ADJUST THE DOWNLOADED XLSX FILE AND USE CSV INSTEAD.

WHEN IT COMES TIME FOR NETWORK ANALYSIS, SEE BEN CORDOLA'S FINAL PROJECT AND OR SAM REUBEN'S INDEP STUDY FOR SIMPLIFIED NETWORK ANALYSIS CODE.

Each of the next subsections describes one data source.

***** NOTE: for sa1 files, the column names for NR, PO, PP had to be changed because the accent mark on Maori was not readable by the code. I made those edits and saved the new version of the data under data > derived, but am not sure how to include that in this plan. 
#### 2018-SA1-dataset-individual-part-1-Hawke'sBayRegion_updated_28-7-20.xlsx

**Standard Metadata**

- `Abstract`: demographic data from the 2018 census
- `Spatial Coverage`: Hawke's Bay Region [map](https://d1pepq1a2249p5.cloudfront.net/media/documents/North-Island-PNG.png)
- `Spatial Resolution`: statistical area 1
- `Spatial Reference System`: no geometry
- `Temporal Coverage`: 2018
- `Temporal Resolution`: Snapshot (1 day). 
  `Lineage`: Downloaded from [StatsNZ](https://www.stats.govt.nz/information-releases/statistical-area-1-dataset-for-2018-census-updated-march-2020#:~:text=The%20statistical%20area%201%20dataset%20for%202018%20Census,geographies%20%28including%20meshblocks%29%20is%20available%20by%20emailing%20info%40stats.govt.nz.%20PUBLISHED%20IN%202020) on February 12, 2024 as an xlsx file. Download Data > Regional Files (Microsoft Excel Open XML) > Hawke's Bay Region (Updated november 2021) > 2018-SA1-dataset-individual-part-1-Hawke'sBayregion_updated_28-7-20.xlsx. Downloaded again as a CSV file on February 17 from the same site. Download data > Total New Zealand files > Statistical area 1 dataset for 2018 Census, total New Zealand (updated 16 July 2020) – CSV (zipped file, 32MB).
From the zipped folder, one file was copied into data > raw > public > Individual_part1_totalNZ-wide_format_updated_16-7-20.csv. 
- `Distribution`: Distributed by [StatsNZ](https://www.stats.govt.nz/information-releases/statistical-area-1-dataset-for-2018-census-updated-march-2020#:~:text=The%20statistical%20area%201%20dataset%20for%202018%20Census,geographies%20%28including%20meshblocks%29%20is%20available%20by%20emailing%20info%40stats.govt.nz.%20PUBLISHED%20IN%202020)
- `Constraints`: Licensed for re-use under a Creative Commons 4.0 International License
- `Data Quality`: Usually resident population count, age, and sex data is of very high quality; ethnicity, languages spoken, and ethnicity data is of high quality according to StatsNZ (see footnotes in database)
- `Variables`:
| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| Area_code_and_description | ... | unique identifier for 2018 statistical area 1s | int | ... | \[7013477, 7022500] | ... | ... |
| Census_2018_usually_resident_population_count | ... | population count of people who usually reside in this statistical area | ... | ... | ... | ... | ... |

**PRIMARY**
    `Abstract`: Brief description of the data source
- `Spatial Coverage`: Specify the geographic extent of your study. This may be a place name and link to a feature in a gazetteer like GeoNames or OpenStreetMap, or a well known text (WKT) representation of a bounding box.
- `Spatial Resolution`: Specify the spatial resolution as a scale factor, description of the level of detail of each unit of observation (including administrative level of administrative areas), and/or or distance of a raster GRID size
- `Spatial Reference System`: Specify the geographic or projected coordinate system for the study
- `Temporal Coverage`: Specify the temporal extent of your study---i.e. the range of time represented by the data observations.
- `Temporal Resolution`: Specify the temporal resolution of your study---i.e. the duration of time for which each observation represents or the revisit period for repeated observations
- `Lineage`: Describe and/or cite data sources and/or methodological steps planned to create this data source.
  - sampling scheme, including spatial sampling
  - target sample size and method for determining sample size
  - stopping criteria for data collection and sampling (e.g. sample size, time elapsed)
  - de-identification / anonymization
  - experimental manipulation
- `Distribution`: Describe who will make the data available and how?
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*
- `Data Quality`: State any planned quality assessment
- `Variables`: For each variable, enter the following information. If you have two or more variables per data source, you may want to present this information in table form (shown below)
  - `Label`: variable name as used in the data or code
  - `Alias`: intuitive natural language name
  - `Definition`: Short description or definition of the variable. Include measurement units in description.
  - `Type`: data type, e.g. character string, integer, real
  - `Accuracy`: e.g. uncertainty of measurements
  - `Domain`: Expected range of Maximum and Minimum of numerical data, or codes or categories of nominal data, or reference to a standard codebook
  - `Missing Data Value(s)`: Values used to represent missing data and frequency of missing data observations
  - `Missing Data Frequency`: Frequency of missing data observations: not yet known for data to be collected

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| variable1 | ... | ... | ... | ... | ... | ... | ... |
| variable2 | ... | ... | ... | ... | ... | ... | ... |

#### Primary data source2 name

... same form as above...

#### Secondary data source1 name

**Standard Metadata**

- `Abstract`: Brief description of the data source
- `Spatial Coverage`: Specify the geographic extent of your study. This may be a place name and link to a feature in a gazetteer like GeoNames or OpenStreetMap, or a well known text (WKT) representation of a bounding box.
- `Spatial Resolution`: Specify the spatial resolution as a scale factor, description of the level of detail of each unit of observation (including administrative level of administrative areas), and/or or distance of a raster GRID size
- `Spatial Reference System`: Specify the geographic or projected coordinate system for the study
- `Temporal Coverage`: Specify the temporal extent of your study---i.e. the range of time represented by the data observations.
- `Temporal Resolution`: Specify the temporal resolution of your study---i.e. the duration of time for which each observation represents or the revisit period for repeated observations
- `Lineage`: Describe and/or cite data sources and/or methodological steps used to create this data source
- `Distribution`: Describe how the data is distributed, including any persistent identifier (e.g. DOI) or URL for data access
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*
- `Data Quality`: State result of quality assessment or state "Quality unknown"
- `Variables`: For each variable, enter the following information. If you have two or more variables per data source, you may want to present this information in table form (shown below)
  - `Label`: variable name as used in the data or code
  - `Alias`: intuitive natural language name
  - `Definition`: Short description or definition of the variable. Include measurement units in description.
  - `Type`: data type, e.g. character string, integer, real
  - `Accuracy`: e.g. uncertainty of measurements
  - `Domain`: Range (Maximum and Minimum) of numerical data, or codes or categories of nominal data, or reference to a standard codebook
  - `Missing Data Value(s)`: Values used to represent missing data and frequency of missing data observations
  - `Missing Data Frequency`: Frequency of missing data observations

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| variable1 | ... | ... | ... | ... | ... | ... | ... |
| variable2 | ... | ... | ... | ... | ... | ... | ... |

#### Secondary data source2 name

... same form as above...

### Prior observations  

Prior experience with the study area, prior data collection, or prior observation of the data can compromise the validity of a study, e.g. through p-hacking.
Therefore, disclose any prior experience or observations at the time of study pre-registration here, with example text below:

At the time of this study pre-registration, the authors had _____ prior knowledge of the geography of the study region with regards to the ____ phenomena to be studied.
This study is related to ____ prior studies by the authors

For each primary data source, declare the extent to which authors had already engaged with the data:

- [ ] no data collection has started
- [ ] pilot test data has been collected
- [ ] data collection is in progress and data has not been observed
- [ ] data collection is in progress and __% of data has been observed
- [ ] data collection is complete and data has been observed. Explain how authors have already manipulated / explored the data.

For each secondary source, declare the extent to which authors had already engaged with the data:

- [ ] data is not available yet
- [ ] data is available, but only metadata has been observed
- [ ] metadata and descriptive statistics have been observed
- [ ] metadata and a pilot test subset or sample of the full dataset have been observed
- [ ] the full dataset has been observed. Explain how authors have already manipulated / explored the data.

If pilot test data has been collected or acquired, describe how the researchers observed and analyzed the pilot test, and the extent to which the pilot test influenced the research design.

### Bias and threats to validity

Given the research design and primary data to be collected and/or secondary data to be used, discuss common threats to validity and the approach to mitigating those threats, with an emphasis on geographic threats to validity.

These include:
  - uneven primary data collection due to geographic inaccessibility or other constraints
  - multiple hypothesis testing
  - edge or boundary effects
  - the modifiable areal unit problem
  - nonstationarity
  - spatial dependence or autocorrelation
  - temporal dependence or autocorrelation
  - spatial scale dependency
  - spatial anisotropies
  - confusion of spatial and a-spatial causation
  - ecological fallacy
  - uncertainty e.g. from spatial disaggregation, anonymization, differential privacy

### Data transformations

Describe all data transformations planned to prepare data sources for analysis.
This section should explain with the fullest detail possible how to transform data from the **raw** state at the time of acquisition or observation, to the pre-processed **derived** state ready for the main analysis.
Including steps to check and mitigate sources of **bias** and **threats to validity**.
The method may anticipate **contingencies**, e.g. tests for normality and alternative decisions to make based on the results of the test.
More specifically, all the **geographic** and **variable** transformations required to prepare input data as described in the data and variables section above to match the study's spatio-temporal characteristics as described in the study metadata and study design sections.
Visual workflow diagrams may help communicate the methodology in this section.

Examples of **geographic** transformations include coordinate system transformations, aggregation, disaggregation, spatial interpolation, distance calculations, zonal statistics, etc.

Examples of **variable** transformations include standardization, normalization, constructed variables, imputation, classification, etc.

Be sure to include any steps planned to **exclude** observations with *missing* or *outlier* data, to **group** observations by *attribute* or *geographic* criteria, or to **impute** missing data or apply spatial or temporal **interpolation**.

### Analysis

Describe the methods of analysis that will directly test the hypotheses or provide results to answer the research questions.
This section should explicitly define any spatial / statistical *models* and their *parameters*, including *grouping* criteria, *weighting* criteria, and *significance thresholds*.
Also explain any follow-up analyses or validations.

## Results

Describe how results are to be presented.

## Discussion

Describe how the results are to be interpreted *vis a vis* each hypothesis or research question.

## Integrity Statement

Include an integrity statement - The authors of this preregistration state that they completed this preregistration to the best of their knowledge and that no other preregistration exists pertaining to the same hypotheses and research.
If a prior registration *does* exist, explain the rationale for revising the registration here.

## Acknowledgements

- `Funding Name`: name of funding for the project
- `Funding Title`: title of project grant
- `Award info URI`: web address for award information
- `Award number`: award number

This report is based upon the template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences, DOI:[10.17605/OSF.IO/W29MQ](https://doi.org/10.17605/OSF.IO/W29MQ)

## References
