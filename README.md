# nosql-challenge

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

This repository contains:
* A Eat_Safe_Love folder containing two jupyter notebooks
* Resources folder containing a json file of establishment data.

----------------

# noSQL_setup.ipynb contains Part 1 and Part 2
----------------
## Part 1: Database and Jupyter Notebook Set up
*  The json file was brought into the Mongo database using the following terminal command:
     mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json 
* The database is called: uk_food

## Part 2: Update the Database 
* A halal restaurant called 'Penang Flavours' was inserted into the uk_food database
* The buisnessTypeID for the new restaurant was changed to 1 to match the rest of the restaurants in the database.
* All establishments in the Dover Local Authority were removed
* The latitude and longitutde of all establishments were converted to decimal

----------------

# NoSQL_analysis.ipynb contains Part 3
----------------

## Part 3: Exploratory Analysis

The following questions were answered:
1. Which establishments have a hygiene score equal to 20?
    * 41 establishments were found to have a hygiene score of 20.

2. Which establishments in London have a RatingValue greater than or equal to 4?
    * A query was created using regex.
    * 34 establsihments have a rating of '4' or greater

3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score nearest to the new restuatant? 
    * The top 5 estaclishments sorted by the lowest hygiene scoreo (a score of 0) are Howe and Co Fish and Chips - Van 17, Lumbini Grocery Ltd, Plumstead Manor Nursery, Iceland, and Volunteer. 

4. How many establishments in each Local Authority area of a hygiene score of 0?
    * A query pipeline was created where the data was grouped by it's local authority area. 
    *It was found that Thanet had the most establishments with a hygiene score of '0' with 1130. 
