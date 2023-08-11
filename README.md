# Analyzing and Predicting Fantasy Football Scores 
## Introduction

Welcome to the repository for this data-science driven project to predict fantasy football scores in the upcoming season! This project aims to analyze and understand the factors that contribute to a player's success from a fantasy football perspective, while making actionable predictions to help a fantasy manager plan their draft better. 

As an avid NFL fan, and fantasy player, I've always been interested in tackling data within this context. And there is an abundance of data on this topic. 

## Yearly Predictions with Supervised Learning

One of the main goals of this project is to predict the fantasy football results for the upcoming season using data from previous years. As an avid player, I'm always wondering and thinking of ways to possibly improve my teams and strategies for each year.

## Data Sources

I've collected data from various sources, including:

    Kaggle datasets
    Websites like profootballreference.com and fantasyfootballcalculator.com (web-scraping via BeautifulSoup)
    Utilizing the nfl_data_py API to connect with nflfastR, nfldata, dynastyprocess, and Draft Scout

### Dataframes

As of 7/20/23, we have six main dataframes that serve various purposes:

    starter_df: Contains players ranked in the top 12 as a QB or TE, top 24 as an RB, and top 36 as a WR for each season.
    ff_tall: Includes players who played in at least 6 games per season and scored in the top 50% of all players over all seasons (scoring ~33 points). This dataframe aids in holistic data analysis and visualization of fantasy performance.
    qb_wide, rb_wide, wr_wide, te_wide: These dataframes contain individual player stats from 2019 to 2022 for each respective position. We use these dataframes for modeling and predicting a player's performance in the following season based on their previous year's stats, as well as some current year attributes (like Average Draft Position, age, and current team's stats last year)

## Data Exploration and Visualization

After extensive data cleaning, merging, and exploration, we have created a Tableau Dashboard for easier visualization and trend spotting.

Here is the link to the Tableau dashboards -- https://public.tableau.com/app/profile/stephen.kuc/viz/FantasyFootballVisualizations/Dashboard2 -- it is still a work in progress but many of the dashboards there give a good view into the overall scoring trends by position.

## Modeling to predict scores

Due to the nature of the data and utilizing stats and features from players' previous seasons, there were many natural nulls and missing data for features for certain players. For example, if a player was injured in 2020 but had stats in 2019 and 2021, their 2020 stats would be null. Or, if a player joined the league in 2022, then they wouldn't have any stats for 2019 - 2021. 

Because of this, models that were able to train with nulls were advantageous. Some that were initially utilized were XGBoost and Histogram Gradient Boosting.

The target data was fantasy points per game. While a large idea is understanding how much players can score in an entire year, injuries do happen, and it would be best to know how many points a player can score a game. Thus, that was the target data.

## Training Models
At first, only the previous year data and current year attributes were utilized in modeling. These models were then tuned, and even more featueres were put in -- including data from 2 seasons ago -- which was more fantasy and individualistic in nature.

## Results

The initial model resulted in metrics like an R^2 in the range of .75 - .85, depending on the position, and RMSE around 2 - 4 points per player.

The second models proved to provide even stronger results wtih the test data, although there was only 2021 and 2022 to test on. However, each year had an R^2 of .9 or more for most positions, with even better RMSE.

### Collaboration

If you have any ideas or have worked on similar projects, we would love to connect and collaborate! Together, we can enhance our understanding of fantasy football dynamics and improve our strategies for better performance in the game. Let's build a winning team together!

Thank you for visiting!
