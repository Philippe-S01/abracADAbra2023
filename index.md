---
layout: page
title: A world full of clichés
subtitle: Using data extracted from Wikispeedia to analyze clichés around the world
use-site-title: true
cover-img: /assets/img/graph.png
thumbnail-img: /assets/img/graph.png
share-img: /assets/img/graph.png
---

----------------

Nowadays, clichés play a significant role in shaping our view of the world. For instance, when one considers France, there is a tendency to connect it with emblematic symbols such as Eiffel Tower, cheese, wine or even cigarettes. Similarly, when thinking about the sun, it’s common to associate it directly with certain countries, such as Costa Rica or Mexico. Whereas these associations accurately reflect reality is a matter of debate. Nevertheless, a question may arise: **How do these clichés shape our processes of thought?**

Using the Wikispeedia dataset, our objective is to analyze the impact of clichés in our research process, with a primary emphasis on those associated with different countries. The dataset provides all the paths of the players, finished and unfinished, allowing us to establish whether they rely on common ideas or concepts to navigate through the pages. In this case, clichés manifest in the form of Wikipedia’s article or categories of these articles.

In understanding real-world networks, it is crucial to recognize the specific way in which they are connected. Wikipedia, being a representative of a similar network, is made of hyperlinks that contains many short-range, and few long-range, connections. This specific semantic space is perceived by humans, and Wikispeedia, as a game, becomes particularly interesting in tackling the small world property. Through our exploration, we will specifically consider how our notion of clichés aids us in navigating through the hyperlinks. One may wonder **if clichés help us navigate through the game.**

----------------

## *What do we have ?*

The dataset is composed of diverse articles and categories, forming the basis of analysis on clichés related to countries. This may raise the question of their substantial representation in the dataset. Indeed, among the top fifty most visited articles, eleven are centered around countries, highlighting a recurrent theme in the dataset. Notably, the United-States of America emerges as the most visited article with 8654 occurrences.

<!-- add the plot top_50_visited_articles.html -->

<iframe src="assets/plot/top_50_visited_articles.html" width="750px" height="530px" frameborder="0" position="relative">Top 50 visited articles</iframe>

Furthermore, the articles within the top fifty target articles feature less notable presence of countries or continents. But then, one may wonder why countries are such a prevalent theme within the paths. (??)

<!-- <p style="color:blue"><em>(add an arrow above the ones that are countries/continents or plot them in a different color?)</em></p> -->

<!-- add the plot top_50_visited_articles.html -->

<iframe src="assets/plot/Percentage_Pos_UK_Path.html" width="750px" height="530px" frameborder="0" position="relative">Top 50 visited articles</iframe>

<!-- add the assest/img/HOMERRRRR.jpg -->

<p align="center">
  <img src="assets/img/HOMERRRRR.jpg" width="500" title="Homer Simpson">
</p>

----------------

## *What is a cliché and how can we find them?*

In this context, when we refer to clichés, we are addressing stereotypes – commonly held ideas and concepts that rapidly come to mind when thinking about a particular subject.

Various approaches were considered to establish clichés associated with a specific country. Initially, manual selection was contemplated, but this posed a risk of significant bias as it relied solely on the perspectives of five individuals. An alternative method involved using artificial intelligence, such as Chat-GPT, to generate clichés associated with a particular nationality. The last option explored data augmentation – a different data set was used to link clichés with articles and/or categories. This process involved text analysis and particularly topic detection. 

----------------

## *Is there any abnormal result that could be analyzed in the scope of our subject?*

Before diving more into the analysis of the impact of clichés on our data, let’s see if there is any particularity in the data that could be explored through the point of view of the clichés. For this, the distribution of the length and the duration of the path have been observed and both measure present expected plots. 

<iframe src="assets/plot/Path_length_vs_duration.html" width="750px" height="530px" frameborder="0" position="relative">Top 50 visited articles</iframe>


The relationship between the length of the path and the rating given by the player followed an increasing linear relationship. 

<iframe src="assets/plot/length_difference_rating.html" width="750px" height="530px" frameborder="0" position="relative">Top 50 visited articles</iframe>


Everything seems “normal”.

----------------

## *But how can we explore them ?*

Exploring clichés through different measures: Statistics and Categories
The articles are defined, amongst other, by categories. It could be interesting to see how often categories from clichés occur in the path containing our subject of interest: United_Kingdom. Are some types of cliché articles more present than others? Do their categories match the ones from United_Kingdom or not at all? 
The results are not very conclusive… Is it the end? ☹

The analyses done previously did not show any result that could represent a sign of influence of the clichés on our way of playing the game. However, we believe that common thinking is usually led by predefined ideas of concept, here of a place: United_Kingdom. So why is it so?

We asked ourselves the question and thought about it in greater depth. We raised three hypotheses:
* The clichés do not really have an influence on the path
* The data and the scope of the game do not allow us to find “significant results” as the paths are usually small and there is no hyperlink 
* Our set of clichés is not great enough, so we use data augmentation

----------------

## *How could we augment our data?*

For the data augmentation, we explored several ways of extracting clichés.
In this scope, we looked at different ways to connect the articles and the reference article “United_Kingdom”. We have selected different measures:
* Common topics 
* Similar proper nouns in the text
* Common hyperlinks

<ol>
<li>For the topics, we proceeded using Tokenization. This process allowed us to break the text into small chunks, words that we then categorized under different topics using a seagull package. As these tokens can contain non-meaningful words such as ‘a’, ‘at’, etc. we decided to further filter them using stop words removal.
This analysis did not give us any 'good' results. In fact, our process of categorisation into different topics gave us fairly general genres that were found in most of the articles. More in-depth text analysis and a more precise and detailed categorisation could perhaps have given us better results.
However, given our level of knowledge of text analysis, we decided to turn to another way of approaching the text: proper nouns.

<<<<<<< HEAD
<iframe src="assets/plot/random_common_topics.html" width="750px" height="200px" frameborder="0" position="relative">Top 50 visited articles</iframe></li>
=======
<iframe src="assets/plot/random_common_topics.html" width="750px" height="250px" frameborder="0" position="relative">Top 50 visited articles</iframe>
>>>>>>> 036d406abbc1c926cbcecaf6515e39fa7cbfaf67

<li>Indeed, proper nouns seemed to be a good alternative as they generally represent a good indication of the subjects covered in a text, whether they be names of countries, people, and so on.
To do this, we again used tokens, but in addition we used a natural language processing feature that allows us to assign each word its function in the sentence. 
Note that this feature has a few limitations, particularly when it comes to common nouns, which end up as the subject and head of the sentence. This is probably due to the fact that this is a basic analysis. We will keep these limitations in mind for future analyses. Given the limitations, this result alone also did not give us satisfactory results.

<<<<<<< HEAD
<iframe src="assets/plot/common_proper_nouns.html" width="750px" height="200px" frameborder="0" position="relative">Top 50 visited articles</iframe></li>
=======
<iframe src="assets/plot/common_proper_nouns.html" width="750px" height="250px" frameborder="0" position="relative">Top 50 visited articles</iframe>
>>>>>>> 036d406abbc1c926cbcecaf6515e39fa7cbfaf67

<li>Finally, we turned to a part of the data that we had not yet explored: hyperlinks. In fact, this is data that could enable us to take a more realistic approach to data augmentation. The game is based on moving from one article to another via hyperlinks. So whatever idea the player has in mind, they will inevitably be limited by the presence or absence of hyperlinks on a given article. 
To do this, we compared the number of hyperlinks between our fairy tale article and the articles in question. However, if we proceed in this way, we could penalize articles that are 'short' or do not include many hyperlinks. That's why we've decided to normalize the number of links: instead of using a whole number, we're working with the percentage of an article's links (in relation to its total number of hyperlinks) that are linked to our flagship article. 

<<<<<<< HEAD
<iframe src="assets/plot/random_common_links.html" width="750px" height="200px" frameborder="0" position="relative">Top 50 visited articles</iframe></li>
</ol>
=======
<iframe src="assets/plot/random_common_links.html" width="750px" height="250px" frameborder="0" position="relative">Top 50 visited articles</iframe>
>>>>>>> 036d406abbc1c926cbcecaf6515e39fa7cbfaf67

… Right then, time for tea ! 

<p align="center">
  <img src="assets/img/tea.gif" width="500" title="Tea">
</p>