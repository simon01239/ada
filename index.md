---
layout: home
title: How much does the political scenario change from one country to another?
subtitle: A brief tour of Europe's parties
---
## Index:
[Abstract](#Abstract)

## Abstract
Europe, 2019.  
It appears that right-wing populists are on the rise in many countries. But can you really compare these parties between countries? What do they have in common? How do they differ?
What is the general political orientation on controversial themes in different countries and what is the position of the leading politicians on these themes?
Is the 'Alternative for Germany' really similar to 'Lega Nord'?
In this project we want to address these and other questions related to political topics. We take a deeper look for the European countries France, Germany, Spain, Italy and Poland.

The main goal is to examine how much the political scenario in one topic changes from one of these countries to another. Taking into account the quotes and the party of politicians, we will discover the hottest topics in each country and compare them to the ones of other countries.

Besides, we will investigate how politicians from different countries position themselves over the same topics, especially if they come from the same political background (i.e. right parties, left parties), by analyzing the similarities and the differences.

## Research questions
1. How much does the political scenario in some hot topics (migration, climate change, EU, gender discrimination, drug legalization, russian politician) change from one country to another? Why is that?
2. Considering rigth-hand parties (AfD(Germany), Lega Nord(Italy), Front National(France), PiS(Poland), UKIP(UK)), how much do their opinions differ compared to a party with similar political orientation from another country?
3. How do the important politicans of these parties positioning themselves over topics (migration, climate change, EU, gender discrimination, drug legalization, russian politician)?


## Methods
For research question 1: Find a way to get the quotes of migration, climate change, EU, gender discrimination, drug legalization, russian politician of Germany, Italy, France, Poland and UK. Examine the distribution of these topics in the countries and over time.

For research question 2: For each topic we do the plots of the sentiment analysis and highlight quotes from different parties with different colours. Then for each topic we can create a boxplot showing the sentiment analysis distribution per country.

For research question 3: Compute for each politican and for each topic the average sentiment and compare them. Find the politicans who are more similar.

In order to answer the research questions we plan to implement pipeline as follows:

    Extract suitable subsets from the quote dataset
    Embed the quotes as vectors
    Extract the topics covered by the quotes
    Use sentiment analysis on the quotes to get the „opinion direction“ expressed about the topic.

Embedding: we currently use Doc2Vec, which learns a joint embedding encoding both the semantic of the words as well as their order in the document. Although we might switch to another pretrained embedding model, like Word2Vec, that we already implemented. In particular, for Word2Vec, with gensim we load a pre-trained Word2Vec model. Then, we pre-process each quote and we average all the words with their TF-IDF score.

Topic Extraction: We follow the approach of Top2Vec. So we use UMAP for dimensionality reduction of the embedding vectors and HDBSCAN for the final clustering.

Sentiment Analysis: we use TextBlob to extract the polarity and subjectivity of quotes.

## heading
We decided to examine the situation in the countries in the following topics: 
- Immigration
- European Union and Brexit
- Discriminations (racism, based on gender, homophobia)
- Israeli-Palestinian conflict
- Russia and Putin
- Terrorism
- COVID-19

### Immigration
![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_time_allcountries.png)
![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_time_percountry.png)
![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_political alignments.png)
![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_political alignments_percountry.png)

