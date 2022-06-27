# Cinephiles
### Project 2, Group 1: Movies, Movies, Movies!
This project was completed as a part of the Data Science and Visualization Bootcamp at Northwestern University (https://bootcamp.northwestern.edu/data/).
![](https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/fall-movies-index-1628968089.jpg)
## Project Intro/Objective
The purpose of this project is to clean and merge two datasets about movies, and create a relational database. 
### Collaborators
* Ishan Sidhu
* Corey Lawson-Enos
* Harish Korrapati 
* Rhiana Schafer
### Methods Used
* Relational Database
* ETL
* Data Cleaning
### Technologies
* Jupyter Notebook
* PostGres, MySql
* Pandas/python
## Project Description
In this project, we were interested in creating a database about movies and their data, combining multiple sources into one comprehensive, referencable location. We cleaned and transformed the following sources:
* Kaggle - TMBD (The Movies Dataset)
   * https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?select=movies_metadata.csv
   * Contains many pieces of metadata information
   * Type: csv
   * Columns (items indicated with ~ were dropped due to incomplete data): 
        * ~Budget (int)~ 
        * Genres (json) - id/name of genres
        * Imdb_id (varchar(9)) 
        * Original_language (string) - 2 letter language type
        * Popularity (float) - values calculated based on the below metrics:
        * Number of votes for the day
        * Number of views for the day
        * Number of users who marked it as a "favorite" for the day
        * Number of users who added it to their "watchlist" for the day
        * Release date
        * Number of total votes
        * Previous days score
        * Production_countries (json) - 2 letter country and full name 
        * Release_date (date) 
        * ~Revenue (int) - in usd~
        * Runtime (int) - in minutes
        * Status (string) - released only
        * Title (varchar)
        * Vote_average (int) - rating among TMDB users
        * Vote_count (int) - number of votes from TMDB users
    * Also from TMDB, we used an API pull to generate hyperlinks that connect to each movie's movie poster, as a downloadable image file.
      *  Instructions for how to access the API can be found here: https://developers.themoviedb.org/3/getting-started/authentication
* IMBD Ratings: 
    * https://www.imdb.com/interfaces/title.ratings.tsv.gz
    * Contains the IMDb rating and votes information for titles
    * Type: tsv: converted to csv for easier visualization
    * Columns: 
        * tconst (string) - alphanumeric unique identifier of the title, same thing as imbd_id in TMBD
        * averageRating (int)–weighted average of all individual user ratings (IMBD)
        * numVotes (int)- number of votes the title has received on IMBD
## Using this database
We encourage any other cinephiles out there to download this database and draw your own cinematic conclusions!
1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).
2. API key is needed for accessing movie poster - instructions can be found here https://developers.themoviedb.org/3/getting-started/authentication
3. Raw Data is being kept in the Resource folder. The original datasets can be pulled fresh from the following sites:
    * https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?select=movies_metadata.csv
    * https://www.imdb.com/interfaces/
4. Data processing/transformation scripts are contained in ETL.ipynb
5. SQL database must be generated on local computer using code in "schema.sql"
## Featured Notebooks/Analysis/Deliverables
* ETL.ipynb - main script
* TitleRatingsTSV - code for transforming TSV file - final version incorporated into ETL.ipynb
* schema.sql - code for SQL setup
