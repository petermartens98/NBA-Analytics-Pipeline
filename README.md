# NBA-Analytics-Pipeline
Python ETL Pipeline that web-scrapes up-to-date NBA data from multiple sources, then statistically analyzes and visualizes into multiple team, player and league-wide reports, as well as predictivelly modelling and statistically correlating various stats.
## Related Projects
<b>Link to NBA Flask Applications repo:<b> https://github.com/petermartens98/NBA-Flask-Applications
<b>Link to NBA Shooting Heatmaps repo:<b> 

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

# Score Predictions Output Example:

![image](https://user-images.githubusercontent.com/87671757/217118003-b9600697-8872-49d3-abb3-b802d250dc68.png)

# NBA Player Report Visulations Output Example:

![image](https://user-images.githubusercontent.com/87671757/216218031-e24163fd-ed3a-4ca7-86f0-b5485a0cb23e.png)
![image](https://user-images.githubusercontent.com/87671757/216218377-ca8740ea-2d17-42de-a8ea-6d081fd4d08e.png)

# NBA Team Report Visualization Output Example:

![image](https://user-images.githubusercontent.com/87671757/216219222-f99764e9-e5b8-4450-929f-6c8b9c97a84c.png)
![image](https://user-images.githubusercontent.com/87671757/216219308-b41a6362-9866-439c-a14e-758fad5c3114.png)
![image](https://user-images.githubusercontent.com/87671757/216219426-bd3a4156-36d1-4f42-ab56-b01d85eb3e4a.png)

# Statistical Regression Anlysis/Visualization Output Example:

![image](https://user-images.githubusercontent.com/87671757/216218923-9181a857-1d5c-49b6-95e2-df7b19cc50fb.png)
