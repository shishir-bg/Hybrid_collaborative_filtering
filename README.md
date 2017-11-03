# Hybrid_collaborative_filtering
A simple matrix filtering model based on Matrix Factorization. 
We use the movie dataset downloaded from MovieLens website. The dataset consists of 100,000 ratings and 1,300 tag applications
applied to 9,066 movies by 671 users

For a content-based recommendation system, it is a regression problem in which we try to make a user-to-item rating prediction using the content of items as features.  On the other hand, for a collaborative filtering based recommendation system, we usually don't know the content of features in advance, and by using the similarity between different users (users may give similar ratings to the same items) and the similarity between items (similar movies may be given similar ratings by the users), we learn the latent features and make predictions on user-to-item ratings at the same time. Also, after we learn the features of the items, we can measure the similarity between items and recommend the most similar items to users based on their previous usage information. 

Content-based and collaborative filtering recommendation were the state of the art more than 10 years ago. Apparently, there are many different models and algorithms to improve the prediction performance. For example, for the case in which we don't have user-to-item rating information in advance, we can use the so-called implicit matrix factorization and replace the user-to-item ratings with some preference and confidence measures such as how many times the users click the corresponding items to perform collaborative filtering. Furthermore, we can also combine content-based and collaborative filtering methods to utilize content as "side information" to improve the prediction performance. This hybrid approach is usually implemented by "Learning to Rank" algorithm.

Most recommendation models consist of building a user-by-item matrix with some sort of "interaction" number in each cell. If one includes the numerical ratings that users give items, then this is called an explicit feedback model. Alternatively, one may include implicit feedback which are actions by a user that signify a positive or negative preference for a given item (such as viewing the item online)
In the case of the MovieLens dataset, we have ratings, so we will focus on explicit feedback models

 Requirements:
 numpy
 pandas
 http
 requests
 json
 
 Steps:
 1. Load in data
 2. Construct User-Item Matrix
 3. Compute Cosine Similarity
 4. Compute Top K (We can attempt to improve our prediction MSE by only considering the top $k$ users who are most similar to the input user (or, similarly, the top $k$ items))
 4. Compute Prediction and MSE (For user-based collaborative filtering, we predict that a user's $u$'s rating for item $i$ is given by the weighted sum of all other users' ratings for item $i$ where the weighting is the cosine similarity between the each user and the input user $u$.)
 
 
