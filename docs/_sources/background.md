# Introduction

## Crop modelling

Crop growth models are valuable tools for researchers and practictioners to push the bounds of scientific konwledge, explore techniques to boost production and efficiency and take grounded agricultural decisions. This is only more important as the amount of arable land per person decreases while consumption rises and the effects of climate change begin to accelerate. Crop modeling is itself a classic interdisciplinary effort with contributions from economicsts, computer scientists, botanists, agricultural systems scientists and more {cite}`JONES2017240`. Today's models reflect this diverse history and have been driven by a number of different research agendas from contributing fields and vary significantly in complexity, accessibility and target end-user.

The Aquacrop model was developed by the Food and Agricultural Organization (FAO) in 2009 to simulate realistic yields of common crops grown throughout the world. The program was designed to balance the robustness of results with the need to keep both the paramaterization and the required data files simple. This is because the program is aimed mainly at practitioners, such as public and private sector agriculture managers {cite}`aquacrop`. Aquacrop comes with an extensive documentation and a number of practical exercises making it an ideal tool as well for students and for practitioners who do not have a programmatic background to nonetheless take advantage of the analytical possibilities offered by modern crop models {cite}`fao1`. The FAO continues to support Aquacrop with regular releases and updates published to its website {cite}`fao_2`.

The first main extension to Aquacrop was the Aquacrop-OS package developed and released as an open source alternative to Aquacrop to address some of the inherent limitations of the original framework. First, as an open source program built in Matlab/Octave, the code is available to anyone and can be run in any operating system. Further, since Aquacrop is a compiled program, lack of access to the source code limits some uses of the model, such as the ability test the influence of the model structures internal to Aquacrop on the results {cite}`aquacropos`. Testing shows that Aquacrop-OS results are in 99% agreement with Aquacrop results demonstrating the viability of the program to be used interchangeably with Aquacrop {cite}`aquacropos`. There is extensive documentation for the Aquacrop OS model {cite}`aquacropos1` and since publication in 2017, a number of research articles have used the Aquacrop-OS module in place of Aquacrop {cite}`rs12162666,w12041080,Zhang2019,anothercite`. 

The framework of the Aquacrop-OS model was extended with the publication of the Aquacrop-OSPY module. This Python 3 module implements the Aquacrop-OS framework to allow for the easy use of the many useful data science extentions available with Python {cite}`KELLY`. While the documentation is not as complete as for Aquacrop and Aquacrop-OS, Aquacrop-OSPY nonetheless has quality documentation that can allow a new user to get started using the data package {cite}`kelly1`. One main advantage for using Aquacrop-OSPY is to take advantage of the efficiency of the Python language to generate a large number of runs model runs programmatically and store the outputs in a convenient way. Since publication in 2021, there have already been a small number of peer reviewed articles that take advantage of this module, see {cite}`LYU2022157104,hess-26-923-2022,w14081188`.


## Tunisia Background
Assessing deficit irrigation of wheat is a critically important issue for Tunisia.  While production and yield per hectare have both increased steadily since 1960, the population has steadily increased and the amount of land devoted to wheat cultivation has declined over the same period, leading to a continued heavy reliance on food imports over this period, as can be seen in Figure 1 {cite}`indexmundi,worldbank`. Like many countries in the Middle East and North Africa, Tunisia relies on imported wheat to feed its population: in 2021 this amounted to 479 million USD, 42% of which came from Ukraine {cite}`fao1,OEC`. Clearly this puts the population in serious risk in light of the recent escalation of the conflict and resulting uncertainty regarding Ukranian grain exports {cite}`anews,fao1`. As the current events discussed demonstrate, Tunisia's population of 11 million already faces signifcant challengs in terms of domestic food security.

```{figure} figures/summary_wheat.png
---
height: 600px
name: Historical statistics on wheat in Tunisia
---
Top: Annual wheat production (green), imports (yellow), consumption (blue); Bottom: harvest area, with respected growth rates; Data from IndexMundi.com
```

Furthermore, optimism in spring 2022 about a potential bounty harvest in Tunisian wheat production had turned into concern over a crop reduced greatly by wildfire and drought by early July 2022{cite}`Amara`.Tunsia's climate is characterized by a hot, dry summer with minimal rain and we, mild winders, as the monthly figures for precipation and air temperature {cite}`worldbank2` show in Figure 3. According to the Köppen-Geiger climate classication, Tunisia is already in an arid mediteranean climate, with a very dry summer, and the outlook is that increasingly desert-like conditions will encroach within the next several decades {cite}`KG`. As such optimizing the use of water resources through techniques such as deficit irrigation will only become more critical for domestic wheat production.

## Deficit irrigation 
Deficit irrigation is the practice of irrigating strategically during a crop's development to maximize the yield of the crop given significant constraints on irrigation {cite}`definition1`. As previously described, Tunisia is an arid mediteranean climate where deficit irrigation is already practiced. Available projections show that precipitation will likely decrease and temperatures will likely increase, both factors that decrease the water availability in the soil for crop development. This means that deficit irrigation will be an increasingly important topic for Tunisia and the region going forward.

In order to optimize irrigation using this strategy one needs to identify the different phenological stages of the plant's growing cycle, then determine the parts of the growing cycle during which application of water will optimize crop productivity. For grains, irrigation is generally optimal during the flowering and fruiting phase of the crop, while Determining the precise growing stages of a crop is quite difficult, as a crops development is dependent on climate conditions, soil and land management, and the exact variety of the crop. A composite timeline of the growth cycle of Durum wheat obtained from two sources was used in this report {cite}`pheno,grdc`, with the vegetative phase lasting until around 65 days from planting, with the crop ready to harvest before 170 days after planting.




```{bibliography}
```
