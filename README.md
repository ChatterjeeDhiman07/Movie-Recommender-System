This Project aims at predicting movies based on 2 systems:

## Demographic Filtering:
 
 provides generalized recommendations to every user, based on movie popularity and/or genre.
 The System recommends the same movies to users with similar demographic features.

## Content Based Filtering: 
 
suggest similar items based on a particular item. 
This system uses item metadata, such as genre, director, description, actors, etc. for movies, to make these recommendations.
The general idea behind these recommender systems is that if a person liked a particular item, he or she will also like an item that is similar to it.

The dataframes are created from the datasets in csv format in the rar file. then the 2 dataframes are merged on the id column.

In content based filtering, we rate the movies based on the following metric taken from the Imdb Website:

![wr 1](https://user-images.githubusercontent.com/44091016/50739477-fc174d00-1206-11e9-987e-0f75d16a80aa.png)

#### v is the number of votes for the movie
#### m is the minimum votes required to be listed in the chart
#### R is the average rating of the movie 
#### C is the mean vote across the whole report

Using the mean of the ratings for the movies, we select the movies which are in the top 0.9 of the quantile. Which are finally included in our reccomended list.

In content based filtering, We will compute pairwise similarity scores for all movies based on their plot descriptions and recommend movies based on that similarity score. The plot description is given in the overview feature of our dataset.


we need to convert the word vector of each overview.For this we'll compute Term Frequency-Inverse Document Frequency (TF-IDF) vectors for each overview.

scikit-learn provides us with a built-in TfIdfVectorizer class that produces the TF-IDF matrix in a couple of lines.

After we have the vetor matrix, we can calculate there similarity cosines. 

Using this similarity index we will create our final predictor function which predicts our movie for us.
