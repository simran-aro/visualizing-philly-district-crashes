---
layout: default
altair-loader:
  altair-chart-1: "charts/measlesAltair.json"
hv-loader:
  hv-chart-1: ["img/crash_data_heatmap.html", "200", "500"] # second argument is the desired height
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "400"] # second argument is the desired height
  folium-chart-2: ["charts/percent_no_internet.html", "400"] # second argument is the desired height
---

# Introduction!

PennDOT collects and shares data on crashes for every year to increase education and awareness around safety. This data can be found [here](https://www.penndot.pa.gov/TravelInPA/Safety/pages/crash-facts-and-statistics.aspx). In this project, data from PennDOT was analyzed for three Philadelphia districts: North, Central and South. This project aims to create spatial components for this data to visualize where crashes are happening, and to create a crash index. This was done with the help of several packages developed for geospatial analysis in Python including OSMnx and folium, along with other packages like matplotlib, geopandas and altair to create charts.

# Methodology

This projects concentrates on spatial analysis. Philadelphia district boundaries were isolated, and spatial operations were performed to only extract street networks and nodes within the districts. Next, crashes were visualized in Philadelphia. Visualizations using heatmaps were created using folium to see where the crashes occur most. These were then separated by times of day, days of week and months to see if there were any patterns. 

To create the crash index, nearest nodes from each crash were extracted. A dataset of crashes per street was made, and the index was calculated by dividing the number of crashes per street by the lenght of the street. This 'crash index' was then visualized for every district.

## Districts with Streets

Philadelphia's Central District

![phl-central]({{ site.url }}{{ site.baseurl }}/images/central.png)

Philadelphia's North District

![phl-north]({{ site.url }}{{ site.baseurl }}/images/north.png)

Philadelphia's South District

![phl-south]({{ site.url }}{{ site.baseurl }}/images/south.png)

## Philadelphia's Crashes in 2021, visualized

![crashes]({{ site.url }}{{ site.baseurl }}/images/crashes.png)

While this map indicates crashes, it is difficult to read because all the dots are the same size. The density of crashes is definitely higher in some districts. A better visualization method is to create a heatmap. The following map is a heatmap of the data shown in the image above. In it we see that Central, North and South districts in Philadelphia are where crashes occur more. Thus, I chose to analyze these further. 

<div id="hv-chart-1"></div>



<div id="altair-chart-1"></div>

This was produced using Altair and embedded in this static web page. Note that you can also display Python code on this page:

```python
import altair as alt
alt.renderers.enable('notebook')
```

## HvPlot Example

Lastly, the measles incidence produced using the HvPlot package:



## Notes

- See the [lecture 13A slides](https://musa-550-fall-2021.github.io/slideslecture-13A.html) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**

# Example: Embedding Folium charts

This post will show examples of embedding interactive maps produced using [Folium](https://github.com/python-visualization/folium).

## OSMnx and Street Networks

The shortest route between the Art Museum and the Liberty Bell:

<div id="folium-chart-1"></div>

<br/>

## Percentage of Households without Internet

The percentage of households without internet by county:

<div id="folium-chart-2"></div>

See the [lecture 9B slides](https://musa-550-fall-2021.github.io/slides/lecture-9B.html) and the [lecture 10A slides](https://musa-550-fall-2021.github.io/slides/lecture-10A.html) for the code that produced these plots.
