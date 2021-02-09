## Fathi_portfolio
Data Mining final project as a junior data scientist.

# Final Project: Movie Recommender System (Project Overview)
* Created a tool that recommend a several movies based on 1 movie title with same characteristics. 
* Understanding the dataset.
* Cleaning data from the movie raw dataset using Phyton, Excel, and PowerBi.
* Optimized K-Nearest Neighbour(KNN) with a different metric (Manhattan distance, Euclidean distance and Cosine similarity) using RapidMiner and Phyton to reach the best model for  predictive data mining solution and used K-means for descriptive data mining solution. 
* Built the interface of Movie Recommender System using Spider.

## Introduction
Movie Recommendation System is a program to predict or suggest a list of movie from inputted movie. The predicted movie is based on past ratings given from a number of users towards a movie.

## Dataset 
We are using two dataset which are movies.csv and ratings.csv. This dataset describes 5-star rating from MovieLens, a movie recommendation service. It contains 100836 ratings across 9742 movies. These data were created by 610 users between March 29, 1996 and September 24, 2018. This dataset was generated on September 26, 2018. We got the following: 
#### movies.csv
* movieId     -> movie unic identification number 
* title       -> movie title eg. Toy Story
* year        -> year of release eg. 1995
* genres      -> movie genre that consist of multiple genres per movie eg. Adventure|Animation|Children|Comedy|Fantasy
* title(year) -> movie title with year of release eg. Toy Story(1995)

#### ratings.csv
* userId    -> user unic identification number
* movieId   -> movie unic identification number
* rating    -> movie review rating from 0.5 until 5
* timestamp -> timestamp

## Data Cleaning 
After scrapping the data, we needed to clean it up so that it was usable for our model. We made following changes and created the following variables:

#### 1) Merged two datasets 
Merged movies.csv and ratings.csv into movieRating.csv dataset using RapidMiner. It is easy for us to used it for data analysis.
* join them with 'movieId'

#### 2) Data selection
We only choose the following data for our problem solving to minimizing the scope using RapidMiner and Phyton.
* movieId
* genres
* title
* userId
* rating

#### 3) Data reduction 
The importance of this step is easy to do data exploratory without having trouble dealing with blank space that will not bring any meaning to our dashboard. The activities below executed by using Excel.
* removed all the movie that have no rating 
* removed 'blank' in genres
* removed '(no genre listed)' in genres

#### 4) Data transformation 
The importance of this step to ease in plotting the graph, for easy to retrieve insightful information and make it easier for stakeholders to read. Hence, to create a readable dashboard for stakeholders. And also helped us in developing the descriptive data mining solution as we focused on genres data to do clustering using K-means. The activities below executed by using Excel.
* splited the genres into several binomial attributes 
* eg. genres consist of (Adventure|Animation|Children|Comedy|Fantasy), we split it into multiple column where if its true is '1', false is '0'

## Problem Statement & Stakeholders 
### Stakeholders
This project we are focusing on several stakeholder which are:
#### 1) Film Director 
* a person who determines the feature film, television show, short film or other production. They have complete control of a project.
#### 2) Cinema owner 
* a person who own a cinema.
#### 3) Moviegoers 
* a person who goes to cinema, especially on a regular basis.

### Problem statement
Based on the dataset we decided to create a question to guided us in doing explotary data analysis, we define some of the questions that can be evaluated for movie rating dataset:
#### 1) What are the top rating animation movies ?
* This is really important as it help the film director to choose animation/cartoon movies that have high rating to bring to live-action adaptation, for example Mulan, Aladdin and etc.
* Help the cinema owner to do an all out campaign when the next movie series of top animation movie are release (Toy Story, Toy Story 2, Toy Story 3), example make merchandise based on the movie. 
#### 2) What word are frequently used in naming the movies ?
* This is for helping the film director to brainstorming on the next movie title for their project.
#### 3) Does the genres of movies affect their rating ?
* Film director can consider what type of movie genre they want to focus on that will catch a lot of view and higher rating. 
#### 4) How frequent movies been release throughout the year by genres?
#### 5) Why certain movie got lower rating ?
* To let the film director to consider their action or idea in making the movies.

## Exploratory Data Analysis (EDA)






