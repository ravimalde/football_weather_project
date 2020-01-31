# Executive Summary

The goal of this project was to determine certain performance characteristics of division 1 and 2 German football teams over the 2011 season. The questions to be answered were as follows:

1. What were the total number of goals scored by each team during the season?
2. How many wins did each team earn during the season?
3. What was each teams' win percentage on match days where the it was raining?

To begin, the kaggle database was imported to Python using SQL queries and then turned into pandas dataframes. All non-German teams were removed from the dataframe. A series of pivots were then used to create a team_data dataframe that contains each teams total goals, wins, losses and draws for the season. A bar plot was then created containing the wins, losses and draws of each team.

A connection was made to the DarkSky API from which the weather data was obtained for each match in the 2011 season. All matches where it did not rain were removed from the dataframe, and a pivot was used to total each teams' wins, losses and draws for matches where it was raining. From this, a percentage win during rainy games was calculated for each team. These values were then added as a new column in the team_data dataframe.

The team_data dataframe was then converted to a dictionary to be stored in a collection on a mongodb server. The bar plot containing wins, losses and draws for each team was converted into a bytes string and also added to the mongo collection.

