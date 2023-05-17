---
name: Farmer's Markets
tools: [Python, altair, HTML, vega-lite]
image: assets/pngs/nyc_covid.png
description: Visualization of Farmer's Markets within Massachusetts
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

Farmer's Markets

## Some Quick Visualizations

Growing up in a small town surrounded by farms and field crops, the running joke at the high school was that we had more cows than students (probably not true but it's pretty close!). Supporting locally grown produce was always a big thing in our area. Curious to see where else in the state I could look for more fresh vegetables, here are the results of my search.


<vegachart schema-url="{{ site.baseurl }}/assets/json/farmer_market_chart1.json" style="width: 100%"></vegachart>

Each dot on the chart represents one farmer market location and hovering over a dot will show the location and town along with a website if available. There is also the dropdown menu at the bottom which has towns sorted alphabetically. If your town does not appear on the list, it likely does not have its own farmer's market. A very unfortunate result, but there are  over 300 markets spread around the state. Surely one of them is close by enough to visit! 

One critique about this map I've made is that there is no function to zoom in/out. Unlike other altair maps, this one is built with geodata involved and is still a work-in-progress with limited features. The background projection of Massachusetts is also one I made myself as the current libraries only support all of United States which makes our region of interest too small to really make much sense of, especially without a zoom in feature available.

![large-map](https://raw.githubusercontent.com/drinkingtea2223/drinkingtea2223.github.io/main/assets/pngs/big_awkward_fm.png)

I had originally made the graph with ipywidgets and contextily but unfortunately it is impossible to transport the widget and maintain its interactivity.

![ctx-map](https://raw.githubusercontent.com/drinkingtea2223/drinkingtea2223.github.io/main/assets/pngs/fm_mass_ctx.png)

For individuals interested in seeing this particular rendering with a more realistic map background, please try out the code below in a jupyter notebook or some other python setting.

'''
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  import geopandas 
  import ipywidgets
  import contextily as ctx


  mass = geopandas.read_file("https://arcgisserver.digital.mass.gov/arcgisserver/rest/services/AGOL/Massachusetts_Counties/MapServer/0/query?outFields=*&where=1%3D1&f=geojson")
  markets = geopandas.read_file("https://arcgisserver.digital.mass.gov/arcgisserver/rest/services/DPH/DPH_Farmers_Markets/MapServer/0/query?outFields=*&where=1%3D1&f=geojson")

  markets_subset = markets.loc[markets["TYPE"]!="Farmers Markets"]

  @ipywidgets.interact(btype=sorted(set(markets['TOWN'].unique())))

  def interact_plot(btype):
      markets_subset = markets.loc[markets["TOWN"]==btype]
      fig, ax = plt.subplots(1, 1, figsize=(10,10))

      mass.plot(ax=ax, alpha=0.5, edgecolor='k')
      markets_subset.plot(column="TOWN", ax=ax, cmap='rainbow', categorical=True, legend=True)
      
      ctx.add_basemap(ax=ax, crs=markets.crs.to_string())

      plt.show()

'''

The data regarding farmer's markets is taken from https://hub.arcgis.com/ with a huge thanks to https://github.com/johan/world.geo.json for providing geojson data for my altair base projection. 



