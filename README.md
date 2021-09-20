# Trip-Advisor-Hotel-Review-Analysis-Sentiment-Prediction
A NLP cum Machine Learning Project which involves building a predictive Classification model and analyzing reviews of differnet sentiments.

Business Problem: Trip Advisor is a platform where millions of travellers post reviews for hotels that they stay in. Trip Advisor is one of the go-to platforms for travellers to decide which hotel to stay at based on comparison of hotels using ratings and reviews. The higher the ratings and more positive the reviews, the better the chance of a hotel being at the top of the recommendations for the viewer and being selected. However, lack of positive interviews or lower ratings could push the hotel down in the search results or prove unfavourable to its chances of being selected.

Approach: To create a classification model to predict the overall rating or sentiment of the reviews. Also, based on the analysis of different types of reviews i,e positive, negative, etc, identify the factors related to the hotel that could have an impact on the satisfaction of its customers, which could in turn affect the ratings and reviews given.

Dataset: To solve the following business problem, the dataset has been downloaded from Kaggle. It was updated by Larxel. To view and download the dataset, click the link - https://www.kaggle.com/andrewmvd/trip-advisor-hotel-reviews

During the Project, the following tasks were performed :

*Data Understanding*
- We had 20000 records and 2 columns i.e Review and Ratings.
- Due to processing and memory allocation issues, 15000 of the 20000 records were taken.
- No missing values

*Text Preprocessing*
- In order to process the reviews and prepare it for model building, we performed several text processing tasks.
- Unnecessary characters and numbers were removed.
- Stopwords (excluding negative words) were removed.
- Accented words were modified to english.
- Unnecessary spaces were also taken out.
- Words in reviews were lemmatized due to need to calculate sentiment scores, which uses a english corpus, which needs valid and existing english words from the sentences.

*Exploratory Data Analysis*
- Majority of the ratings given were positive.
- Most of the sentiments scores calculated were between 0.10 to 0.50, indicating above average to positive sentiments conveyed through reviews.
- On mapping sentiment scores with ratings using boxplots and distribution plots, we could see a lot of overlapping of distributions for several ratings like 1 and 2 & 4 and 5.
- It was concluded that differentiating between reviews on a 5-scale rating was difficult. Hence, a 3 scale review sentiment category was built, were sentiments for review would be classified as positive, negative or neutral.

*Model Building**
- Data was split into train and test
- Count Vectorizer and TF-idf vectorizers were used to transform the reviews into numerical format for models to process.
- Logistic regression and naive bayes models were used.
- Macro F1 along with cross validation scores was looked at during initial model comparison due to understand model performance and stability.
- Logistic regression created using count vectorized train sample was giving the best results with f1 macro score of 0.78 macro f1 score on test.
- Further hyperparameter tuning of count vectorizer parameters like ngrams, min-df, etc was done using a customer grid search to improve macro recall scores as our target is not identify as many negative reviews as possible.
- Logistic regression using tuned count vectorizer improve recall score of negative reviews from 0.63 to 0.64
- Final tuned model gave a macro f1 score of 0.79 and macro recall score of 0.83.
- Deviation in recall macro scores during cross validation was only 0.2%, indicating a very stable model.

*Review Analysis*
- Reviews were seperated based on their category i.e positive , negative or neutral and reviews within each category were analyized.
- Use of Parts of Speech tagging and Named entity recognition were used to find only the adjective and nouns related to the hotel.
- Within negative reviews, people had commonly criticized room aspects such as cleanniness, water, bathroom or floor 
- Many had also mentioned about the customer service and staff.
- Within positive reviews, many had mentioned about the food, location, friendly staff and aspects of room such as its space & cleanniness.

