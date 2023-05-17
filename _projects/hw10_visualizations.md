---
name: UFO Sightings
tools: [Python, HTML, vega-lite]
image: assets/pngs/ufo2.png
description: UFO Sightings in the US
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

UFO Sightings within the U.S.

## Search The Data & Methods


Playing around with some data collected on UFO sightings within the United States, here are some visualizations.

This first chart splits UFO sighting by seasonal reports and maps the locations out.

<vegachart schema-url="{{ site.baseurl }}/assets/json/hw10_chart2.json" style="width: 100%"></vegachart>



Here is a graph comparing results of surrounding visibility and wind speed reports by state.


<vegachart schema-url="{{ site.baseurl }}/assets/json/hw10_chart3.json" style="width: 100%"></vegachart>



Below is where we can put some links to both the data and the analysis code as buttons:


<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_bcubcg_fall2022/main/data/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/drinkingtea2223/drinkingtea2223.github.io/blob/main/python_notebooks/hw10.ipynb" text="The Analysis" %}
</div>

