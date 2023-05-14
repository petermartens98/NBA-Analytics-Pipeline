# NBA-Analytics-Pipeline
Python ETL Pipeline that web-scrapes up-to-date NBA data from multiple sources, then statistically analyzes and visualizes into multiple team, player and league-wide reports, as well as predictivelly modelling and statistically correlating various stats.
## Related Projects
<b>Link to NBA Flask Applications repo:<b> https://github.com/petermartens98/NBA-Flask-Applications

<b>Link to NBA Shooting Heatmaps repo: <b> https://github.com/petermartens98/NBA-Shooting-Heatmaps

<b>Link to NBA Performance vs Salary Regression Anlaysis repo: <b>https://github.com/petermartens98/Salary-and-Performance-Regression-Analysis-for-2012-to-2018-NBA-Data

# File Desctiptions and Example Screenshots
## NBA_Injuries_Webscraping.ipynb
#### Imports Utilized
This is a Python function that scrapes the daily NBA injury report from the CBS Sports website and returns the data as a Pandas DataFrame. The function uses the BeautifulSoup and Selenium libraries to parse the HTML and interact with the website.

The function starts by setting some options for the Selenium webdriver, including running in headless mode (without opening a visible browser window). It then defines the URL to scrape and the location of the Chrome driver on the user's computer. 

The function then creates a new webdriver instance, sets a page load timeout, and navigates to the specified URL. It retrieves the page source HTML and uses BeautifulSoup to find the sections of the page containing injury data for each team.

For each team, the function loops through the player injury data and creates a dictionary of the relevant fields (team, player name, position, injury, and status). It then appends this dictionary to a list of all player data for all teams.

Once all the data has been collected, the function quits the webdriver and returns the data as a sorted Pandas DataFrame, with one row per player injury.

## NBA_Live_Scores_Webscraping.ipynb
#### Imports Utilized: Pandas, NumPy, Requests, BeautifulSoup, and Selenium
This code defines a function called "today_matchups" that uses web scraping to retrieve information about NBA games that are being played today from ESPN's website.

The function begins by creating a URL using the current date, which is obtained using the datetime module. A Chrome webdriver is then set up with Selenium and the page is loaded using the URL. The page source HTML is then parsed using BeautifulSoup.

The function then retrieves the date and day of the week using datetime, and finds all of the divs on the page that contain information about each game. It iterates over these divs to extract relevant data, such as the teams playing, the time of the game, the current score, and the betting odds. The data is stored in a dictionary for each game, and all of these dictionaries are appended to a list called "games_data".

Once all of the data has been extracted, it is stored in a Pandas DataFrame, which is returned by the function. The Chrome webdriver is then closed to avoid resource leakage.

Overall, this function retrieves the latest information about NBA games being played today, and stores it in a DataFrame that can be used for further analysis or visualization.

## NBA_Players_Webscraping_to_SQLite.ipynb
This code is a Python script that demonstrates webscraping data from a website, storing it in a Pandas DataFrame, and then inserting that data into an SQLite database. Specifically, the script scrapes NBA player data from ESPN.com for all teams in the league, stores it in a DataFrame, and then converts certain columns to numeric values (height to inches, weight to pounds, and salary to an integer). The script then creates an SQLite database with a table named "NBA_Players" and inserts the player data from the DataFrame into that table. Finally, the script commits the changes to the database and closes any open cursors.

## NBA_Score_Predictions_Pipeline_V1.ipynb
![image](https://user-images.githubusercontent.com/87671757/217118003-b9600697-8872-49d3-abb3-b802d250dc68.png)

## NBA_Team_Analytics_Pipeline_V2.ipynb
#### Data Webscraping
This code segment scrapes NBA boxscore data for the 2022-2023 regular season from stats.nba.com and basketball-reference.com using a request to a specific URL with parameters to filter the data. It retrieves the data in JSON format and converts it into a pandas DataFrame. The DataFrame is then modified to include additional columns with statistics related to field goals made, attempted, and points, as well as opponent team and opponent points, as well as other more advanced statistics such as distance and shot type. It also adds columns for the team's conference, whether the game was played at home or away, and a formatted date and matchup string. 

#### Correlation Heatmap for Team Average DF
![image](https://user-images.githubusercontent.com/87671757/235541616-6c0d92de-e570-4bcb-98b9-d375dc16c75b.png)

#### Points Scored vs Rebound Gained Regression Analysis 
  ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/cefdf60f-1c0b-4779-9d03-aac381f4d6d9)

#### Points Scored vs Assists Gained (Wins vs Losses) Regression Analysis 
  ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/c1b364f0-5ff6-4dbf-b27a-5cedc003122d)

  
#### Visualization Functions
##### def nba_fg_by_dist() - visualize fg% by differing distances for the whole NBA at a given time
or 
##### def team_fg_by_dist(abbr) - visualize fg% by differing distances for a given team at a given time
![image](https://user-images.githubusercontent.com/87671757/235541363-44827d57-2728-401e-821f-0a5a4d058930.png)

##### def NBA_stat_boxplots(stat, sort_by='mean', asc=True) - visualize by team their comparing boxplots for a given stat
![image](https://user-images.githubusercontent.com/87671757/235541852-8417ae48-0d5b-46fa-80d0-737c115f1636.png)

##### def plus_minus_plot(team_abbr)
![image](https://user-images.githubusercontent.com/87671757/235542379-067a2a60-69d2-4c7d-b7da-f77749fcac0b.png)

##### def scored_allowed_compare(team_a_abbr, team_b_abbr)
![image](https://user-images.githubusercontent.com/87671757/235542460-a86dee52-fa7e-4b8b-b68c-4484f896182d.png)

##### def rebounds_compares()
  ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/79c3c06a-b2d3-48fb-bccd-fc266a3a9d27)

##### def line_plot_scores()
 ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/8b43e86f-17c5-464d-869d-793199f9837d)

##### def trend_plot_scores()
  ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/da4d9008-6040-4a69-8a5d-3e10f2638842)

##### def shot_pies() ~ Scoring Distribution 
  ![image](https://github.com/petermartens98/NBA-Analytics-Pipeline/assets/87671757/48585838-4b79-4d1f-8935-e53df2d0aa6e)

##### Team Average Reression (statx vs staty) Plot and Analysis Function
 

#### NBA Team Report Visualization Output Example:

![image](https://user-images.githubusercontent.com/87671757/216219222-f99764e9-e5b8-4450-929f-6c8b9c97a84c.png)
![image](https://user-images.githubusercontent.com/87671757/216219308-b41a6362-9866-439c-a14e-758fad5c3114.png)
![image](https://user-images.githubusercontent.com/87671757/216219426-bd3a4156-36d1-4f42-ab56-b01d85eb3e4a.png)

# NBA Player Report Visulations Output Example:

![image](https://user-images.githubusercontent.com/87671757/216218031-e24163fd-ed3a-4ca7-86f0-b5485a0cb23e.png)
![image](https://user-images.githubusercontent.com/87671757/216218377-ca8740ea-2d17-42de-a8ea-6d081fd4d08e.png)

# Statistical Regression Anlysis/Visualization Output Example:

![image](https://user-images.githubusercontent.com/87671757/216218923-9181a857-1d5c-49b6-95e2-df7b19cc50fb.png)
