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
