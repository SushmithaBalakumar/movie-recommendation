

# Movie Recommendation System

## Overview

This project implements a **Movie Recommendation System using Item-Based Collaborative Filtering**.
The system analyzes user ratings to identify similarities between movies and recommend films that users are likely to enjoy.

The project also includes **model evaluation and visualization of recommendation performance**, demonstrating how recommendation systems can be analyzed using metrics such as precision, recall, F1-score, and accuracy.

The application is exposed through a **Flask API**, allowing recommendations to be retrieved dynamically.

# Key Features

* Item-based collaborative filtering
* Cosine similarity for movie similarity calculation
* Personalized recommendations based on user ratings
* REST API built using **Flask**
* Model persistence using **Pickle**
* Performance evaluation using:

  * Precision
  * Recall
  * F1 Score
  * Accuracy
* Visualization of model performance
* Similarity heatmap for movie relationships

# Dataset

The system uses the **MovieLens Latest Small Dataset**.

Dataset contains:

* User ratings
* Movie titles
* Movie IDs
* Tags and metadata

Files used:

```
movies.csv
ratings.csv
links.csv
tags.csv
```

Dataset source:

[https://grouplens.org/datasets/movielens/](https://grouplens.org/datasets/movielens/)

# Recommendation Method

This project uses **Item-Based Collaborative Filtering**.

### Steps

1. Load user ratings dataset
2. Create **user-item matrix**
3. Compute **cosine similarity between movies**
4. Identify movies similar to those liked by the user
5. Rank recommendations by similarity score
6. Return the **top 10 recommended movies**

# Project Structure

```
movie-recommendation
│
├── movie
│   ├── ml-latest-small
│   │   ├── movies.csv
│   │   ├── ratings.csv
│   │   ├── links.csv
│   │   └── tags.csv
│
├── model
│   ├── similarity.pkl
│   └── user_ratings.pkl
│
├── app.py
├── train_model.py
├── frontend.py
├── login.py
├── generate_meta.py
├── update_posters.py
└── README.md
```

### File Description

**app.py**
Flask API that generates recommendations for a given user.

**train_model.py**
Builds the recommendation model and computes the similarity matrix.

**frontend.py**
Handles the user interface of the recommendation system.

**login.py**
Provides user authentication functionality.

**generate_meta.py**
Processes movie metadata for recommendations.

**update_posters.py**
Fetches and updates movie posters.

# Model Training

Run the following script to train the recommendation model:

```
python train_model.py
```

This will:

* Create a user-item matrix
* Compute cosine similarity between movies
* Save trained models as:

```
model/similarity.pkl
model/user_ratings.pkl
```

# Running the Application

Start the Flask server:

```
python app.py
```

The API will run on:

```
http://127.0.0.1:5000
```

# API Endpoint

### Get Movie Recommendations

```
GET /recommend?user_id=<id>
```

Example:

```
http://127.0.0.1:5000/recommend?user_id=1
```

Example Response:

```
[
 { "title": "Interstellar", "score": 0.91 },
 { "title": "The Prestige", "score": 0.87 },
 { "title": "The Dark Knight", "score": 0.85 }
]
```

# Model Evaluation

The model is evaluated using multiple metrics.

### Metrics used

* **Precision**
* **Recall**
* **F1 Score**
* **Accuracy**

Evaluation is performed by:

1. Splitting user liked movies into train and test sets
2. Predicting recommendations
3. Comparing predicted movies with actual liked movies

# Visualization

The training script generates visualizations including:

* Bar chart of average metrics
* Precision vs Recall scatter plot
* Heatmap of item similarity

These visualizations help analyze recommendation quality.

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Flask
* Matplotlib
* Seaborn
* Pickle

# Future Improvements

* Hybrid recommendation system
* Deep learning based recommendations
* Real-time user preference learning
* Web deployment
* Improved evaluation metrics (MAP, NDCG)


Which makes it **much stronger for internships**.

---

If you want, I can also show you **3 small improvements that would make this project look much more impressive on GitHub (without changing your code much).**
