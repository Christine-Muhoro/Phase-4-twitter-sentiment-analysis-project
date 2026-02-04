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
## **Data Understanding**
The dataset being used is a set of tweets about Apple and Google products evaluated by some contributors. The crowd was asked if the tweet expressed positive, negative, or no emotion towards the brand and/or product. If some emotion was expressed they were also asked to say which brand or product was the target of that emotion.  
This dataset contains 9093 data rows of tweets. It contains the tweets, the product/company and the sentiments.
## **Data Cleaning and Preprocessing**
The dataset had 22 duplicated entries and 1 sentiment without a text attached to it which were dropped. The `product/company` column was dropped too because it had too many missing values. There were also 156 sentiments classified as uncertain dropped since they added a lot of noise to our modeling process. We cleaned the text by converting it to lovercase, removing URLs, mentions, hashtags, punctuations and numbers.  
For preprocessing, we've used: a `RegexpTokenizer` for tokenization, stopwords removal, lemmatization using `WordNetLemmatizer`.  
## **Exploratory Data Analysis**
A countplot for sentiment distribution 

![Sentiment distribution](https://github.com/user-attachments/assets/90e77b5a-fc20-4b50-a979-f7ae6ce0c283)


A wordcloud for each sentiment

![Wordcloud](https://github.com/user-attachments/assets/abf7987a-a1b7-4b7b-8a3e-a9f5c8dbbafe)

## **Modeling and Evaluation**
### **Binary Classifier**(Positive and Negative Sentiments)
Trained a logistic regression model,a random forest, a multinomial naive bayes model and a linearSVC model. According to the following results, the random forest model performed best with a higher accuracy, recall and F1 score.

![binary model](https://github.com/user-attachments/assets/7c702626-bd72-4845-818c-e43c6d5f0d88)

### **Multiclassifier Modeling**(Positive,Negative and Neutral Sentiments)
Trained a logistic regression model,a random forest, a multinomial naive bayes model, a linearSVC model and a XGBoost model. According to the following results, the random forest model performed best with a higher accuracy, recall and F1 score.

![multi class models](https://github.com/user-attachments/assets/fbd4c1ef-fac9-4edb-bbe9-01ee0dff0aa7)

## **Recommendations**
## **Conclusions**
