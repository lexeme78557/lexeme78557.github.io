---
name: Visualization of WikiText-2
tools: [Python, torch, HTML, NLTK]
image: assets/pngs/cbow_viz_icon.png
description: TSNE of Word Embeddings of CBOW Model
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---



## Introduction

There are many methods on how to train a model to predict an unknown word. Today lets take a look at Continuous-Bag-of-Words (CBOW) Embeddings. CBOW works by predicting a single word based on a fixed window size of context words. For example, if our sentence is "The boy walked the dog in the park", using the context words of ["boy", "walked", "dog", "in"] we try to predict "the". The [original paper](https://arxiv.org/pdf/1301.3781.pdf) shows CBOW to be a fast converging algorithm which works well in learning syntactic relatinoships between words.  



<body>
    <div>                        <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script type="text/javascript">/**
* plotly.js v2.18.2
* Copyright 2012-2023, Plotly, Inc.
* All rights reserved.
* Licensed under the MIT license
*/
/*! For license information please see plotly.min.js.LICENSE.txt */
</body>



For the visualization, I used [WikiText-2](https://arxiv.org/pdf/1609.07843v1.pdf) which is formed from a collection of Wikipedia articles. To construct our CBOW model，I have an embedding layer followed by one hidden layer then an output layer. After succesfully training the model on the WikiText2 dataset, we can extract the weights from the embedding layer to create the [TSNE](https://en.wikipedia.org/wiki/T-distributed_stochastic_neighbor_embedding), a technique to embedding high dimensional data for visualization in low dimension space. The visualization shows the thousand most frequent words. Panning through the visualization, you may see many clusters which make sense such as words relating to time being closeby such as  "hours, minutes, century". There are also large gaps in other similar words such as the months of the year which are scattered far and wide. At a high level, words with similar meanings should cluster together, however when reducing dimensionality, it is unclear what exact factors are chosen to represent words so there will be some strange effects present.
