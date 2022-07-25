# Introduction

## Aquacrop

Crop growth simulation tools are a valuable part of the toolkits of both farm managers and researchers. The Aquacrop model was developed by the Food and Agricultural Organization (FAO) in 2009 to simulate realistic yields of common crops grown throughout the world. The program was designed to balance the robustness of results with the need to keep both the paramaterization and the required data files simple. This is because the program is aimed mainly at practitioners, such as public and private sector agriculture managers {cite}`aquacrop`. Aquacrop comes with an extensive documentation and a number of practical exercises making it an ideal tool as well for students and for practitioners who do not have a programmatic background {cite}`fao1`. 

Aquacrop-OS was developed as open source alternative to Aquacrop to address some of the limitations of the original software and framework. First, as an open source program built in Matlab/Octave, the code is available to anyone and can be run in a number of programming languages and operating systems. Further, since Aquacrop is only available as a compiled program, lack of access to the source code limits the ability of the model to be used in interdisciplinary analysis and to test the influence of the model structures internal to Aquacrop on the results. Testing shows that Aquacrop-OS results are in 99% agreement with Aquacrop results demonstrating the viability of the program to be used interchangeably with Aquacrop {cite}`aquacropos`. There is extensive documentation for the Aquacrop OS model {cite}`aquacropos1` and since publication of Aquacrop-OS there is notably a Python and an R implemention. 

The framework of the Aquacrop-OS model was extended with the publication of the Aquacrop-OSPY module. This Python 3 module implements the Aquacrop-OS framework to allow for the easy use of the many data science extentions available within the Python framework {cite}`KELLY`. While the documentation is not as complete as for Aquacrop and Aquacrop-OS, Aquacrop-OSPY nonetheless has extensive documentation that can allow a new user to jump into using the data package {cite}`kelly1`. one main advantage for using Aquacrop-OSPY is to take advantage of the efficiency of the Python language to generate a large number of runs model runs programmatically and store the outputs in a convenient way.

## Tunisia Background
Assessing deficit irrigation of wheat is a critically important issue right now for Tunisia. Like many countries in the Middle East and North Africa, Tunisia relies on imported wheat as an important staple food for its population {cite} `fao1`. While production has increased steadily since 1960, since the amount of land devoted to wheat cultivation is on a long term decline, the reliance on food imports has also increased over this period as can be seen in Figure 1. {cite}`indexmundi`. Decline in arable land devoted to wheat production has constrained the ability of productivity improvement to meet domestic consumption (Ibid). As of 2021, Tunisian wheat imports stood at 479 million USD, 42% of which came from Ukraine {cite}`OEC`, which puts the population in serious risk in light of the recent escalation of the conflict and resulting uncertainty regarding Ukranian grain exports {cite}`anews`. Furthermore, optimism in the spring about a potential bounty harvest in Tunisian wheat production has turned into concern over a crop damaged severaly by wildfires and drought {cite}`Amara`.

```{figure} figures/summary_wheat.png
---
height: 600px
name: Historical statistics on wheat in Tunisia
---
Top: Annual wheat production (green), imports (yellow), consumption (blue); Bottom: harvest area, with respected growth rates; Data from IndexMundi.com
```

As current events discussed previously demonstrate, Tunisia's population of 11 million {cite}`worldbank` already faces signifcant climate challenges. Tunsia's climate is typified by the lack of rain in the summer, and the opportunity to grow crops during the wet and relatively mild winders, as the monthly figures for precipation and air temperature {cite}`worldbank2` show in Figure 3. According to the Köppen-Geiger climate classication, Tunisia is already in an arid mediteranean climate, with a very dry summer, and the outlook is that increasingly desert-like conditions will encroach within the next several decades {cite}`KG`.

```{figure} figures/summary_temp_rain.png
---
height: 400px
name: tunis-climate
---
Temperature and precipitation over the year, data from the World Bank
```

## Deficit irrigation 
Deficit Irrigation is a strategy of irrigating strategically during a crop's phenological development to maximize the yield of the crop given significant constraints on irrigation {cite}`definition1`. As previously described, Tunisia is an arid mediteranean climate where deficit irrigation is already practiced. Available projects show that precipitation will likely decrease and temperatures will likely increase, both factors that decrease the water availability in the soil for crop development. This means that deficit irrigation will be an increasingly important topic for Tunisia and the region going forward.

In order to optimize irrigation one needs to identify the different phenological stages of the plants growing cycle. The below figure gives the major growing stages of Durum wheat under two growing conditions, the first simulating conitions in 2020 and the second simulationg projected conditions in 2070 in Italy {cite}`pheno`. Considering Tunisia is a similar climate, but a bit more arid, it was decided to use a subjective combination of the 2020 and 2070 indications to represent the phenological stages for Winter Wheat in Tunisia. While there is a certain amount of variation of phenological development based on the exact variety, field management and local climate and soil conditions, this graphic agrees roughly with other sources and provides the baseline phenological stages for this report {cite}`grdc`. In this study, deficit irrigation is reduced to irrigating three times during the growing season. The first occurs at planting, while the second and third irrigation dates are chosen from different stages in the plants phenological cycle.


```{figure} figures/pheno.png
---
height: 400px
name: Phenology
---
Phenological development of Winter Wheat
```



```{bibliography}
```
