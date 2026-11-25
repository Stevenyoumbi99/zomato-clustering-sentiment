# Zomato Restaurant Clustering and Sentiment Analysis

This is the project I built during my Labmentix internship (Data Science with AI). I worked on Zomato data for restaurants in Hyderabad, India, and tackled two problems: grouping restaurants into meaningful segments, and predicting whether a customer review is positive or negative.

## What I did

### Restaurant clustering

I grouped 100 restaurants into 5 segments using K-Means:

1. **Casual hangouts**
2. **Budget quick bites**
3. **Top-rated stars**
4. **Mid-range all-rounders**
5. **Premium multi-cuisine dining**

I also ran hierarchical clustering to compare the results and check that the segments held up with a different method.

### Sentiment analysis

I turned the review text into features with TF-IDF and trained a tuned Logistic Regression model to classify reviews as positive or negative. It reached **96.2% accuracy** and a **0.993 ROC-AUC** on the test set.

## The data

I used 2 datasets:

- **Zomato Restaurant names and Metadata.csv**: 105 restaurants with their estimated cost per person, cuisines, collections and links
- **Zomato Restaurant reviews.csv**: 10,000 reviews with the reviewer, rating, review text and timing

## Main steps

- **Data cleaning**: fixing data types, handling missing values and duplicates, and merging the two datasets
- **EDA**: 18 charts to understand costs, cuisines, ratings and review behaviour
- **Cost by cuisine**: comparing the cost per person across the most common cuisines
- **Best restaurant for each cuisine**: finding the 3 best rated restaurants for each of the 6 most common cuisines
- **Identifying the critics**: spotting the reviewers with 1,000+ followers, since their opinion reaches a lot of people
- **Hypothesis testing**: statistical tests to check a few assumptions I made during the EDA
- **Feature engineering**: encoding categorical features, log transforming skewed columns, scaling, and reducing dimensions with PCA
- **Text preprocessing**: expanding contractions, lowercasing, removing punctuation and stopwords, and lemmatizing. I made sure to keep negation words like "not" and "never", since removing them would flip the meaning of a lot of reviews
- **Models**: K-Means and hierarchical clustering for the restaurants, and a Logistic Regression model for sentiment that I tuned with GridSearchCV
- **Visualizing the clusters**: plotting the restaurants on the first 2 PCA components to see how the 5 segments separate
- **A strategy for each segment**: practical ideas for how Zomato could work with each type of restaurant
- **Explainability**: looking at which words push a review towards positive or negative, and what makes each cluster different
- **Saving the models**: both final models are saved with joblib (`zomato_clustering_model.joblib` and `zomato_sentiment_model.joblib`)

## Project files

- `Zomato_Clustering_Sentiment.ipynb`: the full notebook
- `Zomato Restaurant names and Metadata.csv` and `Zomato Restaurant reviews.csv`: the datasets
- `zomato_clustering_model.joblib` and `zomato_sentiment_model.joblib`: the saved models
- `Zomato_Clustering_Sentiment_Presentation.pptx`: my presentation of the project
- `requirements.txt`: the Python packages I used

## Presentation

I also made a presentation of the project: `Zomato_Clustering_Sentiment_Presentation.pptx`. It has 18 slides, and the script I used for the video is in the speaker notes.

## How to run it (Windows)

Clone the repo, open a terminal in the project folder, and run:

```
python -m venv .venv
.venv\Scripts\activate
python -m pip install -r requirements.txt
```

Then open `Zomato_Clustering_Sentiment.ipynb` in Jupyter or VS Code, select the `.venv` kernel, and click **Run All**.

## Author

YOUMBI NJANDA Steven Alan
