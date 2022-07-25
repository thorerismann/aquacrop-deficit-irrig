# Methodology

The goal of this report is to leverage the flexibility and power of the AquaCrop-OSPY framework to eficiently generate a lare number of model runs and perform an initial statistical analysis of the results. More specifically, the Aquacrop-OSPY version number 2.2 was used to test the effect of changing the timing of irrigation dates on different measures of crop productivity and water efficiency for growing Winter Wheat in Tunisia. All of the code to generate the results has been extensively commented and can be found in the notebooks folder of the accompanying github repository. All of the data for the output and the figures used in this report can also be found in accompanying GitHub repository in their respective folders.

## Model and Parameterization
The constant parameters fed into the model with their accompanying values are listed in the following table and follow Exercise 7.7 of the FAO Handbook. 

```{list-table} Model parameters
:header-rows: 1

* - Parameter
  - Value
* - Soil
  - Sandy Loam
* - Crop
  - Winter Wheat 'Wheat GDD'
* - Initial Water Content
  - Wilting Point 'WP'
* - Weather
  - tunis_climate
* - Simulation start date
  - 1979/08/15
* - Simulation end date
  - 2002/05/31
* - Water Quality
  - clean (default
* - Irrigation Method
  - scheduled
* - Planting & First Irrigation Date
  - 12-15-YYYY (December 15th)
```

The effects of changing two parameters were tested in this report, namely the depth of irrigation and the timing of irrigation application. The different irrigation depths tested were 5mm, 10mm, 15mm, 20mm, and 25 mm, spanning the allowed values in the Aquacrop system for localized irrigation at any one time, the default irrigation application method for Aquacrop-OSPY. In each season the crop was planted on December 15th and irrigated immediately. The second and third irrigation dates were randomly chosen from subsequent intervals in the growing season, according to different stages in winter wheat's phenology. The intervals chosen for testing and the corresponding phenological stage are given in the below table:

```{list-table} Intervals tested
:header-rows: 1

* - Count
  - First interval
  - Reason
  - Second interval
  - Reason
* - Baseline Interval
  - [15-01,15-03]
  - Roughly first half of growing season
  - [16-03,16-05]
  - Roughly second half of growing season
* - Interval 1
  - [01-06,01-21] (day 30)
  - Tillering phase
  - [02-05,02-21] (day 60)
  - Infolorescence emergence
* - Interval 2
  - [01-06,01-21] (day 30)
  - Tillering phase
  - [02-23,03-13] (day 80)
  - Flowering phase
* - Interval 3
  - [01-06,01-21] (day 30)
  - Tillering phase
  - [03-27,04-12] (day 110)
  - Grain filling phase (dough stage)
* - Interval 4
  - [02-05,02-21] (day 60)
  - Infolorescence emergence
  - [03-27,04-12] (day 110)
  - Grain filling phase (dough stage)
* - Interval 5
  - [01-06,01-21] (day 60)
  - Inflorescence emergence
  - [04-16,05-02] (day 130)
  - Grain Ripening
* - Interval 6
  - [02-23,03-13] (day 80)
  - Flowering phase
  - [03-24,04-14] (day 110)
  - Grain filling phase (dough stage)
* - Interval 7
  - [02-23,03-13] (day 80)
  - Flowering phase
  - [04-26,05-12] (day 140)
  - Harvest phase
* - Interval 8
  - [03-27,04-12] (day 110)
  - Gran filling phase (dough phase)
  - [04-26,05-12] (day 140)
  - Harvest phase
```

For the first interval pair `[15-01,15-03]` and `[16-03,16-05]` 250 runs were conducted for irrigation at 10 mm and 25 mm depths, for a total of 500 model runs. For each subsequent interval, 20 runs were conducted for each interval at each irrigation depth, also for a total of 500 models runs. A simple algorithm was used to generate the random dates: First, the two desired date intervals were created. Then, the dates were then chosen with replacement from a unifom distribution including the first and last dates of each interval. For comparison the model was run with no irrigation as well.
 
## Model Output
Aquacrop-OSPY yields the same outputs as Aquacrop and are grouped into four categories: `final_statistics`, `water_flux`, `water_storage` and `crop_growth`. The `water_storage` outputs pertain to the storage of moisture in each layer of soil and were not used in this analysis. The data presented in this report result from aggregating `water_flux` outputs according to their cumulative sum over the season and aggregating `crop_growth` outputs according to the seasonal maximum. Summary statistics (the variance, mean, median maximum and minimum) are then computed for each run of the model and used for the results section.

```{list-table} Variable aggregation
:header-rows: 1

* - Variable included in Aquacrop Model Output (output group)
  - Method used to aggregate values across seasons
* - Yield (tonnes/ha) (crop_growth)
  - Maximum value within each season
* - Biomass (crop_growth)
  - Maximum value for each season
* - Canopy Cover (grop_growth)
  - Maximum value for each season
* - Harvest Index (grop_growth)
  - Maximum value for each season
* - Surface Evaporation (water_flux)
  - Cumulative sum for each seasonm
* - Transpiration (water_flux)
  - Cumulative sum for each season
* - Deep Percolation (water_flux)
  - Cumulative sum for each season
```
