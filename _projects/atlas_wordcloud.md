---
name: Playing with WordCloud
tools: [Python, nltk, wordcloud, HTML]
image: assets/pngs/atlas_shrugged_icon.png
description: Experimenting with WordCloud
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

## Some Basic nltk

[WordCloud](https://amueller.github.io/word_cloud/index.html) is a rather special library. Although perhaps not that suited for academic purposes, it is a great tool for providing visualizations that are playful and fun. Both of which are qualities which an onlooker with no knowledge of NLP may find interesting. 

Today I'll be taking a short dive into the words within [Atlas Shrugged](https://aynrand.org/novels/atlas-shrugged/) by Ayn Rand. For starters, let us take advantage of the [nltk](https://www.nltk.org/) library to tokenize our text and parse the words. I used this particular regex which removes punctation and other random characters. However, words such as 'Mr.' and 'Ms.' along with contractions such as "can't" will also get removed, so please be cautioned in your own endeavors when splitting words from text. More words may disappear than you initially anticipate!

```python
tokenizer = RegexpTokenizer(r'\w+')
```
In this particular quest, these words are not so important for me so I used this method without hesitation but for individuals interested in keeping these words with punctation attached it might be better to just tokenize first then remove the punctations after with a more careful replacement method.

Now let us remove the [stopwords](https://www.nltk.org/search.html?q=stopwords) and with the words left we can create this chart of the most common ones. Stopwords are words which are commonly thought of to be 'filler' words and often have no real meaning when taken alone.

![atlas-bar](https://raw.githubusercontent.com/lexeme78557/lexeme78557.github.io/main/assets/pngs/atlas_shrugged_barchart.png)

As a book full of exchanges of dialogue between characters, I am not surprised that 'said' is the most commonly occuring word by a far margin above the rest of the field. What does strike out to me as surprising is the fact that Rearden shows up more frequently than Taggart. The 'protagonist' of the book is clearly Dagny Taggart and although Hank Rearden is the predominant male 'counterpart', I still expected Taggart to appear more as Dagny also has a brother (with last name Taggart) whose name also shows up frequently. I guess that Rearden shows up more as the book frequently mentions his company Rearden Metal but Dagny and her brother also own a company Taggart TransContinental which I suppose falls off latter on. Looking through the list, the next name that follows (skipping Dagny as Taggart is basically referring to her 90% of the time) is Galt. The main question asked throughout the first half of the book is the phrase "Who is John Galt" so it makes sense he would show up next even if he only appears in person much later on. 

Of note is that sometimes 'said' can be thought of as a stopword and will be removed in certain cases but is not explicitly included within the nltk list of English stopwords which I used above.


## Finally onto WordCloud
Looking at a barchart can be tedious and the one above is limited to 50 of the most common words. If the number were to be increased to say 100, the graph bars would be too small to reasonably make out word labels anymore. Furthermore, reading a bar chart simply isn't fun. This is where wordcloud can come into play. With our dictionary of words and their counts, we can create the following visualization.

![atlas-words](https://raw.githubusercontent.com/lexeme78557/lexeme78557.github.io/main/assets/pngs/atlas_shrugged_wordrect.png)

Here the words are displayed such that their size is in proportion with its frequency. Larger words in the rectange mean they occur more frequently in our text. The word rectangle is colorful and the larger words capture my attention immediately and I am able to glean the same information as I could from the bar chart but in an easier fashion.


Now one final upgrade, rectangles are boringly shaped. Instead let us choose an image which is more representative of our text. I have chosen an image of [Atlas](https://wallpaperaccess.com/full/6875296.jpg) which is quite apropo for this particular novel both in terms of the title and for the story which the novel tells. Here we generate a wordcloud but with some image outlining thanks to [cv2](https://opencv.org/), the wordcloud can be transformed to be colored in a similar fashion to our selected Atlas image. At first I was not so much of a fan of this as I felt the original color pallete of purple, green, and yellow was quite nice but this Earthen color due to my selected image feels more fitting for the story and I am pleased with the results.

![atlas-colored](https://raw.githubusercontent.com/lexeme78557/lexeme78557.github.io/main/assets/pngs/atlas_shrugged_coloredimg.png)