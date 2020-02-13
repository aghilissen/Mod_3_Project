# Mod_3_Project

This project is the result of the collaborative work between Antoine Ghilissen and Mate Pocs, carried out for the Flatiron School Module 3 Project. 
<br>
<br>
## Executive Summary
We based our analysis on the 2019 World Happiness Report. This is an annual publication of the U.N., aimed to capture the general happiness level of the population in individual countries.  The happiness score is based on respondents rating their own lives. We wanted to analyse which economic / demographic variables have a large impact on the happiness level of the countries. 
<br>
We collected various information on a country level from two sources:
<br>
- Wikipedia tables, which we web scraped using Python BeautifulSoup
- World Bank data, for which we used an API provided by the organization
<br>
Then we merged these per country information with the WHR table to create a combined database. After excluding a few rows (disputed territories, countries where a lot of information was not available, etc), we were left with 152 rows and 46 columns.
<br>
In the next step, we explored the data with visualization tools like scatter plots, plotly combined plots. Following that, we carried out various statistical analyses to identify variables that have a strong relationship with the happiness index. Our analysis includes:
- Welch's t-tests
- Linear regression (OLS method)
- ANOVA
<br>
__Conclusion__
There is a strong positive relationship with GDP per capita, life expectancy at birth, government type. Happiness also changes based on which continent the country is on. 
We found various, less strong relationships with a number of variables (weight of agriculture / service industry in economy, median age of the population, suicide rates also have a slight positive relationship with happiness).A number of variables (olympic medals, alcohol consumption, cigarette consumption) showed no significant pattern of relationship with happiness.
## GitHub Structure
-data folder: 
--individual databases from various sources in .csv files
--Jupyter Notebooks with Python code of webscraping 
--Jupyter Notebooks with Python code of API data requests
--finaldf.csv: final combined .csv that is going to be used in the statiscial analysis
<br>
-wiki.ipynb: merges World Happiness Report with per country information web scraped from various Wikipedia pages
<br>
-WB.ipynb: merges combined.csv created in the previous step with information gathered from the World Bank API, creates the finaldf.csv file, saved in the data folder
<br>
-index.ipynb: the main results of the project, the statistical analysis of the data in finaldf.csv
presentation.pdf: a presentation aimed at a general, non-technical audience



