# Sentimental Analysis on Amazon Product Reviews

The major 3 questions covered by this project:
1) Taking into consideration the reviews given by reviewers, what are the main keywords that most of the reviewers use in their reviews?
2) What can we do with the keywords of Positive reviews and Negative Reviews?
3) Can review keywords help in determining which product is more loved by the viewers in comparison to others?

#### Methodology
Scrapped the data from amazon website using Selenium. Considered top 10 HP laptops from amazon since the number of reviews of these laptops were greater as compared to other laptops and HP is a big brand in today’s world. Data scrapped was usually the Reviewer name, review, Date when review was written, Location from where review was written, Ratings, etc.

#### Exploratory Data Analysis
“taking a peek” at the data to understand more about what it represents and how to apply it, we performed following steps:
1. Finding Average Ratings of Reviews
2. Checking No. of Reviews from different Countries
3. Comparing Ratings with Polarity of Laptops

#### Modelling and Data Analysis
The classification of sentiments is executed following procedures that ensure the raw data is cleaned, converted into a corpus (a collection of words) and a term document matrix (a matrix showing the frequency of words in the corpus). These objects make it easy for the classification models to learn the relationship between the words and the sentiments. The following steps explain how the entire text mining is done using machine learning. In this part, the NLTK library will be used to analyze sentiment analysis. To get the bag of words, which is a way of extracting features from text for modelling, tokenization, lemmatization and removing the punctuation, and vectorization the text is required.

#### Pre-Processing
In preprocessing, the reviews from the scraped dataset are cleaned with the help of a library called “spacy.” The reviews are tokenized using spacy and then each tokenized unigram is lemmatized to achieve the root word. When analyzing text, it is useful to extract these basic forms, which will let us extract useful statistics to analyze the input text There are many meaningless words in the English text, such as "the", "in", some short words, and some punctuation marks, which we need to remove them. These invalid words are stop words. We remove all the stop words and punctuation from the lemmatized words. The words that remain after the pre-processing are joined to form clean text which are called “Clean_Reviews”.

#### Word Cloud
One is Positive reviews; another is negative reviews and last one is neutral reviews. We are taking positive and negative reviews into consideration. We have used word cloud generator to generate the word cloud of all the reviews. Negative Keywords are slow, screen, update issues, internet and Positive Keywords are Fast, battery life, screen time, battery life, keyboard.

#### Vectorization
In the step of counting the word frequency, we will get the word frequency of all the words in the text. With the word frequency, we can use the word vector to represent the text. The vectorization method is easy to use and straightforward, but it is difficult to use in some scenarios such as the vocabulary after word segmentation is exceptionally large.

#### Support Vector Machine (SVM) and Naive Bayes Algorithm
-> Data is split into 70% for training 30% for testing. The training dataset is the sample dataset for learning, while the test dataset is the sample dataset for performance evaluation. The machine learning models implemented in this project are SVM and Naïve Bayes. The parameters of the algorithms were manually adjusted to achieve a better performance.

-> After applying the SVM and Naive Bayes, we can get the results of each model. The accuracy of the SVM model is 86%

-> The SVM model works better at predicting reviews with a positive sentiment. This difference can be observed from the above classification report where the recall for the labels ‘Negative’ and ‘Neutral’ is very less compared to ‘Positive.’ The reason is that the dataset is imbalanced with most of the comments as positive.

->  The accuracy of the Naïve Bayes model is 78%; the confusion matrix and classification report are above. The
 accuracy of Naïve Bayes is lesser when compared to SVM by a good margin and so are the precision and recall
 values. It can be observed that the naïve bayes algorithm performs worse on the minority classes and the majority
 class as well.
 
 #### Limitations
One of the main Limitations of performing sentimental Analysis on Amazon reviews is that Neutral Reviews won’t be able to contribute as it is neither a positive response nor negative response. And sometimes, some of the reviews might be labelled incorrectly i.e. review might be positive but ML algorithm might have detected it as a negative review. Also, the two columns that is review and rating might be giving opposite responses i.e. review might be negative but ratings might be 5 out of 5. Such data should be removed from the dataset but we have not consider this case. Even more problematically, most online review data is in English. For global organizations, successful reputation management requires monitoring media sources in many languages. In order to use sentiment analysis systems trained on English data exclusively, special steps must be taken that either involve costly translation of all relevant news articles and social media posts, or complex, state-of-the-art methods that allow the trained system to transfer what it has learned from one language to another.

#### Conclusion and Future Work
Future Work would be that we can make use of neutral reviews and can classify it into other two reviews i.e. either positive or negative reviews. Because it’s difficult to have a 3rd label which does not give much information about the data in the dataset. In conclusion, After getting the word cloud of positive and negative reviews, we can come to conclusion that Amazon can recommend HP to improve their products by the negative keywords mentioned in the word cloud i.e. All the 10 products can improve their update issues, slowly and with the help of positive keywords, they could recommend those products to those who are searching that kind of laptops. So, Amazon can work on Negative keywords to improve their product and can take positive keywords and recommend those products based on the search of the customers. Also, SVM and Naive Bayes Algorithm has been implemented and their results are compared to get better accuracy and precision. One of the main reason our accuracy is not high enough is because of less data we have in the dataset and the data imbalance. We tried resampling and different weighting techniques that we got from the feedbacks of the audience during the poster session. But that didn’t help too much.
