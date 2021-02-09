## Fathi_portfolio
Data Mining final project as a junior data scientist.

# Final Project: Movie Recommender System (Project Overview)
* Created a tool that recommend a several movies based on 1 movie title with same characteristics. 
* Understanding the dataset.
* Cleaning data from the movie raw dataset using Phyton, Excel, and PowerBi.
* Optimized K-Nearest Neighbour(KNN) with a different metric (Manhattan distance, Euclidean distance and Cosine similarity) using RapidMiner and Phyton to reach the best model for  predictive data mining solution and used K-means for descriptive data mining solution. 
* Built the interface of Movie Recommender System using Spider.

## Dataset 
We are using two dataset which are movies.csv and ratings.csv. We got the following: 
### movies.csv
* movieId     -> movie unic identification number 
* title       -> movie title eg. Toy Story
* year        -> year of release eg. 1995
* genres      -> movie genre that consist of multiple genres per movie eg. Adventure|Animation|Children|Comedy|Fantasy
* title(year) -> movie title with year of release eg. Toy Story(1995)

### ratings.csv
* userId    -> user unic identification number
* movieId   -> movie unic identification number
* rating    -> movie review rating from 0.5 until 5
* timestamp -> timestamp

