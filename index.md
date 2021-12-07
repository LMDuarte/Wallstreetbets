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
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```
