# Metacritic-Game-Reviews-Sentiment-Analyzer

## Introduction ---->

Launched in year 2001, Metacritic has emerged as the foremost online review website that aggregates user reviews of video games, movies and music albums. For every game on Metacritic, the scores from each review are averaged into a single score, a weighted average of all ratings posted by users with member access. Metacritic aims to help consumers make informed decisions about investing their time and money on game entertainment. So which genre influence video games to become popular? Can game reviews get classified based on their sentiments? Which games have the most positive reviews? Can we identify the most positive and negative reviews and form visual representations? So basically, our prime objective is to categorize user reviews based on their positivity and visualize the general trend of games relevant to customers.

## Project Flow ---->

![image](https://user-images.githubusercontent.com/57821332/115661127-004dd280-a30b-11eb-9a97-cb0f54ac8b1f.png)

## Project Steps ---->

Part 1 --> Web Scraping of Game Content and Game reviews
Part 2 --> Data Preprocessing (Removing lemmatization, lowercase, punctuation and stop words)
Part 3 --> Sentiment Analysis (Aspect Based/Rule Based)
Part 4 --> Visual Analysis (Graphs)
Part 5 --> Classification Algorithms (Decision tree, k-nearest neighbor, Random Forest)

## Data ---->

A. Data Source
We have built a web-scraper to scrape game data from Metacritic website using python Libraries; BeautifulSoup and Selenium Web driver.
Web Scraping Links:
1. Game Data:
https://www.metacritic.com/browse/games/score/metascore/all/all/filtered
2. User Review Data:
https://www.metacritic.com/game/{Platform}/{GameName}/user-reviews
We chose data from this source because it incorporated all the characteristics of a video game required to perform sentiment analysis and build predictive models.

B. Data Summary
1000 Games and 26 Genres
 --> Games: Grand Theft Auto 4, SoulCalibur, Tony Hawks Pro Skater 2 etc.
 --> Genres: Action, Adventure, Strategy, Sports, Fighting, Fantasy etc.
175 Developers and 20 Platforms
--> Developers: Rockstar Games, Nintendo, Activision, Blizzard Entertainment etc.
-->  Platforms: PC, PlayStation, Xbox 360, PSP, Dreamcast, Nintendo 64 etc.

7 ESRB Rating Categories
-->  E, T, M, E10+, K-A, AO etc.
84,000 Reviews and User Scores
--> Positive, Neutral, Negative based Score reviews and ratings
Game Metascores and Summary
--> Metascore: Weighted Average scores of critic's reviews. Range (1-100)
--> Summary: Brief Account of main points of the game.

C. Primary Data Variables
Variables necessary to perform Sentiment Analysis include:

Data Frame 1 (Game Data) Variables --> 1000 Observations, 9 Variables
Variable	Description
game_name	Name of the game
Platform	Platform on which game was launched
Release_Date	Date when game was released
Game_Summary	Brief Account of main points of the game
Meta_Score	Weighted Average of the single score by critics writing reviews
Developer	Developer of the game.
Genre	Separate category of games
No_Players	Total Number of Players for gameplay
Rating	ESRB (Environment Software Rating Board) rating for video game


C. Primary Data Variables
Variables necessary to perform Sentiment Analysis include:

Data Frame 1 (Game Data) Variables --> 1000 Observations, 9 Variables
game_name     -->	Name of the game
Platform	     --> Platform on which game was launched
Release_Date  -->	Date when game was released
Game_Summary	 --> Brief Account of main points of the game
Meta_Score	   --> Weighted Average of the single score by critics writing reviews
Developer	    --> Developer of the game.
Genre         --> Separate category of games
No_Players    -->	Total Number of Players for gameplay
Rating	       --> ESRB (Environment Software Rating Board) rating for video game


DataFrame 2 (User Review Data) Variables: 83991 observations, 5 Variables
game_name     --> Name of the game
Platform	    --> Platform on which game was launched
Review_Date	  --> Date when user posted review for the game
User_Review	  --> User Review of the game
User_Rating	  --> Rating posted by user for the game



Data Acquisition ---->
Web Scraping -->
This project sets out to pull data by building a web scraper and automate the process of extracting data from the web. Metacritic is one such website which gave us a foothold in the data acquisition process for scraping game data. For the project, we have scraped the top 1000 games with respect to their metascore and userscore rating. We have built a web scraper in such a way that it goes on to a webpage of the web, scrapes relevant game data and then moves forward with the next webpage. Further, we have scraped close to 84000 reviews posted by the users for each of the 1000 games.

A. Part 1 – Scraping Metacritic Game Elements/Game Links/User Review Links
In the part 1 of the scraping process, we have extracted a wide array of games and its elements using BeautifulSoup Library in python. Moreover, we also extracted game links and user review links for further scraping of inner html which comprises of reviews, ratings, and their review date.

![image](https://user-images.githubusercontent.com/57821332/115755092-f3f96200-a36a-11eb-80fe-15475d01187e.png)

![image](https://user-images.githubusercontent.com/57821332/115755161-0a072280-a36b-11eb-9c98-9b578883567e.png)


B. Part 2 – Scraping Metacritic Game Reviews
In the part 2 of the scraping process, we have extracted game user reviews and user ratings for the top 1000 games using Selenium web driver framework and phantomJS browser.

![image](https://user-images.githubusercontent.com/57821332/115755213-1d19f280-a36b-11eb-91e0-c289bf2a27e2.png)

## Sentiment Analysis -->
Sentimental Analysis is contextual mining of text to extract subjective information in a material to understand and predict public reviews or opinions. Our project implements two different sentiment analysis methods- 

Method-1 
Rule Based System

Rule-based system is one of the NLP methods, which uses a set of manually crafted rules. These rules are applied on the text corpus, i.e. the game reviews in our project. It counts the words in every review that reflect positivity and negativity based on pre-defined dictionaries. And later provides a polarity & subjectivity of each & every review.

DISTRIBUTION OF POLARITY ---->

![image](https://user-images.githubusercontent.com/57821332/115755357-420e6580-a36b-11eb-820a-2b5914aca094.png)

The above graph is normally distributed and symmetric. Which indicates that the top 1000 games reviews are more on the positive side. 

Method -2 

Aspect based Sentiment Analysis

![image](https://user-images.githubusercontent.com/57821332/115755500-69fdc900-a36b-11eb-9960-094bd167440c.png)

The Aspect Based Sentiment Analysis (ABSA) takes into consideration the terms related to the aspects and identifies the sentiment associated with each aspect. ABSA model requires aspect categories and its corresponding aspect terms to extract sentiment for each aspect from the text corpus, which is the reviews for the games in our project and determines if the identified aspect is positive or negative

## Aspect Sentiments ---->

![image](https://user-images.githubusercontent.com/57821332/115755612-869a0100-a36b-11eb-8b41-5682ce632f05.png)

The above figure reflects positive sentiments for aspects like “graphics”, “story” & “gameplay”. 

3# Word Cloud of positive user reviews  ---->
As word clouds are best way to analyze text and shows which words are the most frequent among the given text. We have used word cloud to show positive and negative user reviews of all the games. 

![image](https://user-images.githubusercontent.com/57821332/115755743-acbfa100-a36b-11eb-9528-b1400b312d28.png)

First, with the help of ruled based system we found out polarity of each word. Moreover, words with polarity > 0 are positive words. As you can see from the image above, some of the overused positive words with high polarity value are good, great, best, fun, perfect, etc. To make this look better we have masked the PNG of game controller under the word cloud. In addition, to make sure that mask works properly, we used it in numpy array form. 

## Word Cloud of Negative User Reviews ---->

![image](https://user-images.githubusercontent.com/57821332/115756351-1f308100-a36c-11eb-83d5-b95f4b5e7c5f.png)

Similar to the positive reviews word cloud, we have used the same approach to show negative words in word cloud, found polarity of each words with rule-based system approach. 
Words with polarity < 0 are negative words. As you can see from the image above, some of the overused positive words with less polarity value are bad, boring, terrible, never, etc.

## Visual Analysis ---->

A. Visual Representation 1
Top 10 positive games with respect to sentiment (Polarity) --> 
![image](https://user-images.githubusercontent.com/57821332/115756727-45562100-a36c-11eb-9d2c-70e794a575a0.png)

Insight --> Tony Hawk’s Pro Skater 2 has most positive reviews posted by users in terms of polarity. Sports Genre has the highest number of games with positive reviews.


B. Visual Representation 2
Top 10 positive game developers with respect to sentiment (Polarity) --> 
![image](https://user-images.githubusercontent.com/57821332/115757103-5b63e180-a36c-11eb-8540-b3f31d4164e3.png)

Insight --> Nintendo has developed the greatest number of games with positive reviews from users. 

C. Visual Representation 3
User Rating Distribution and Review Sentiment Distribution -->
![image](https://user-images.githubusercontent.com/57821332/115757382-6c145780-a36c-11eb-9ddf-9b9db6f919f2.png)

Insight --> Here we can observe that, difference in the number of positive reviews is minimal while comparing user rating and review sentiment distribution. Further, there is a slight increase in number of negative reviews for games. 


D. Visual Representation 4
Top 20 game genre with respect to sentiment (polarity) --> 
![image](https://user-images.githubusercontent.com/57821332/115757613-7a627380-a36c-11eb-8ed0-40b54975fbcb.png)

Insight --> Here, the bubble chart visualizes the top 20 genres in terms of polarity.


## Machine learning Models ---->
In our project we have used classification model to identify whether the given sentiment is positive or negative. 

Before training the model, we have created a new variable called Reviews Sentiment in our dataset. Based on polarity score we tried to label positive and negative sentiments. If the polarity score < 0 then we considered it as negative review and if the polarity score > 0 then we considered sentiment as positive review. Here, we used classification technique which is useful to classify the output. For that we applied 3 ML algorithms like Random Forest classifier, Decision Tree Classifier and KNN algorithm.

First, we took review columns in Dataset. Then we cleaned this text and converted this text into vector array using TF-IDF vectorizer which is used to transform text into a meaningful representation of numbers. Moreover, used to fit machine algorithm for prediction. 

After that we split our dataset using train test split function from Scikit learn. Here we used 80% data for training and 20% data for testing.


A.	Random Forest Classifier:
Large number of approximately uncorrelated models working as a committee will surpass any of the individual basic models.  

![image](https://user-images.githubusercontent.com/57821332/115758174-d4633900-a36c-11eb-9d2d-9ad1c2de0599.png)

Here we took,

n-estimator = 200 (it is a parameter that defines the number of trees in the random forest).

![image](https://user-images.githubusercontent.com/57821332/115758213-de853780-a36c-11eb-8ae2-ddbbea068c6e.png)


C.	K-nearest Neighbor:

The k-nearest-neighbors algorithm is useful to find the ‘sameness’. The algorithm takes labelled points and uses them to learn how to label other points. 

![image](https://user-images.githubusercontent.com/57821332/115758248-e8a73600-a36c-11eb-8020-3afa80ccc819.png)

For Nearest Neighbor we got testing accuracy of 33.38%

## Results ---->
Findings --> 
Our findings signify that while comparing user rating and review sentiment distribution, difference in the number of positive reviews is minimal in user rating. In addition, there is slight increase in number of negative reviews for the games. 

Proposed Prediction Method -->
After running the different machine learning models like K- nearest neighbor, decision trees and random forest. We found out K-nearest Neighbor is best fit for predicting negative and positive sentiments of user reviews.

## Conclusion ---->
•	Implementing BeautifulSoup and Selenium simultaneously, streamlines the process of web scraping for Metacritic.com.  
•	Based on the Sentiment Analysis of games reviews, it is evident that 95% of the games have positive reviews.
•	After performing Analysis of user reviews and building a predictive model, we achieved 84% accuracy with Random Forest classification algorithm.



