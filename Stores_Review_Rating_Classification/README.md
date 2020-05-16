# SCRAPPING CONSUMER REVIEWS AND CLASSIFICATION

Website to scrape review from: http://mlg.ucd.ie/modules/yalp/

### Task 1.
* Selecting any three review categories. Scraping all reviews for each category and storing them as three separate datasets. For each review, we have stored the review text and a class label (i.e. whether the review is “positive” or “negative”).

### Task 2.

* For each of the three category datasets, we have loaded the data and applied appropriate pre-processing mentioned below:

__1. Lemmatization:__

There are two popular approach for finding out the base form of a word:
  i. Stemming 
  ii. Lemmatization

The goal of both stemming and lemmatization is to reduce inflectional forms and sometimes derivationally related forms of a word to a common base form.

However, the two differ in their flavor. __Stemming__ usually refers to a crude heuristic process that chops off the ends of words in the hope of achieving this goal correctly most of the time, and often includes the removal of derivational affixes. __Lemmatization__ usually refers to doing things properly with the use of a vocabulary and morphological analysis of words, normally aiming to remove inflectional endings only and to return the base or dictionary form of a word, which is known as the lemma.

__2. StopWord Removal:__

Stop words are basically a set of commonly used words in any language. Determiners(the, an, a), Coordinating conjunctions(for, an, nor, but), Prepositions(in, under, towards, before) are majorly considered as stop words.

Why to remove?
    
* They don't help us to find the context or the true meaning of a sentence. These are words can be removed without any negative consequences to the final model. Also removing these word decreases the dataset size as they are used very frequently and do not convey any meaning.



__3. Minimum Document Frequency:__

`min_df` is used for removing terms that appear too infrequently.

* `min_df` = 0.01 means ignore terms that appear in less than 1% of the documents.

* `min_df = 10` means ignore terms that appear in less than 10 documents.

* The default `min_df is 1`, which means "ignore terms that appear in less than 1 document". Thus, the default setting does not ignore any terms.

__4. TF-IDF Vectorization:__

`Tf-idf` stands for term frequency-inverse document frequency, and tf-idf weight is a weight mostly used for information extraction and text mining. This weight is a mathematical method used to determine the value of a term in a list or corpus text. Importance decreases in relation to the amount of times a term occurs in the text, which is offset by the occurrence of the term in the corpus.

Rather than using `countVectorizer` to convert a collection of text documents to a matrix of token counts and then applying idf to find `tf-idf` we can form matrix directly using __TfidfVectorizer__.

* Also classifier evaluation is done using the following:
  1. Confusion Matrix
  2. Cross Validation
  3. Repeated K-Folds

### Task 3.

* Evaluate the performance of each of your three classification models when applied to data from the other two selected categories. That is, for the selected categories (A,B,C), running the experiments.


## Conclusion

* With the aid of BeautifulSoup, a huge amount of reviews from Automotive, Hotels and Restaurants was scrapped. Initially, all key links are retrieved using the fetch all feature of the scraper, from which the 3 chosen group links are placed in the list for further reference.

* For each main group, the request.get() method retrieves the links via the 'a' suffix. Further contents of the href tags are being fetched. In addition, for each category, all contents are scrapped using BeautifulSoup() and the reviews are collected using 'p' tags.

* Based on the number of ratings, the target class is chosen for each review and each review, along with its target class, is saved in a csv file. A number of pre-processing steps are also taken in the context of text reviews:
    * Lemmatization
    * Stop word removal
    * Minimum document frequency
    * TF-IDF
    
* After this the Logistic Regression model is built for each category and measures the success of each category via the Confusion matrix and portrays the incorrectly labeled reviews.

* Next, training the model for each category serving as a training dataset and checking its performance against the other two categories is evaluated.

* The Logistic Regression classification model appears to be the most powerful of the three classification models. Also, the efficiency of every model is measured using a variety of techniques such as confusion matrix, K Fold cross validation and Repeated fold cross validation.
