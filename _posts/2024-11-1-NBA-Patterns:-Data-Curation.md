---
layout: post
title:  "NBA Patterns: Data Exploration From a New Lense"
description: Has the NBA been getting better at Basketball or just getting our money?
image: /assets/img/post2header.png
---

## Introduction

The National Basketball Association (NBA) has grown into one of the world’s wealthiest sports leagues, boasting a net worth of over [$120 billion](https://www.statista.com/statistics/193696/franchise-value-of-national-basketball-association-teams-in-2010/) and experiencing remarkable expansion over the last two decades. This growth is not just a result of outstanding athletic performances and innovative coaching; it’s driven by strategic business management, compelling marketing, and strong fan engagement.

Yet, the NBA has also faced unprecedented challenges. The COVID-19 pandemic halted games, limited audience attendance, and impacted revenue streams, casting uncertainty over the league’s future. Now, as the NBA adapts, we have the opportunity to dig into data and explore how gameplay itself has evolved.

## This analysis seeks to answer two key questions:

1. Does the NBA show consistent patterns in points scored across seasons?
2. Has the variation in points scored by teams fluctuated significantly over the past four years?

By examining these trends, we can gain new insights into whether the NBA has changed in how the game is played or if these patterns reveal something deeper about the league’s appeal and its strategies for keeping fans engaged.

## Data 

The data for this NBA analysis was obtained from apilayer.com at [the rundown api](https://apilayer.com/marketplace/therundown-api). Because this api is free and open to the public access as you register an api key, it is ethical to use and implements good practice of not extracting information that is private or restricted. It is important to follow ethical scraping and data curation procedures to ensure the legality of such data exploration but as well to be an honest web user.

As in any other data analysis, one of the first steps after identifying a motivating question is to obtain reasonable data to further explore the topic.  The rundown api contains data from several hundred sports and thousands of games. I used this api to obtain the data set for this analysis. 

I like using api's because they allow you to obtain lots of information quickly. The website [apilayer.com](https://apilayer.com/) is a great place for anyone to start! It's relatively simple:
1. Choose an api to work with
2. Obtain an api key (remember not to share it! Even on github)
3. Query your desired data by reading documentation and following relavent examples.

For this project to explore patterns across seasons and see how points have been effected over the past several years, I decided to obtain data from individual games from the NBA. I obtained an api key and decided to select preseason, regular season, post season, and playoff games to be included in the analysis. I included the date, type of game, home team name, away team name, home team score, away team score, location, and several other variables to be included for further exploration. This was all done on the apilayer website as it allows you to demo the request for each url. Hit the live demo button on this website and you can get whatever data you need from the api.

As I did this, I noticed that the api only allowed 500 games per query. So I created a loop that would add additional games to the data query. In following ethical practices, I had the loop sleep for 5 seconds per iteration as to not overwelm the website. Doing this, I obtained a final sample size of 5,500 games ranging from 2021 to 2024. You can do this for any api and to follow along with my code go to my [githup repo](https://github.com/dsumsio/Data-Curation-Project).

## Analysis of NBA Scoring Trends
In addressing the questions of scoring consistency and fluctuation over recent NBA seasons, these plots reveal several trends about the dynamics of team performance and the league as a whole.

![post2plot1.png]({{site.url}}/{{site.baseurl}}/assets/img/post2plot1.png)

#### Patterns Across Seasons
In this first plot, which tracks home and away team scores over time, the gradual rise in the average scores (as shown by the red and purple trend lines for home and away scores, respectively) suggests a consistent increase in offensive scoring across seasons. This steady climb, from an average of 107.6 to 114.5 points per game, could indicate several factors at play:

1. Increased Offensive Efficiency: Teams may be becoming better at optimizing their offensive strategies, with players improving in areas like three-point shooting, ball movement, and transition play. This shift aligns with the recent emphasis on analytics in basketball, which prioritize high-value shots and [efficient scoring](https://jonashonick.com/how-analytics-is-revolutionizing-modern-basketball/#:~:text=Teams%20are%20increasingly%20relying%20on,most%20efficient%20ways%20to%20score.) which could be pursued in another analysis.

2. Player Skill Development: Today's players are entering the NBA with higher skill levels, especially in shooting and playmaking, leading to increased scoring. This could be due to better training programs at the youth and collegiate levels, combined with an increase in international talent increasing teams scoring abilities.

3. Team Familiarity and Cohesion: The upward trend in points as each season progresses could suggest that teams become more cohesive and effective as they spend more time playing together, which could explain the higher scores later in the season.

![post2plot2.png]({{site.url}}/{{site.baseurl}}/assets/img/post2plot2.png)

#### Fluctuations and Scoring Variation Among Teams
In the second plot, showing each team’s average points per season, the upward-sloping trend lines across almost all teams show the league-wide scoring increase. However, the variation among teams' scores also provides valuable insights:

1. Competitive Balance and Scoring Distribution: While the average score across teams is rising, the variability in team performance indicates that some teams are improving offensively faster than others. The standard deviation for teams ranges from 13.59 to 22.04 points. This disparity could be attributed to differences in team composition, coaching philosophies, and resource allocation for player development. 

2. Emergence of High-Paced Playstyles: Teams with the steepest upward slopes could be adopting faster-paced playstyles, prioritizing quick scoring opportunities. Such strategies could help explain why teams purposely lack dominant defensive players and instead have several skilled shooters.

## Implications for the NBA and Future Seasons
The consistent rise in scoring implies that the NBA is evolving toward a fast paced and potentially offensively focused game. This shift has implications for fan engagement, as higher-scoring games are typically more exciting and can attract more viewers. However, this trend could eventually face limitations if defensive strategies begin adapting effectively or if rule adjustments are made to balance the game. 

Monitoring this scoring trend in future seasons and analyses could reveal whether the current upward trajectory will plateau or whether the points scored per game will continue to increase. Leave a comment below! Which one do you think will be the case? 



#### Additional resources

Here are some additional articles to read about how [defense is declining in the NBA](https://www.theguardian.com/sport/2023/feb/03/nba-offensive-revolution-scoring-defense) as well as how [individual players points](https://www.nba.com/stats/leaders) stack up in the NBA.

#### Github Repo

Follow this link to my [github repo](https://github.com/dsumsio/Data-Curation-Project) to see code and additional analysis of this NBA dataset.

