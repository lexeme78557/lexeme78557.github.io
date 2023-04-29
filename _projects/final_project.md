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


Here is a plot showing the amount of recorded cases by month in New York City. We can see that December 2021 was by far the most severe month of the last three years. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart2.json" style="width: 100%"></vegachart>



Interested in how other cities compared, here is a similar graph but for the city of Chicago. Though not as drastic as in NYC, we also can see that December 2021 along with January 2022 were the two most severe months in terms of number of cases. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart5.json" style="width: 100%"></vegachart>

Same as we saw in Chicago, for Los Angeles the peaks also occurred in December 2021 along with January 2022. It seems that these are the two most severe months across America. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/p2_chart6.json" style="width: 100%"></vegachart>



Below is where we can put some links to both the data and the analysis code as buttons:


<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/nychealth/coronavirus-data/master/trends/data-by-day.csv" text="NYC Data" %}
</div>

