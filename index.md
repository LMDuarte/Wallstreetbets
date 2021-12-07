# Introduction

In recent years, social media has continued to show the transformative and destructive power it has. Platforms such as Twitter, Facebook, and Reddit have allowed people to unionize and impact major institutions. From its effects on politics, public health, and the stock market, social media platforms have shown to be powerful “tools”.

Among all these “tools” Reddit differs with their enfaces in community. Their subreddit feature allows people to collaborate with others in very specific ways. There is a common belief that you could find a subreddit for any kind of community. For this particular analysis, the community or subreddit of interest is r/wallstreetbets.

Wallstreetbets is a subreddit where people discuss anything related to the stock market with an enfaces on high-risk trades. People share their portfolios, predictions, gains, and losses. The emphasis on wallstreetbets is mainly due to its role in the sudden price change of Game Stop stock (GME). Earlier this year, active users in r/wallstreetbets performed a coordinated purchase of undervalued stocks [2,4,6]. Game Stop stock (GME) received a particular interest among these Reddit users, which caused its stock price to skyrocket in less than a couple of days.

At the beginning of the year, when the price of GME reached its peak, there were a lot of questions surrounding wallstreetbets. Many questioned the legality of the users' tactics, some wondered if the internet would change the stock market's operation, and others were curious about the individuals posting on wallstreetbets. For this analysis, I would attempt to clarify the events surrounding the spike in price. I will explore the sentiment and use of language of reddit users, as well as the effect social media sentiment has on the price of Game Stop stock.

# Methods
## Variables

### Game Stop
Game Stop is a Delaware corporation established in 1996 specializing in entertainment products such as video games or video game merchandise. According to their 2020 annual report, they have 4,816 Game Stop stores across the United States, Canada, Australia, and Europe. They have additional stores, 73, operating under the name Zing Pop for international markets and ThinkGeek for the United States [3].

Game Stop as a company has been on the decline for a few years. Their net sales have decreased from $8,285.3 million in 2018 to $5,089 million in 2020. They have also reported a net loss of 215.3 million dollars as of 2020 [3]. However, despite their decline in sales, some customers may still have some fondness for the company. Perhaps this fondness could have been why subreddit users targeted Game Stop stock.

### Wallstreetbets
The wallstreetbets subreddit was created on January 31st, 2012, and currently has 11.3 million users. According to the wallstreetbets moderators," [the subreddit] is a community for making money and being amused while doing it [7]." Members of this community are traders who implement a risky strategy based on little evidence. Hence their approach resembles more gambling than traditional investment. It could be said that the events surrounding GME started mainly as another form of speculative gambling. However, the organization and targeting by a large portion of the community may have resulted in the spike.

### Sentiment Analysis
Public sentiment has been shown to affect the price of cryptocurrency; therefore, it stands to reason that the same could be possible with stock prices [9]. Using multiple analysis methods such as VADER, afinn, and bing lexicon, we analyzed the sentiment expressed by Reddit users across time.

VADER (Valance Aware Dictionary and sEntiment Reasoner) is a lexicon and rule base tool designed to analyze text posted on social media. In contrast to other methods VADER is design to recognize language commonly used in social media as well as analyze the whole post at once. VADER is attuned to the intensity often found in social media, by recognizing emoticons, abbreviations, and slang. This tool also considers the placements of words in sentences and the degree in which it modifies a sentence. A sentence such as "the service is extremely good" and "the service is good" would receive a different positive score based on the words modifying the sentence’s intensity. After performing the analysis each posts receives a compound score between -1 and 1 [5].

Additionally to VADER, I utilize the bing & afinn lexicons. The "bing" lexicon labels words as either positive or negative. Bing can be helpful to get a broad picture of the overall vocabulary used by Reddit users. However, it is not suited to graph sentiment across time, and a second 4
lexicon, afinn, was needed to get a more in-depth look into the average sentiment expressed between 2019 and 2021. With the afinn lexicon assigning a score between -5 to +5 to words used in the posts it was possible to get a more in depth look into the average sentiment expressed by members of wallstreetbets.

## Data Collection

### Posts
For this analysis, I needed to find a method that would allow me to extract Reddit data from a specific window of time. Common data extraction methods, both in R and python, only collected the most recent posts under a subreddit. It used to be possible to extract Reddit data through python using PRAW (Python Reddit API Wrapper). However, recent changes made by Reddit have disrupted PRAW's ability to extract specific data. A solution to PRAW's limitation came from pushift.io Reddit API [1]. Pushift.io was designed and created by the r/datasets subreddit to enhance search capabilities for Reddit's posts and comments.

Using upshift.io, I extracted posts from r/walstreetbets mentioning GME between January 2019 and January 31st, 2020. In that timeframe, there was a total of 73,786 posts mentioning GME. In 2019 there were 105 posts, 2020 had 1,274 posts, and January 2021 had 73,786 posts. There was a large amount of data, and the code could only extract around 1,000 posts; therefore, I needed to run the code 22 times.

### Stock Data
In addition to Reddit posts, I needed to extract the price of Game Stop stock from January 2019 to January 2020. Using R, I extracted and visualized the stock price across time. The visualization of the stock price will serve to contextualize the rest of the analysis.

# Results

## Scale
When looking at the data I have decided to separate it based on the year. Due to the drastic increase in price that GME saw at the beginning of 2021, any visualization or analysis would not accurately reflect the events of 2019 and 2020, if it also included data from January 2021.

## Price
Looking at the price of Game Stop stock by year, we can see a steady decline in price, followed by dramatic increase at the beginning of 2021. At the beginning of 2019 the Game Stop stock price was valued at $15.24, however it saw a steady decrease culminating in a price of $5.88. The price then saw an organic growth during the year resulting in a price of $18.84. However, on January 29th 2021, the stock price for game stop saw a sudden spike resulting in a stock price of $325.00.

![image](https://user-images.githubusercontent.com/69866550/145123537-f0c5c161-fd23-457c-b886-e05c64a1a1ab.png)

```markdown
Figure 1: Price of GME as of January 31, 2021
```
## GME Mentions
Game Stop stock has been a topic of conversation in the subreddit r/wallstreetbets all the way back to 2019. However, the number of mentions in 2019 to 2020 have been minimal compared to the number of mentions in 2021. Back in 2019 the highest number of monthly posts discussing “GME” were around 20, it is still notable that people had some interest in the status of GME back then. It is not until the end of 2020 that we see an increase in GME mentions. On November 2020 there were a total of 573 posts mentioning GME. Later on we see a dramatic increase at the beginning of 2021. In total there were 73,786 posts mentioning GME on January 2021. The majority of these comments were posted on January 28th (a day before the price spike) with 22,502 posts. 

![image](https://user-images.githubusercontent.com/69866550/145123665-683a9bd8-02f9-46f9-b5e9-416f9fa45211.png)
```markdown
Figure 2: Number of comments mentioning GME: 2019-2021
```

![image](https://user-images.githubusercontent.com/69866550/145123708-443d3e39-a3c6-414e-aebd-82c4db5b2ee5.png)
```markdown
Figure 3: Number of comments mentioning GME: January 2021
```
## Sentiment Analysis
For the sentiment analysis I utilize three different tools; VADER, Bing lexicon, and Afinn lexicon. Both the afinn lexicon and VADER were used to graph the users sentiment towards GME across time. While the Bing lexicon allowed me to separate the most negative and positive words used by the commentors.

### Top Woeds
When looking at the users vocabulary my goal was to identify if the way users spoke about GME changed across the years. However, what my visualization ends up showcasing is the users general vocabulary. I do want to be upfront and explain that the language used by the commentors is fairly inappropriate. However, I believe it should be mention and included in this report, since it can be used to understand the kind of people discussing GME. In 2019 the vocabulary was fairly concentrated on terms related to the stock price. Words like “death” and “fail” are used by the commentors to describe the status of GME at the time. Moving up to 2020 we see that the top negative words used are “retards” and “fucking”, both immature and aggressive language. The type of language used does not change for 2021. The data shows that the top two words used in January of 2021 is “fucking” and “fuck”. Instead of reflecting their opinion towards GME it showcases the juvenile and carefree attitude of the users.  

![image](https://user-images.githubusercontent.com/69866550/145123846-b82a3ce4-94bc-4471-b547-5b2a15a8fade.png)
![image](https://user-images.githubusercontent.com/69866550/145123855-ca8231cd-6e22-43a5-a7bd-52ff3dacfe57.png)
![image](https://user-images.githubusercontent.com/69866550/145123859-7da5a2b1-7a2c-4b8b-91fc-f23afe3400d6.png)

### Sentiment over time
Using VADER and the afinn lexicon I was able to graph users’ sentiment towards GME across the years. Performing the analysis with VADER shows us that from 2019 to the end of 2020 the average sentiment towards GME was fairly positive. To put things into context , VADER assigns a score between -1 to 1, and our data shows that between 2019 and the end of 2020 the scores ranged from -0.056 to 0.712. Another thing to note is the two spikes that occurred on October 2019 (0.712000000) and August 2020 (0.245909091). 

![image](https://user-images.githubusercontent.com/69866550/145123984-bd0ef4cb-2d89-46c4-b28c-1ce9ca512f77.png)

```markdown
Figure 7: VADER sentiment 2019 -2020
```
Despite the positive tone found in the comments before 2021, the comments from January 2021 display a different sentiment. When looking at the average sentiment scores you can see that they are barely positive. The posts have a more neutral sentiment with their scores ranging from -0.026 to 0.019. 

![image](https://user-images.githubusercontent.com/69866550/145124043-d76801d5-4122-4338-917e-0ce3fd2f9886.png)

```markdown
Figure 8: VADER sentiment January 2021
```
I utilized the Afinn lexicon and VADER as a form of redundancy. When measuring the data from 2019 and 2020 using the Afinn lexicon, we can see similar patterns as the sentiment displayed with VADER. The data is mostly positive, with some negative spikes. The Afinn lexicon assigns a score between -5 and 5, and the 2019 and 2020 data has scores ranging from -1.85  to 2.00. We see a score of 2.00 in multiple dates; April 2019, October 2019, July 2020 & August 2020. In contrast, we see a score of -1.85 on September 2019.

![image](https://user-images.githubusercontent.com/69866550/145124121-e237f004-01dd-452a-bdd1-b57d2300557b.png)

```markdown
Figure 9: Afinn sentiment 2019 - 2021
```
Using the Afinn lexicon, it is apparent that the sentiment from January 2021 is neutral. Compared to the 2019 and 2020 data, the sentiment displayed at the beginning of 2021 has an average score of 0.002. The data shows a positive spike on January 9th 2021 with a score of 1.067 and a negative spike on January 28th 2021 with a score of -0.225.  

![image](https://user-images.githubusercontent.com/69866550/145124179-060d5d05-f5cc-4397-8c40-ce03745222bb.png)
```markdown
Figure 10: Afinn sentiment January 2021
```
# Discussion
## Price and Mentions
When looking at the number of mentions and the price of GME, we can see that the two mirror each other. When graphing the two side by side, we see that both the price and mentions increase at a similar rate. As soon as we graph the 2020 data, we start to observe similar spikes between the two graphs. Both the price of GME and the number of mentions in r/wallstreetbets see a spike after August 2020. Now, the most important comparison comes 







