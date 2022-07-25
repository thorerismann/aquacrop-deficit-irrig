# Results

The model results demonstrate that 

The most important measure of crop productivity in In the subsequent discussion "yield" refers to the Aquacrop output Yield (tonnes/hectare), unless otherwise specified. Unless otherwise specified, all days are given in days since planting, with the planting date of December 15th.


## Seasonal values
There is a large variation across growing seasons regardless of the irrigation depths and schedules as the followig charts show. The drops in production seen in the actual values plotted in the introduction are correspond to the drops in each image.

Across seasons, we see that biomass, yield and transpiration are strongly positively correlated. Surface evaporation has a strong negative correlation with yield and biomass, clearly increasing during drought years and decreasing during bumper years.

```{figure} figures/seasonal.png
---
height: 450px
name: Baseline-season
---
Aggregation by growing season of 250 runs of 10 mm and 25 mm irrigation depths with irrigation dates chosen randomly from the intervals [15 Jan,15 Mar] and [16 Mar,15 May]
```
The mean yield converges for all intervals and all depths during seaons with bumper crops. During seasons with severe drought causing drops in yield, increased irrigation clearly improves the yield and there are small differences visible among the different irrigation intervals.
```{figure} figures/season_.png
---
height: 450px
name: interval-season
---
The 8 different irrigation intervals aggregated by season and stratified by irrigation depth.
```

## Yield

The most important measure of crop productivity is Yield (tonnes/hectare).

The below regression plots of yield versus the first and second irrigation day over the baseline set of runs demonstrate that at every irrigation schedule, 25mm of irrigation provides a significantly higher yield than 10 mm. Given the constraints imposed by the randomization method chosen, the following conclusions about the irrigation dates can be taken from the data:
* There are local optimums around day 40 and day 90 for irrigation 1
* There is a local optimum around day 105 for irrigation 2

```{figure} figures/reg-plot-yield.png
---
height: 450px
name: Baseline-yield
---
Regression plot of 250 runs of 10 mm and 25 mm irrigation depths irrigation dates chosen randomly from the intervals [15 Jan,15 Mar] and [16 Mar,15 May] Top represent Yield against the first irrigation date, Bottom row represents yield versus the second irrigation date. Organge is 25 mm irrigation, blue is 10 mm irrigation.
```

Looking at the mean yield in the below figure, we see that increasing the irrigation amount improves mean yield by a relatively constant amount. Further, this effect is more important than the effect of choosing among the 8 irrigation intervals chosen for testing. Nonetheless, the following intervals stand out: 1) day 30/day 110, 2) day 80/day110, and 3) day 110/day 140. The commonality is the irrigation date around during the interval centered around day 110.

There is an inverse relationship between variance and depth, which comes from the irrigation dates being able to mitigate somewhat the effects of drought on the mean yield. The maximum yield varies less  with both irrigation schedule and irrigation depth (notice the scales are not the same for each chart!) than the mean yield. This suggests that the maximum is more determined by favorable climatic conditions than than the mean yield, and conversely that irrigation management has a stronger effect on the mean than on the maximum under these conditions.

Finally, the minimum value corresponds to the growing season with the worst drought for each run. Like the maximum, the minimum varies significantly, but less so than the mean. This implies that the seasonal variation in climatic conditions drives the minimum seasonal yield in each run.

```{figure} figures/yield_int.png
---
height: 450px
name: int-yield
---
Different statistics representing the Yield for each chosen interval. The scatter plots represent the actual values for each random date pair, the line represents the mean value in each plot.
```

The tables below of the top 15 yield mean yields for the interval runs and the baseline run shows the strong correspondace between the two strategies in identifying an optimum. 

```{figure} figures/topbase.png
---
height: 450px
name: baseline-top
---
Top 15 irrigation date combinations by mean yield for the random baseline
```

```{figure} figures/topintervals.png
---
height: 450px
name: intervals-top
---
Top 15 irrigation date combinations by mean yield across all intervals.
```
