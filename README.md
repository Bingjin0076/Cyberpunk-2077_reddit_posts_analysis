# Cyberpunk-2077_reddit_posts_analysis
We explore the reddit posts data from 2020/8/21 to 2021/2/14, find the topics of these posts and analyze the sentiments of these posts.


## Backgroud:
Cyberpunk 2077 is a RPG developed by CD Projekt ([wikipedia link](https://en.wikipedia.org/wiki/Cyberpunk_2077)). Because of the great success of this company's last RPG: the Witcher3: Wild Hunt, Cyberpunk 2077 was highly anticipated before it release. The company has delayed game release three times, finally to 2020/12/10. But the launch was distraunous because the game suffered from numerous bugs and bad performances. Later the company suspended the distribution of this game on playstation 4 platform. An official apology and a commitment to quality was announced on 2021/01/13. And several fixes and patches were released intermittently.

## Data:
The data set is collected by Matheus de Albuquerque, a Kaggle user. Here is the [link](https://www.kaggle.com/matheusdalbuquerque/rcyberpunkgame-posts)to the data.
Details about the data:
The data consist of reddit posts collected from 2020/08/21 to 2021/02/14 related to the video game: Cyberpunk 2077. The data set are two csv files, one consists of posts, another is a collection of comments. These two files can be found at *data* folder.

## Project goal:
We first group these posts according to their topics, and we would like to know the sentiment reddit users had to CD Projeck and to this game, and we would like to study the sentiment change along time. From the analysis, we can figure out which part of the game did not come up to people's expectations.

## Methods:
For topic modeling, we compare LDA model with the model with NMF (non-negative matrix factorization) applied to tfifd matrix. For details, check *topic_exploration.ipynb* in *exploration* folder.
For sentiment analysis, we use SentimentIntensityAnalyzer in nltk package to rate each comment a sentiment score from -1 to 1, then compute the sentiment for a post using 'up_votes' as weights. For details, check *sentiment_exploration.ipynb* in *exploration* folder.
For the trends, we visualize the trends of many features from 2020/08/21 to 2021/02/14, for example, the number of reddit posts related to a particular topic, the sentiment score of a topic. For details, check *trends.ipynb* in *exploration* folder.

## Conclusion:
There 2 big topics of the posts: about the CD projekt and the news from the company, the second topic is about the game cyberpunk.
The first topic has many sub topics: 
- the news of about the game, the delay, the bugs and people's views on these news
- the release news of the game, release information on different platforms
- the hardware requirement of the game and the advanced picture technology the game is using

The second topic contains some sub topics:
- the romance elements of the game
- the violent elements of the game, guns, fighting
- the cars, racing, motorbikes 
- the stories, quests of the game
- the costume of characters in the game, also various cosplays inspired by characters from the game

The overall sentiment of all topics are positive. The highest ones are the release of the games on various platform, the costums of characters plus cosplays and the hardware requirements. The topics with lowest sentiment scores are the racing and fighting elements of the gameplay.
There is a steady increase of sentiment for the game since various videos about it were posted on youtube channel. The sentiment reached its peak at the release date, then suffered from a significant drop due to numuour bugs. After the launch of the orginal game, one official apology from CD projekt and several fixes are released. Each such release brought some sentiment increase. 
More details can be found in the *trends.ipynb* in *exploration* folder.

From the data analysis, people would be more happy about the game if there would not be so many bugs in the game, and if the gap bwt expectation and the real game.


## Future work:
1. Collect the stock price data of CD projekt, compapre the trends of stock price and the sentiment from the posts and check the corelations.
2. Collest reviews from various gaming platforms to get more precise information regarding to game experiences. Also collect recent reviews (because of fewer bugs) to get ratings to the game itself. 
