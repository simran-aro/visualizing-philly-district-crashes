---
layout: default
altair-loader:
  altair-chart-1: "charts/measlesAltair.json"
hv-loader:
  hv-chart-1: ["assets/img/crash_data_heatmap.html", "500", "800"] 
  hv-chart-2: ["assets/img/crash_data_heatmap_time.html", "500", "800"]
  hv-chart-3: ["assets/img/crash_data_heatmap_days.html", "500", "800"]
  hv-chart-4: ["assets/img/crash_data_heatmap_months.html", "500", "800"]
  hv-chart-5: ["assets/img/center_crash_index.html", "500", "800"]
  hv-chart-6: ["assets/img/center_crash_index_n.html", "500", "800"]
  hv-chart-7: ["assets/img/center_crash_index_s.html", "500", "800"]

---

# Introduction

PennDOT collects and shares data on crashes for every year to increase education and awareness around safety. This data can be found [here](https://www.penndot.pa.gov/TravelInPA/Safety/pages/crash-facts-and-statistics.aspx). In this project, data from PennDOT was analyzed for three Philadelphia districts: North, Central and South. This project aims to create spatial components for this data to visualize where crashes are happening, and to create a crash index. This was done with the help of several packages developed for geospatial analysis in Python including OSMnx and folium, along with other packages like matplotlib, geopandas and altair to create charts.

# Methodology

This projects concentrates on spatial analysis. Philadelphia district boundaries were isolated, and spatial operations were performed to only extract street networks and nodes within the districts. Next, crashes were visualized in Philadelphia. Visualizations using heatmaps were created using folium to see where the crashes occur most. These were then separated by times of day, days of week and months to see if there were any patterns. 

To create the crash index, nearest nodes from each crash were extracted. A dataset of crashes per street was made, and the index was calculated by dividing the number of crashes per street by the lenght of the street. This 'crash index' was then visualized for every district.

## Districts with Streets

Philadelphia's Central District

![phl-central]({{ site.url }}{{ site.baseurl }}/assets/img/central.png)

Philadelphia's North District

![phl-north]({{ site.url }}{{ site.baseurl }}/assets/img/north.png)

Philadelphia's South District

![phl-south]({{ site.url }}{{ site.baseurl }}/assets/img/south.png)

## Philadelphia's Crashes in 2021, visualized

![crashes]({{ site.url }}{{ site.baseurl }}/assets/img/crashes.png)

While this map indicates crashes, it is difficult to read because all the dots are the same size. The density of crashes is definitely higher in some districts. A better visualization method is to create a heatmap. The following map is a heatmap of the data shown in the image above. In it we see that Central, North and South districts in Philadelphia are where crashes occur more. Thus, I chose to analyze these further. 

<div id="hv-chart-1"></div>

The following visualization shows the hours of the day when crashes occur. Do you see any patterns? There are more crashes during the evening- the time when folks are going home during work. Another high incidence time is morning rush hours. I used the same method to see if there were any patterns for days of the week and months. While the visualization for months did not give any conclusive answers, weekends were certainly days when crashes occured more. 

#### Crashes aggregated by hour of day

<div id="hv-chart-2"></div>

#### Crashes aggregated by day of week

<div id="hv-chart-3"></div>

#### Crashes by months of 2021

<div id="hv-chart-4"></div>

## Crash Index

To create the crash index, the number of crashes per street was divided by the lenght of the street. This number was log transformed and then normalized into an index. The lower the number the more dangerous the street is. The frequency of the index is visualized in the graphs below, for every district.

![g1]({{ site.url }}{{ site.baseurl }}/assets/img/central_crash_ind.png)

![g2]({{ site.url }}{{ site.baseurl }}/assets/img/north_crash_ind.png)

![g3]({{ site.url }}{{ site.baseurl }}/assets/img/south_crash_ind.png)

## Spatializing the Crash Index for the Three Districts

The darker the color, the more crashes that have happened on that street. The yellow streets represent those that have no crashes. It can be seen that highways and larger roads are the ones that perform poorly on the crash index.

Central District

<div id="hv-chart-5"></div>

North District

<div id="hv-chart-6"></div>

South District

<div id="hv-chart-6"></div>
