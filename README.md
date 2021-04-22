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
