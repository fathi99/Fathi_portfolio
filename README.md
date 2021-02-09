## Fathi_portfolio
Data Mining final project as a junior data scientist.

# Final Project: Movie Recommender System 

## Overview
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
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/dashboard.JPG)



## Descriptive (K-Means)

## Predictive (K-Nearest Neighbour)

## Result 
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/result%20experiment.JPG)

## Data Product
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/data%20product-KNN.jpeg)

The user will enter the movie title and then press the button 'Recommend', the system will recommend 10 list of movies that have similarity. Noted that we are using Manhattan distance for our Movie Recommendation System as we have discuss in result and analysis previously. And below is system that we built based on K-means algorithm that cluster the movie based on genres and ratings. Insert movieId in the textfield, next click Recommend button it will recommend 10 list of movies that have similarity based on clustering. Both systems are developed using spider software after coding in phyton using colab and both system will listed 10 recommended movies with its movieId and title.

![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/data%20product-Kmeans.jpeg) 


## Conclusion 
Finally, it may be concluded Rapid Miner offers a rich range of Machine Learning algorithms for data mining activities, along with a robust set of operators (functions) for pre-processing data. Rapid Miner has a website of hundreds of machine learning algorithms and functions. Rapid Miner is simple to use because RapidMiner is an easy-to-use visual workflow designer program. We design models to ensure that the precision of each model is capable of achieving the desired standard. It is also simple to set the parameters for each degree of operation and the ratio for each model. 

Building a data mining model using Python is challenging because every process that we want to use either exists in the module or needs to be built. The codes used in this assignment have limited configuration or tuning that can be done to increase the accuracy of each model. However, we managed to conduct training and testing using the dataset we chose. The use of Python programming and Rapid Miner allows us to analyse a lot of the dataset and then compare the results for both approaches.





