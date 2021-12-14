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
Is the 'Alternative for Germany' similar to 'Lega Nord'?
in this project we will take a short journey through the different political topics. For this purpose, we will focus on the larger EU member states France, Germany, Spain, Italy and Poland.  

The main goal is to examine how much the political scenario in one topic changes from one of these countries to another. Taking into account the quotes and the party of politicians, we will discover the hottest topics in each country and compare them to the ones of other countries.

Besides, we will investigate how politicians from different countries position themselves over the same topics, especially if they come from the same political background (i.e. right parties, left parties), by analyzing the similarities and the differences.

## Research questions
1. How much does the political scenario in some hot topics (migration, climate change, EU, gender discrimination, drug legalization, russian politician) change from one country to another? Why is that?
2. Considering rigth-hand parties (AfD(Germany), Lega Nord(Italy), Front National(France), PiS(Poland)), how much do their opinions differ compared to a party with similar political orientation from another country?
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

## Topic selection
We decided to examine the situation of each country in the following topics: 
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

### European Union and Brexit  
This time we will start our analysis from the most popular speakers:  
![Top Speakers Brexit](/assets/img/Project_graphics/Brexit_Top_Speakers.png)  

We can see, indeed, that there are eminent European politicians:
- Donald Tusk (President of the European Council from 2014 to 2019)
- Michel Barnier (Former European Commissioner for Cohesion and Reforms)
- Pierre Moscovici (Former European Commissioner for Economic and Financial Affairs, Taxation and Customs).
- Ursula von der Leyen (President of the European Commission)  

How was the distribution of the number of quotes per country?:  

![Top Speakers Brexit](/assets/img/Brexit_Distribution_per_country.png)  

As we will see, the peaks correspond to important events of Brexit, the withdrawal of the United Kingdom from the European Union.

#### <center>March 2017</center>
<center><img src='https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Prime_Minister%E2%80%99s_letter_to_Donald_Tusk_triggering_Article_50.pdf/page1-390px-Prime_Minister%E2%80%99s_letter_to_Donald_Tusk_triggering_Article_50.pdf.jpg' width=300></center>

On 29 March 2017, the United Kingdom invoked Article 50 of the Treaty on European Union which began the member state's withdrawal from the European Union.

In compliance with the TEU, the UK gave formal notice to the European Council of its intention to withdraw from the EU to allow withdrawal negotiations to begin.

#### <center>March 2019</center>

The UK had long been expected to leave the European Union at 11pm on 29 March 2019.  However, following a House of Commons vote on 14 March 2019, the Government sought permission from the EU to extend Article 50 and agree a later Brexit date.

On 20 March 2019 the Prime Minister, Theresa May, wrote to European Council President Donald Tusk, asking to extend Article 50 until 30 June 2019.

#### <center>October 2019</center>
In the run-up to the scheduled date for the UK’s departure at Halloween, Boris Johnson’s government finally sealed a new exit deal with the EU – but a missed deadline in the British parliament forced the prime minister by law to seek another Brexit delay.

European leaders agreed to the request for a three-month extension, while UK lawmakers finally agreed to an early general election in December to try to clear the path ahead.

### Discrimination
![Top Speakers Brexit](/assets/img/Project_graphics/Discrimination_Distribution_percounry.png)  

First, we can observe a huge peak in January 2015, corresponding to the only peak in France.
In addition, there are a few more peaks, more accentuated in the countries distributions.

#### <center>January 2015</center>
The most important peak is linked to the Islamic terrorism attacks of the same month in France.

It is also an important event for discriminations. The former President of France, Hollande, affirmed that radical Islam had fed off contradictions, poverty, inequality and conflict, and that "it is Muslims who are the first victims of fanaticism, fundamentalism and intolerance".

He also added that "French Muslims have the same rights as all other French [...]. We have the obligation to protect them. [...] Anti-Muslim and anti-Semitic acts have to be condemned and punished."

#### <center>July 2016</center>
As in the last case, the peak is mainly because of Donald Tusk's statements on Nice terrorism attack. In fact, he affirmed that the "subjects of the attack were people celebrating liberty, equality and fraternity".

#### <center>March 2017</center>
This peak can be linked to the third top speaker: <a href='https://en.wikipedia.org/wiki/Thomas_Bach'>Thomas Bach</a>, President of the International Olympic Committee.
In fact, the International Olympic Committee (IOC) Executive Board on this day approved a major review project regarding gender equality in the Olympic Movement.

#### <center>October 2017</center>
This time the main term is "liberty". In fact, in October 2017, the <b>Catalan independence referendum</b> took place.

#### <center>February 2018</center>
On 3 February 2018, in the city of Macerata, Marche, 28-year-old local Luca Traini seriously wounded, in a drive-by shooting, six African migrants.
After the attack, <b>Traini</b> reportedly had an Italian flag draped on his shoulders and raised his arm in a Fascist salute.

Traini said the attack was revenge for the murder of Pamela Mastropietro, an 18-year-old local girl whose dismembered body had been found a few days earlier, stuffed into two suitcases and dumped in the countryside. For this, a 29-year-old Nigerian national and failed asylum seeker, Innocent Oseghale, had been arrested and charged.

#### <center>April 2018</center>
On 17 April 2018, <b>Adam Armoush</b>, a 21-year-old Israeli Arab living in Berlin and his German friend of Moroccan origin went through a street in Prenzlauer Berg taking selfies while wearing kippahs.

At one point, an argument with three Arab-speaking young men started, which was followed by a violent attack. Armoush managed to document the violence with his cell phone and later allowed the video to be shared on Facebook, from where the video went viral.

The video shows the main attacker beat Armoush repeatedly with his belt. During the onslaught, the attacker shouted the word "Yahudi", the Arabic word for Jew, before one his companions intervened and dragged him away.

References:
- <a href='https://www.bbc.com/news/world-europe-30829733'>France to protect all religions, vows Francois Hollande</a>
- <a href='https://olympics.com/ioc/news/ioc-launches-bold-initiative-on-gender-equality'>IOC launches bold initiative on gender equality</a>
- <a href='https://en.wikipedia.org/wiki/Macerata_shooting'>Macerata shooting</a>
- <a href='https://en.wikipedia.org/wiki/2018_Berlin_anti-semitic_attack'>2018 Berlin anti-semitic attack</a>

### Israeli - Palestinian conflict


### Climate change


### Russia


### Coronavirus
