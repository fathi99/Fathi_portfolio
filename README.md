## Fathi_portfolio
Data Mining final project semester as a junior data scientist.

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
#### 2) Film Producer
* a person who oversees the film production, typically manages the logistics and business operations.
#### 3) Cinema Owner 
* a person who own a cinema.
#### 4) Moviegoers 
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
We looked at the data and came up with this dashboard as it based on our stakeholders to maximize the data and easy to understand for their own benefits. Below are the several graphs and table that we transform it in dashboard for easy understanding. The most important why we build this dashboard is to increase our stakeholder revenue.


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/dashboard.JPG)


#### 1) Top Rated Movie From Top 5 Genre per Year (1995-2018) [Stacked Bar Graph]
Attribute: genres, rating, year; For this stacked bar graph we can observed that which top 5 movie genres that have been produced have the higher rating from 1995-2018. We observed that drama and comedy have a higher rating compare to 3 others action, romance and thriller. With this observation film director or producer can produced more movies based on drama and comedy, maybe also can combine the genres and make it into drama comedy movies. The movie will definitely gone hit in the market. Besides, cinema owner can do an advertisement on movie that based on drama and comedy, it will help increase in revenue. 

#### 2) Percentage of Genre From 1995 to 2018 [Donut Graph]
Attribute used: genres, year; For this donut graph we can observed which are the most movie genres produced from 1995-2018, so that we can see the trend what kind of movies that people want to watch, producer can invest on making movies based on the top movie genres produced which are Drama, Comedy and Action.

#### 3) Top Rating Animation Movie [Table]
Attribute used: title, rating, genres; For this table we can see the top rating animation movies that have potential to recreate into live-action adaptation. It will have higher possibilities that the live-action adaptation movie based on top animation will get a hit and increase the revenue for the stakeholders. Besides, cinema owner can consider what animation movie to invest their merchandise on (mug, t-shirt, figure) to create more profit.

#### 4) Most Frequent Word Used in Movie Title [Bar Graph]
Attribute used: title; For this bar graph we are exploring the most frequent word used in movie title which can help the film director to generate title for their new upcoming movies. For example, if the director decide to continue its movie series it can add '2' in the title eg. Toy Story, Toy Story 2. 


## Methodology 
### Descriptive (K-means)
The k-means clustering is a method of vector quantization, originally from processing that aims to partition 'n' observations into k-clusters in which each observation belongs to the cluster with the nearest mean(cluster centers or cluster centroid), serving as a prototype of the clister. K-means clustering minimizes within-clustering variances (squared Euclidean distances, but not regular Euclidean distances. In this project we build and testing the model using RapidMiner and Phyton.
#### RapidMiner
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/kmeans_design_model.JPG)
* #### Read excel

Read a dataset that has been pre-processing as we mention before in Data Cleaning.
* #### Select attribute

We selected targeted attributes and labels for the model to predict, for this case for the k-means to cluster. We are using it for tuning the models to increase the accuracy, sometimes we target more than 3 attributes to assist the prediction. But most of the time we chose the one that we thinkreally will impact the most. 
* #### Filter examples

We applied the targeted attribute equals to “not missing” as we want to ease our models without needto find or predict the missing data. If not get rid of the missing value sometimes it will count as ‘blank’ and that will affect the prediction models.
* #### Normalize

This Operator normalizes the values of the selected Attributes. Normalization is used to scale values so they fit in a specific range. Adjusting the value range is very important when dealing with Attributes of different units and scales.
* #### Clustering

The descriptive model operator (k-means) set k = 18.
* #### Performance

This operator is used for statistical performance evaluation of classification tasks. This operator
delivers a list of performance criteria values of the classification task.

#### Phyton
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/kmean_phyton.JPG)
* #### Merge dataset 

We merged dataset from movies.csv and ratings.csv into 1 dataset.
* #### Apply pre-processing 

Remove all the null values and split the genre into a simple form.
* #### Apply k-means algorithm

clustering k = 18.
* #### Run code

User enter the movie id and the system will recommend the top 10 movies.
* #### Debug

Fix any bug or error in the coding if any.

### Predictive (K-Nearest Neighbour)
The k-nearest neighbors algorithm is a supervised classification algorithm. It takes a bunch of labeled points and uses them to learn how to label other points. To label a new point, it looks at the labeled points closest to that new point which are its nearest neighbors, and has those neighbors vote.
#### RapidMiner
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/knn_design_model.JPG)
* #### Read excel

Read a dataset that has been pre-processing as we mention before in Data Cleaning.
* #### Select attribute

We selected targeted attributes and labels for the model to predict, for this case for the k-means to cluster. We are using it for tuning the models to increase the accuracy, sometimes we target more than 3 attributes to assist the prediction. But most of the time we chose the one that we thinkreally will impact the most. 
* #### Set role

We set 'rating' as labels. Because 'rating' we want to look at and predict. 
* #### Split data

We splitted the data for training and testing the models to: 
* Training 70%, testing 30%. 
* Training 50%, testing 50%. 
* Training 30%, testing 70%. 

* #### K-Nearest Neighbour

This Operator generates a k-Nearest Neighbor model, which is used for classification or regression. We measured numerical and its types are Cosine Similarity, Euclidean Distance and Manhattan Distance.
* #### Apply model

This Operator applies a model on an ExampleSet.
* #### Performance

This operator is used for performance evaluation. It delivers a list of performance criteria values. These performance criteria are automatically determined in order to fit the learning task type.
#### Phyton
![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/knn_phyton.JPG)
* #### Merge dataset 

We merged dataset from movies.csv and ratings.csv into 1 dataset.
* #### Apply pre-processing 

Remove all the null values and split the genre into a simple form.
* #### Apply k-nn algorithm

Using different metric = Manhattan/ Cosine/ Euclidean. Algorithm = Brute and n_neigbors = 20.
* #### Run code

User enter the movie id and the system will recommend the top 10 movies.
* #### Debug

Fix any bug or error in the coding if any.

## Experiment Setting

## Result 
After conducting the experiment above we have observed and create a result table like below.


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/result%20experiment.JPG)


In phyton, we used accuracy(%) to measured the performance of the model when we do the split data training and testing. Higher performance accuracy indicate that the model is good for the dataset and  we can observed that overall the Manhattan distance have the higher performance accuracy. In RapidMiner used Root Mean Square Error(RMSE) (+/-) to measured the performance of the model when we do the split data training and testing. Lower in RMSE indicate that the model is good for the dataset and we can observed that overall the Euclidean distance have the lower RMSE, but not big in different with the Manhattan distance.  

We used the same design models to apply to all the predictive models in RapidMiner and Phyton. Although we applied the same design, they have different preprocessing and data selection methods. Some models when we select more attributes as a target it will increase the accuracy of the model, and some are not. For example we will tune the 0.7:0.3 models for each of the predictive models the accuracy reaches above 80%, then we apply the design models for ratio 0.5:0.5 and 0.3:0.7. We have observed the accuracy will decrease based on their training and testing ratio. The higher the training ratio, the more accurate the models will become when doing the testing. This is because we feed the models with more dataset to observe and develop (training) the models. Noted that we used the same tuning model and design model for the different training and testing ratio. Therefore we can say if we feed the models with 100% of the dataset to do the training for developing the models, the accuracy will be higher than the 70% training models in testing. Next, below are the result for k-means, we did not do any comparing as it not meant to find accuracy or RMSE. 


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/k-means%20graph.JPG)


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/clustering%20kmeans.JPG)




In conclusion, we decided to use K-nearest neighbour with Manhattan distance to our product tool which is Movie Recommender System and we also develop with k-means algorithm for our product tool.



## Data Product


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/data%20product-KNN.jpeg)


The user will enter the movie title and then press the button 'Recommend', the system will recommend 10 list of movies that have similarity. Noted that we are using Manhattan distance for our Movie Recommendation System as we have discuss in result and analysis previously. And below is system that we built based on K-means algorithm that cluster the movie based on genres and ratings. Insert movieId in the textfield, next click Recommend button it will recommend 10 list of movies that have similarity based on clustering. Both systems are developed using spider software after coding in phyton using colab and both system will listed 10 recommended movies with its movieId and title.


![](https://github.com/fathi99/Fathi_portfolio/blob/main/images/data%20product-Kmeans.jpeg) 

## Conclusion
Machine learning is a method of data analysis that automates analytical model building. It is a branch of artiﬁcial intelligence based on the idea that systems can learn from data, identify patterns and make decisions with minimal human intervention. In this proposed system a movie recommendation system is built using the K-Means Clustering and K-Nearest Neighbor algorithms. The data are taken from movieLens dataset. The system is implemented in the Python programming language and rapidminer. It is seen that after implementing the system in the python programming language the accuracy value for the manhattan technique is better than the cosine and euclidean technique. For the rapidminer has a low root mean square error. The proposed work can be improved using more datasets. The sentimental analysis concept can be used in the future to enhance the efﬁciency of the movie recommendation system, so the model can be tuned to accommodate more situations.

## Reflection
Finally, it may be concluded Rapid Miner offers a rich range of Machine Learning algorithms for data mining activities, along with a robust set of operators (functions) for pre-processing data. RapidMiner has a website of hundreds of machine learning algorithms and functions. Rapid Miner is simple to use because RapidMiner is an easy-to-use visual workflow designer program. We design models to ensure that the precision of each model is capable of achieving the desired standard. It is also simple to set the parameters for each degree of operation and the ratio for each model. 

Building a data mining model using Python is challenging because every process that we want to use either exists in the module or needs to be built. The codes used in this assignment have limited configuration or tuning that can be done to increase the accuracy of each model. However, we managed to conduct training and testing using the dataset we chose. The use of Python programming and Rapid Miner allows us to analyse a lot of the dataset and then compare the results for both approaches.





