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
Let's take a look into one of the most controvers discussed topic in the European countries, the immigration topic. How did it develop over time?

![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_time_allcountries.png)

First, you may have noticed that on average there are fewer citations in the colder months. The reason for this is that migrants prefer to take advantage of better weather and therefore their number rises in warmer months.
Second, you can see 2 clear peaks. It seems that immigration made headlines in September 2015 and June 2018. What happened in these months? To get an answer to this question, let's look at the distribution w.r.t each country. 
The peaks distinguish quite a lot in each country:

![Topic Distribution over all countries](/assets/img/Project_graphics/Immigration_Distribution_over_time_percountry.png)


##### <center>September 2015</center>  

Let's start with the situation in **2015**. Do you remember the refugee routes?  
In 2015, the main route shifted from the dangerous Mediterranean, crossing from Libya to Italy, to another one crossing from Turkey to Greek islands like Lesvos, what would prove to be even deadlier.
This explains why the peak is completely absent in Italy's point of view and, in the other hand, is quite marked in Germany or Poland.
Over 75% of those arriving in Europe had fled conflict and persecution in Syria, Afghanistan or Iraq.

The peak on this month can be sadly explained by a drammatic event that took place on 2 September 2015.
On this day, <a href='https://en.wikipedia.org/wiki/Death_of_Alan_Kurdi'>Alan Kurdi</a>, a three-years-old Syrian boy, lost his life trying to reach Europe from Turkey.
The photo of his body laying on a beach in Turkey moved millions worldwide.

By the time Aylan's body washed ashore, more than 300,000 people had risked their lives to reach Europe. Over 2,600 had perished in the attempt.

##### <center>June 2018 and Matteo Salvini</center>  

<center><img src="https://ichef.bbci.co.uk/news/976/cpsprodpb/0260/production/_102080600_migrant_ship_with_spain_640_v4-nc.png" width=600></center>  

At first glance, the peak in **June 2018** is clearly caused by Italy and, most likely, by the most popular speaker in the immigration topic, Matteo Salvini. However, this huge crest could be quite weird by just looking at <a href='https://www.youtrend.it/2021/02/15/sbarchi-e-immigrazione-in-italia-il-punto-della-situazione/'>data.</a> The number of migrants in 2018 is quite low if compared to the figures of the previous years.

However, something happened in Italian politics during these days. Indeed, <a href='https://en.wikipedia.org/wiki/Matteo_Salvini'>Matteo Salvini</a>, leader of the far-right party "Lega Nord", was sworn in as Deputy Prime Minister and Minister of the Interior on 1 June 2018. He immediately stated that his main aim was to drastically reduce the number of illegal immigrants to Italy.  

On 10 June 2018, **Salvini**, who is also the person with the most quotes in immigration (see plot below), announced the closure of Italian ports. The vessel <b>Aquarius</b>, which carried more than 600 migrants, was refused a port of disembarkation by the Italian authorities. It was accepted by Spanish authorities, and it finally arrived at the Port of Valencia on 17 June 2018.  

![Top Speakers](/assets/img/Project_graphics/Immigration_Top_Speakers.png)  


