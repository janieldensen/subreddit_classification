# Project 3
### Subreddit Classification
## Problem Statement
This project aims to build multiple clasification models that can separate r/NFL and r/soccer reddit posts. These models will be useful for anyone that's confused about which side of the Atlantic Ocean they're currently on. It will also clear up any confusion one might have when reading a discussion about football. The project specifically uses a random forest model and a support vector machine to classify posts as belonging to either subreddit.
## Data
The project uses the [Pushshift Reddit API](https://github.com/pushshift/api) to pull 100 posts from each subreddit per day from the first two weeks of October 2022. 
* [`October_1-14.csv`](./data/October_1-14.csv) Post titles and selftext.
|Feature|Type|Description|
|---|---|---|
|subreddit|object|Categorical variable for which subreddit the post was on|
|self_text|object|Text of post (not present for most links)|
|title|object|Post titles|
## Images
One picture from https://www.si.com/soccer/2022/07/07/cristiano-ronaldo-transfer-options-man-united-chelsea-napoli-bayern-munich.
## Processing
Any missing data is replaced with empty strings. Then, uses sklearn's CountVectorizer to process text into useable data for modeling. 
## Random Forest Model
This random forest classifier is made using a gridsearch to find the optimal number of estimators and maximum depth. This model is 93% accurate on the test data.
## Support Vector Machine Model
This svm is constructed with gridsearch to find the best regularization strength. It has an accuracy of 91.7%.
## Conclusion
Overall, the random forest model produces the most accurate results. Both models perform well above the basline of 50%. 