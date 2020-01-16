# Similarity

**Following tasks are performed on set of word features.**

**Task 1) Make up your own set of word features describing 6 different entities; with some obvious overlaps and differences.**

 

1.Modify the Jaccard-Index python program to do Jaccard-Distance and then compute all pairwise distances between the entities.
Based on results, show empirically, that the property of triangle inequality holds for the measure.

 

Ans. I have created a python dictionary target_dic which consists of 6 different targets(entities).
Pre-processed the dictionary tokenize -> Removal of stop words -> Removal of special words->Normalization -> Removing blank spaces -> Lemmatization -> Joining elements  back -> Final Processed Dictionary.

 ![image](https://user-images.githubusercontent.com/26432753/72297881-ce07ec80-3654-11ea-8f0c-acdd2e3384fd.png)

Fig: Final preprocessed dictionary

 

Jaccard-Index: The Jaccard index or Jaccard similarity coefficient compares members for two sets see which members are shared and which are distinct. It’s a measure of similarity for the two sets of data, with a range from 0% to 100%. The higher the percentage, the more similar the two populations. [1].

Formula : J(X,Y) = |X∩Y| / |X∪Y|

 

Jaccard-Distance: A similar statistic, the Jaccard distance, is a measure of how dissimilar two sets are. It is the complement of the Jaccard index and can be found by subtracting the Jaccard Index from 1[1].

Formula : D(X,Y) = 1 – J(X,Y)

 

Triangle Inequality: The sum of any two sides of a triangle is greater than or equal to the third side; in symbols, a + b ≥ c[2].
 

Formula: ||x|| + ||y|| ≥ ||x + y||.

Modified function to calculate Jaccard-Distance.

 ![image](https://user-images.githubusercontent.com/26432753/72297894-d3fdcd80-3654-11ea-9fab-6d8f35ea8e97.png)

After calculating the pairwise distance, the following is the result.

 ![image](https://user-images.githubusercontent.com/26432753/72297902-d8c28180-3654-11ea-9a85-96cd4ebb3730.png)

Here dis1_2, show the distance between target1 and target2. Similarly rest all distance are calculated above.

Jaccard Distance holds triangle inequality property for each pair. The code snippet below shows the calculation for a few of the pairs.

 ![image](https://user-images.githubusercontent.com/26432753/72297911-dd873580-3654-11ea-9577-613d59e4c1ed.png)

Above we are calculating Jaccard-distance between pairs. It can be seen that the pair satisfies triangle inequality theorem.

 

2.Now implement the difference function for the Dice Coefficient and show that the property of triangle inequality may not hold for this measure.
Ans: Dice Coefficient: |X| and |Y| are the cardinalities of the two sets (i.e. the number of elements in each set). The Sørensen index equals twice the number of elements common to both sets divided by the sum of the number of elements in each set.

 ![image](https://user-images.githubusercontent.com/26432753/72297935-e972f780-3654-11ea-8f2b-1653888d13c1.png)


Dice coefficient distance is calculated by,

 ![image](https://user-images.githubusercontent.com/26432753/72297940-ed9f1500-3654-11ea-9b06-7289ccabf510.png)


But it is not a proper distance metric as it does not possess the property of triangle inequality.

I have calculated the pairwise Dice coefficient distance, the following is the result.


![image](https://user-images.githubusercontent.com/26432753/72297958-f2fc5f80-3654-11ea-855b-63159fba5e06.png)

 
Triangle inequality doesn’t possess by Dice distance and it can be proved by looking at below output.


![image](https://user-images.githubusercontent.com/26432753/72297964-f7c11380-3654-11ea-9543-e0f12f0af75d.png)

 
**Task2. Have a look at the Cosine.py program; nb you may need to install the packages its imports.**

Ans: Cosine Similarity: Cosine similarity is a metric used to measure how similar the documents are irrespective of their size. Mathematically, it measures the cosine of the angle between two vectors projected in a multi-dimensional space. The cosine similarity is advantageous because even if the two similar documents are far apart by the Euclidean distance (due to the size of the document), chances are they may still be oriented closer together. The smaller the angle, the higher the cosine similarity[3].

The Formula is given by:

  

![image](https://user-images.githubusercontent.com/26432753/72297979-fe4f8b00-3654-11ea-85a2-9076552a187f.png)

 

1. Find 3 short documents about which you might want to know their similarity. Produce 5 variants on one of the documents and see how the cosine similarity changes.
Ans: three short docs for calculating cosine similarity.

 ![image](https://user-images.githubusercontent.com/26432753/72297984-01e31200-3655-11ea-9f7c-b35d5ee140a6.png)


2. Now pairwise similarities are calculated from get_cosine method from cosine.py file. For eg., cosine similarity between doc1 and doc2 is calculated then doc1 and doc3 and so on.

Below is the output after calculating each pair cosine value.

 ![image](https://user-images.githubusercontent.com/26432753/72297992-060f2f80-3655-11ea-9922-c921249e60f4.png)


Variants of d3 doc are:


 ![image](https://user-images.githubusercontent.com/26432753/72297999-09a2b680-3655-11ea-988a-de8708f9c233.png)
 

Calculating the cosine distance of doc3 from doc4 to doc8. Below is the python function that is used to calculate the cosine similarity and the output produce after pairwise comparison.

 ![image](https://user-images.githubusercontent.com/26432753/72298010-0dced400-3655-11ea-8808-31b852919b2f.png)


Output:



![image](https://user-images.githubusercontent.com/26432753/72298017-12938800-3655-11ea-8d75-98a4c56ad3e5.png)

 

All pairwise distance from each document:



![image](https://user-images.githubusercontent.com/26432753/72298027-17f0d280-3655-11ea-8555-aa63ba6dbd26.png)



![image](https://user-images.githubusercontent.com/26432753/72298033-1c1cf000-3655-11ea-90bd-ca9d58c4e4ed.png)         

 

Plot the similarity differences on a graph showing their cosine similarity score. Verify that your intuitions about what makes the differing docs less similar do indeed lead to less similar scores.
Ans: The graph shows the cosine similarity score of document 3 with all other documents. The graph shows clearly that the documents are similar when the cosine score is high.

When the cosine angle between documents is less more is the similarity hence the cosine score. Hence the intuition was appropriate that when the score is less, the similarity is also low.


![image](https://user-images.githubusercontent.com/26432753/72298041-20e1a400-3655-11ea-92f8-cfc03a25e7eb.png)


Find a python package that computes cosine similarity and euclidean distance. Use it process the data you have already. Do the answers for Cosine Similarity correspond? What do the Euclidean Distance scores look like relative to the Cosine ones?
Ans: Package for cosine similarity: sklearn.metrics.pairwise.cosine_similarity

Package for euclidean distance: sklearn.metrics.pairwise.cosine_similarity


![image](https://user-images.githubusercontent.com/26432753/72298048-250dc180-3655-11ea-8760-287426389f29.png) 


Fig1: Plot for Cosine Score                     



![image](https://user-images.githubusercontent.com/26432753/72298054-2939df00-3655-11ea-8c72-7f0f263e2028.png)


Fig2: Plot for Euclidean Distance

 

Cosine similarity of doc3 with all other documents are calculated using the library specified above. It internally calculates Term frequencies (TF) for most occurring terms using fit_transform inside CountVectorizer and then using cosine similarity function. Calculating the cosine manually and through inbuilt libraries are related but values are changing because of the tf-IDF values differ when calculated manually and via CountVectorizer. Fig 1 shows the Cosine Score.

 

Moreover, Euclidean distance is opposite to the cosine similarity. It measures the length between two sample points. It considers the magnitude whereas cosine considers the angle between the vectors.

Hence we use cosine similarity when the magnitude is not of much importance. Fig 2 shows the Euclidean distance.

 

**Task3. Create or find 5 “normal” tweets from Twitter. Now take one of these tweets and systematically generate 20 SPAM tweets from it; using the typical techniques of spammers. Now, perform comparisons between these 20 SPAM tweets each of the 5 Normal Tweets. Plot their edit-distance scores in a graph and colour code to show how the SPAM v Normal ones. Are the SPAM tweets obvious, if not why?**

Ans: Tweets:


![image](https://user-images.githubusercontent.com/26432753/72298061-30f98380-3655-11ea-86bb-af436cc3b0df.png)

 

Based on tweet4 20 spam tweets are created.


 ![image](https://user-images.githubusercontent.com/26432753/72298074-3525a100-3655-11ea-9c4a-2f59ec88f28c.png)

 
All the normal and spam tweet are preprocessed using the usual procedure as mentioned in question 1 above.

Levenshtein Distance: It is a string metric for measuring the difference between two sequences.

The Levenshtein distance is calculated between normal and spam tweets and the result is shown below.


![image](https://user-images.githubusercontent.com/26432753/72298086-3951be80-3655-11ea-9996-caf629415fc6.png)



![image](https://user-images.githubusercontent.com/26432753/72298106-41116300-3655-11ea-9590-1e4cd0af6683.png)

                         

The plot for Levenshtein distance between normal and spam tweet is shown below.

 

 ![image](https://user-images.githubusercontent.com/26432753/72298113-466ead80-3655-11ea-81f8-cfc5b9078ff5.png)

 

Looking at the graph above it can be seen that spam tweets are related to normal tweet t4 as it shows it requires a minimum number of transformation to achieve maximum similarity measure.

 

 

References:

S.Glen, “Jaccard Index / Similarity Coefficient”, 2, December 2016 [Online]. Available: https://www.statisticshowto.datasciencecentral.com/jaccard-index/. [Accessed Oct. 19, 2019]
L. Hosch, “Triangle inequality”,18, August 2009 [Online]. Available: https://www.britannica.com/science/triangle-inequality. [Accessed Oct. 19, 2019]
S.Prabhakaran, “Cosine Similarity – Understanding the math and how it works (with python codes)”, 16, May 2019[Online]. Available: https://www.machinelearningplus.com/nlp/cosine-similarity/. [Accessed Oct. 19, 2019]
 
