---
title: Illinois Building Inventory Visualization
tags: [Illinois, Inventory, Visualizations]
style: fill
color: secondary
description: A look at building contruction in Illinois.
---

Source: [portfolYOU](https://github.com/YoussefRaafatNasry/portfolYOU)

This project analyzes Illinois state-owned buildings using Python, Pandas, and Altair.

## Visualization 1: Building Size by Usage

<vegachart schema-url="{{ '/assets/json/building_sizes.json' | relative_url }}" style="width: 100%"></vegachart>

In this visualization we can see how large buildings in Illinois are depending on what category of building they are. It shows detentional dacilities as the largest median size, with business and healthcare following close behind. For this visualization, I decided to visualize the types of buildings that were the most common in Illinois, which ended up with the 8 seen above. This means that there might by building usage types that have a larger square footage on average, but are not nearly as common in Illinois. The x-axis of the visualization (Square Footage) was encoded as quantitative, due to it being a numerical building size measurement. The y-axis (Usage Description) was encoded as nominal due to it being categorical data that did not have a set order. For the color scheme, a simple blue was chosen, as there is not a third layer of data that requires a colormap. I felt that keeping the bars one color maintained understandability. 

For the data, I first converted the square footage column to numeric and then dropped and invalid values. From there, I then only kept data points that had a square footage above 0 and were contructed between 1800 and 2026. This is because buildings made before 1800 or that have a square footage of 0 likely indicate some type of erroneous entry given that Illinois was founded after 1800 and buildings with no area are not usable. These 0 square footage values may correspond to PO boxes or something similar and therefore are not relevant for our purposes. 




## Visualization 2: Construction by Decade

<vegachart schema-url="{{ '/assets/json/building_decades.json' | relative_url }}" style="width: 100%"></vegachart>

For this visualization, it shows how many buildings were contructed by decade, spanning from 1900's to 2010's. What we do see is a large fall-off in building construction towards around the 2010's in every building usage category. Some categories also have a large spike during one decade and a relatively small number constructed during the other decades. For example, healthcare and residential buildings. The x-axis (Decade) in this visualization was encoded as ordinal because it is categorical data that contains a chronological nature to it, and was converted from date time to vategorical decades. The y-axis (Count of Constructed Buildings) was encoded as quantitative because the count is a numerical value. The dropdown (Usage Description) was encoded as nominal because it is a categorical variable with no built-in order to it. For the color, I chose a simple orange because there is no varaible represented by the color. The dropdown shows the category so the color is not neccessary. The data transformations performed for this visualization was similar to the ones performed for the first visualization. The data was cleaned to only include buildings with greater than 0 square footage and valid values. The main difference is that this visual only looks at buildings contructed from 1900 onwards.

## Interactivity

The interactivity for this plot I chose is a dropdownmenu that lets you filter the number of buildings contructed each decade by the category of usage. This adds another layer to the visualization as you can see which types of usage were prioritized and when and could potentially compare that to historical reasons that might be true. This interactivity applies to the second plot. It also lets you see some interesting trends about building construction and which types of buildings don't follow those trends. 

## 4. Data and Analysis Links

[Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)

[Analysis](https://github.com/nikhil-koka/nikhil-koka.github.io/blob/main/python_notebooks/homework_visualizations.ipynb)

<script src="https://cdn.jsdelivr.net/npm/vega@6"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@6"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@7"></script>
<script src="{{ '/assets/js/justcharts.js' | relative_url }}"></script>
