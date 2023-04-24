# Anime Recommendation

<p align="center">
  <img width="495" alt="image" src="https://user-images.githubusercontent.com/85885666/234065818-e637edb4-c2e4-433e-9833-bbebe22120d7.png">
</p>

As a relatively new fan of anime, I find myself overwhelmed with the sheer number of anime titles available to watch. With limited time on my hands, I need a way to narrow down my options and discover the best anime that align with my interests. To solve this problem, I embarked on a project to build an anime recommendation system.

In this notebook, I'll take you on my journey of creating a personalized anime recommendation system using Kaggle's anime dataset. Through various algorithms and techniques, I'll demonstrate how my model can suggest anime titles based on my viewing history and preferences.

## Data Processing
As I am only interested in Anime series and not the other categories, anime with type != 'TV' is dropped. Also, ratings with -1 which means that the user watched it and not rated it were dropped as well. 

<p align="center"
<img width="384" alt="image" src="https://user-images.githubusercontent.com/85885666/234066868-1647bc8b-dbe7-4059-b2dc-7a9a775d5611.png">
</p>

## Content Based Filtering (CBF)
<p align="center">
![image](https://user-images.githubusercontent.com/85885666/234067811-1fcf99ae-b8b0-4cb5-b020-a8f80463c1e2.png)
</p>

Content-Based Filtering (CBF) is a recommendation system that uses the characteristics of items, such as genre, to recommend similar items to users. To recommend anime to users based on their previous anime choices, CBF analyzes the genre of each anime and builds a model that can predict how likely a user is to enjoy an anime based on these features. This is done using the TF-IDF vectorizer to convert the list of genres for each anime into a feature matrix, and then using the cosine similarity metric to compute the similarity between each pair of anime based on their genre features. Finally, anime is recommended to a user based on their previous choices and the anime that are most similar to those they have enjoyed.

<p align="center">
<img width="952" alt="image" src="https://user-images.githubusercontent.com/85885666/234068341-b8bd2093-7122-4c09-8119-3c8bc289e10c.png">
</p>

## Collaborative Filtering (CF)
<p align="center">
![image](https://user-images.githubusercontent.com/85885666/234066040-1b622455-646e-4735-a4c3-7326a42f3803.png)
</p>

User-Based Collaborative Filtering (UBCF) is a technique used in recommendation systems that suggests items to users based on the similarity of their preferences to those of other users. UBCF analyzes the past behavior of users to identify those with similar preferences and uses a similarity metric such as cosine similarity or Pearson correlation coefficient to determine their similarity. UBCF then recommends items that similar users have enjoyed to the target user, assuming that users who have enjoyed similar items in the past are likely to enjoy similar items in the future. UBCF is an effective approach for building personalized recommendation systems that provide relevant suggestions to each user.

<p align="center">
  <img width="1050" alt="image" src="https://user-images.githubusercontent.com/85885666/234069019-2df7d3af-d472-4074-8aa9-c5a042176d1c.png">
</p>


## Requirements
To run the notebook, you will need to have Python 3 and the following libraries installed:

<ol>
  <li>numpy</li>
  <li>pandas</li>
  <li>matplotlib</li>
  <li>seaborn</li>
  <li>sklearn</li>
</ol>
You can install these packages by running the following command using pip:
<code>pip install numpy pandas matplotlib seaborn sklearn</code>

## Usage
To use this notebook, you can either download it directly from the repository or clone the entire repository to your local machine. Once you have the notebook, you can open it using Jupyter Notebook or JupyterLab. 

To run the notebook, you can execute each cell in sequence. The notebook includes detailed explanations of each step and how the function is created. You can then use get_recommendation(anime_title,num_recommendations=5) for CBF or get_recommendation(user_id,nums_recommendation=5).

## Dataset
This data set contains information on user preference data from 73,516 users on 12,294 anime. Each user is able to add anime to their completed list and give it a rating and this data set is a compilation of those ratings. The data set contains two csv, anime.csv and rating.csv. The anime.csv contains information about each anime such as name,genre,episodes,types. Rating.csv contains user_id, anime_id, and rating from the user. 

You can find the dataset from the following link: https://www.kaggle.com/datasets/CooperUnion/anime-recommendations-database

## License
The code in this repository is licensed under the MIT License. See [LICENSE.md](LICENSE.md) for more information.

  
