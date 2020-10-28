# Analysis of the World Happiness Report 
This project is the result of the collaborative work between Antoine Ghilissen and [Mate Pocs](https://github.com/MatePocs), carried out for the Flatiron School Module 3 Project.

## Executive Summary
We based our analysis on the [2019 World Happiness Report (WHR)](https://en.wikipedia.org/wiki/World_Happiness_Report#2019_World_Happiness_Report). This report is an annual publication of the United Nations Sustainable Development Solutions Network, aimed to capture the general happiness level of the populations in countries around the world. The happiness score is calculated following a survey asking respondents to rate various life factors. The purpose of this analysis is to highlight which economic/demographic variables have a significant impact on the happiness level.

## GitHub Structure
* [data folder](./data/):
  * Individual databases from various sources in `.csv` files
  * Individual python web scraping script used on the Wikipedia tables
  * Charts png exports (to circumvent the plotly express restriction on Github)
  * [Finaldf.csv](./data/finaldf.csv): final combined .csv used in the statistical analysis
* [Wikipedia Notebook](wiki_data_combine.ipynb): merges World Happiness Report with per-country information web scraped from various Wikipedia pages
* [World Bank Notebook](WB.ipynb): merges combined.csv created in the previous step with information gathered from the World Bank API, creates the finaldf.csv file, saved in the data folder
* [Index Notebook](index.ipynb): the main results of the project, the statistical analysis of the data in finaldf.csv
* [Project presentation](presentation.pdf): a presentation aimed at a general, non-technical audience

## The Methodology
We collected various information from two principal sources:
- Wikipedia tables were web scraped using Python's `BeautifulSoup4` library.
- World Bank data were collected via the World Bank API provided in the `pandas_datareader` library.

All these pieces of information provided a  country-level granularity.

This information was then merged with the WHR table to create a combined database. We have excluded some data for various reasons: disputed territories (thus insufficient data), countries where a lot of information was not available, etc.

Following this process, the dataset consisted of 152 rows (countries) and 46 columns.

We then explored the data with visualization tools like `seaborn` scatter plots, `plotly express` combined plots, etc.

Leading us to carry out various statistical analysis identifying the different variables that have an impact on the happiness index. The methods/tests used are:
- Welch's t-test
- Linear regression (OLS method)
- ANOVA

## Insights
There is a strong positive relationship with GDP per capita, life expectancy at birth, government type. Happiness also changes based on which continent the country is on.

We found various, less strong relationships with many variables: the weight of agriculture versus service industry in the economy, the median age of the population and suicide rates also have a slight positive relationship with happiness.

Some variables (Olympic medals, alcohol consumption, cigarette consumption) showed no significant pattern of a relationship with happiness.