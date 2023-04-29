---
name: Covid19 Representations in NYC
tools: [Python, HTML, vega-lite]
image: assets/pngs/nyc_covid.png
description: Final Project
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

Covid Reports for Large Cities in America --- Dylan Han

## Some Quick Visualizations

The recent Corona Virus Epidemic has made quite a mark in terms of interupting daily goings. Curious as to how things were going in other cities in America, I decided to take a look and make some visualizations for some of the larger cities where spreading is likely to be more common. 


<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart3.json" style="width: 100%"></vegachart>

Here is a depiction of case and hospitalization counts for NYC within the last few years. The darker the color indicates the more recent the listing. We can see that as of recent, the numbers are quite low which is a good sign of things to come. The last signs of obvious red come from January 2022 which is already over a year ago. The graph is quite large in terms of scaling and we can pick a month to look at yearly trends more easily. After panning around, double click to bring the graph back into focus. Looking at July or September can be quite scary individually but thankfully the axises scales are quite small and are tiny in terms of the bigger picture. Hovering over datapoints will also show some more detailed information of the counts recorded.


Here is a plot showing the amount of recorded cases by month in New York City. We can see that December 2021 was by far the most severe month of the last three years. I've chosen a slightly differing color palette but still red as I feel it is the only color suitable for shading in this topic of pandemic.

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart2.json" style="width: 100%"></vegachart>



Interested in how other cities compared, here is a similar graph but for the city of Chicago. Though not as drastic as in NYC, we also can see that December 2021 along with January 2022 were the two most severe months in terms of number of cases. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart5.json" style="width: 100%"></vegachart>

Same as we saw in Chicago, for Los Angeles the peaks also occurred in December 2021 along with January 2022. It seems that these are the two most severe months across America. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart6.json" style="width: 100%"></vegachart>

For further investigations I will take a dive into reports for other large cities. 




The original data is taken from https://data.gov/ but I've done some editting and here are the versions I am using

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/drinkingtea2223/drinkingtea2223.github.io/main/assets/datasets/nyc_data.csv" text="NYC Data" %}
{% include elements/button.html link="https://raw.githubusercontent.com/drinkingtea2223/drinkingtea2223.github.io/main/assets/datasets/chicago_data.csv" text="Chicago Data" %}
{% include elements/button.html link="https://raw.githubusercontent.com/drinkingtea2223/drinkingtea2223.github.io/main/assets/datasets/la_data.csv" text="LA Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/drinkingtea2223/drinkingtea2223.github.io/blob/main/python_notebooks/p3.ipynb" text="The Analysis" %}
</div>

