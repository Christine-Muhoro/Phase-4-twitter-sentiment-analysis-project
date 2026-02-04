# **Twitter Sentiment Analysis Group Project**
## **Business Understanding**
### **Overview**
This project aims to build NLP models that can predict the sentiment of tweets for Apple and Google products as either positive, negative or neutral.

The NLP base model will be a binary classifier focusing on the positive and negative reviews and will expand into a multiclass classifier capturing neutral sentiment reviews.

This will aid the companies in collection of reviews for their products and build or improve said products from the reviews.
### **Business Problem and Stakeholders**
Marketing and Branding teams at technology companies such as Apple and Google rely heavily on public feedback to shape brand strategies. Social media platforms such as twitter provide a large source of customer feedback that is difficult to analyze manually due to the nature of tweets(text). The business problem for this project is the need for a system that can accurately classify the sentiment of tweets towards the products as positive, negative or neutral.  
By automatically identifying changes in public sentiments, marketing brands and teams can track brand perception and respond more quickly to customer feedback. The model will support data-driven branding decisions by transforming raw tweets into actionable sentiment insights.
### **Objectives**
#### **Main Objective**
Build a model that can rate the sentiment of a Tweet based on its content.
#### **Specific Objectives**
1. Develop an automated sentiment classification system that accurately labels tweets about Apple and Google products as positive, Negative or neutral.
2. Preprocess and transform raw Twitter text data into a structured format suitable for machine learning.
3. Train and evaluate multiple NLP models to identify the most effective approach for sentiment classification based on performance metrics such as accuracy, precision, recall, and F1-score.
## **Data Understanding**
The dataset being used is a set of tweets about Apple and Google products evaluated by some contributors. The crowd was asked if the tweet expressed positive, negative, or no emotion towards the brand and/or product. If some emotion was expressed they were also asked to say which brand or product was the target of that emotion.  
This dataset contains 9093 data rows of tweets. It contains the tweets, the product/company and the sentiments.
## **Data Cleaning and Preprocessing**
The dataset had 22 duplicated entries and 1 sentiment without a text attached to it which were dropped. The `product/company` column was dropped too because it had too many missing values. There were also 156 sentiments classified as uncertain dropped since they added a lot of noise to our modeling process. We cleaned the text by converting it to lovercase, removing URLs, mentions, hashtags, punctuations and numbers.  
For preprocessing, we've used: a `RegexpTokenizer` for tokenization, stopwords removal, lemmatization using `WordNetLemmatizer`.  
## **Exploratory Data Analysis**
A countplot for sentiment distribution![A countplot for sentiment distribution](images/Countplot.jpg)
A wordcloud for each sentiment![A wordcloud for each sentiment](images/Wordcloud.jpg)
## **Modeling and Evaluation**
### **Binary Classifier**(Positive and Negative Sentiments)
Trained a logistic regression model,a random forest, a multinomial naive bayes model and a linearSVC model. According to the following results, the random forest model performed best with a higher accuracy, recall and F1 score.
![Binary evaluation results](images/Binary_models.jpg)
### **Multiclassifier Modeling**(Positive,Negative and Neutral Sentiments)
Trained a logistic regression model,a random forest, a multinomial naive bayes model, a linearSVC model and a XGBoost model. According to the following results, the random forest model performed best with a higher accuracy, recall and F1 score.
![Multiclass evaluation results](images/Multi_class_models.jpg)
## **Recommendations**
1. We built a binary classifier for positive and negative sentiment. We recommend deploying this model in marketing and branding systems for twitter feedback analysis.
2. The multi classifier has an accuracy of 67% which is a bit low due to unclear classification of the neutral sentiment. We recommend finding better strategies for training this model in the future.
3. Classification was done using the tweet itself. Incorporating additional features such as emojis, hashtags and user engagement metrics (like, retweets) would improve sentiment classification performance.

## **Conclusion**
This project successfully addressed the tasked of sentiment analysis by building and evaluating machine learning models for both binary and multi class sentiment classification.

Through effective data preprocessing, feature extraction and model evaluation, the approach was able to accurately identify sentiment patterns within twitter texts.

This analysis helps organisations understand public opinion and customer feedback, enabling data-driven decisions that improve brand engagement and strategic planning.