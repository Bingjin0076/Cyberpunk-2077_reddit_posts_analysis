
# Cyberpunk-2077_reddit_posts_analysis
We explore the Reddit posts data from 2020/8/21 to 2021/2/14, find the topics of these posts and analyze the sentiments of these posts.


## Backgroud:
Cyberpunk 2077 is an RPG developed by CD Projekt ([wikipedia link](https://en.wikipedia.org/wiki/Cyberpunk_2077)). Because of the great success of this company's last RPG: the Witcher3: Wild Hunt, Cyberpunk 2077 was highly anticipated before its release. The company has delayed game release three times, finally to 2020/12/10. But the launch was disastrous because the game suffered from numerous bugs and bad performances. Later the company suspended the distribution of this game on PlayStation 4 platform. An official apology and a commitment to quality were announced on 2021/01/13. And several fixes and patches were released intermittently.

## Data:
The data set is collected by Matheus de Albuquerque, a Kaggle user. Here is the [link](https://www.kaggle.com/matheusdalbuquerque/rcyberpunkgame-posts)to the data.
Details about the data:
The data consist of Reddit posts collected from 2020/08/21 to 2021/02/14 related to the video game: Cyberpunk 2077. The data set is two CSV files, one consists of posts, another is a collection of comments. These two files can be found in *data* folder.

## Project goal:
We first group these posts according to their topics, and we find the sentiment Reddit users had to CD Projeck and this game, and observe the sentiment change over time. From the analysis, we can figure out which part of the game failed to come up to people's expectations.

## Methods:
For topic modeling, we compare the LDA model with the model with NMF (non-negative matrix factorization) applied to the tfifd matrix. For details, check *topic_exploration.ipynb* in *exploration* folder.
For sentiment analysis, we use SentimentIntensityAnalyzer in the nltk package to rate each comment a sentiment score from -1 to 1 (the higher the score is, the positive the altitude is), then compute the sentiment for a post using 'up_votes' as weights. For details, check *sentiment_exploration.ipynb* in *exploration* folder.
For the trends, we visualize the trends of many features from 2020/08/21 to 2021/02/14, for example, the number of Reddit posts related to a particular topic, the sentiment score of a topic. For details, check *trends.ipynb* in *exploration* folder.

## Conclusion:
There are two big topics of the posts: one is about the CD Projekt and the news from the company, the other topic is about the game cyberpunk itself.
The first topic has many sub-topics: 
- the news about the game, the delay, the bugs, and people's views on the news
- the release news of the game, release information on different platforms
- the hardware requirement of the game and the advanced picture technology the game is using

The second topic contains some sub-topics:
- the romance elements of the game
- the violent elements of the game, guns, fighting
- the cars, racing, motorbikes 
- the stories, quests of the game
- the costume of characters in the game, also various cosplays inspired by characters from the game

The overall sentiment of all topics is positive. The highest ones are the release of the games on various platforms, the costumes of characters plus cosplays, and the hardware requirements. The topics with the lowest sentiment scores are the racing and fighting elements of the gameplay, these two parts in the game are more prone to bugs.
There is a steady increase in sentiment for the game from 2020/11/19 since various related videos were posted on the Youtube channel. The sentiment reached its peak at the release date, then suffered from a significant drop due to numerous bugs. After the launch of the original game, one official apology from CD Projekt and several fixes were released. Each such release brought some sentiment increase. 
More details can be found in the *trends.ipynb* in *exploration* folder.

In conclusion, people would be happier about the game if there would not be so many bugs in the game, and if the gap between expectations before release and the real game.


## Future work:
1. Collect the stock price data of CD Projekt, compare the trends of stock price and the sentiment from the posts and check the correlations.
2. Collect recent reviews from various gaming platforms to get more precise information regarding game experiences, because these reviews are more likely from gamers who played this game. The company is consistently releasing patches and fixes, dissatisfaction with bugs plays a less important role in the sentiment of this game. 
