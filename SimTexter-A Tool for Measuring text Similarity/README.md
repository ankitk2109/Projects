# SimTexter: A Tool for Measuring text Similarity

Given a set of word features we have created a python dictionary target_dic which consists of 6 different targets(entities).

**Pre-processed the dictionary**

Tokenize -> Removal of stop words -> Removal of special words->Normalization -> Removing blank spaces -> Lemmatization -> Joining elements  back -> Final Processed Dictionary.


 ![image](https://user-images.githubusercontent.com/26432753/72297881-ce07ec80-3654-11ea-8f0c-acdd2e3384fd.png)

Fig: Final preprocessed dictionary

 
## Using Jaccard Index to find similarity.

The Jaccard index or Jaccard similarity coefficient compares members for two sets see which members are shared and which are distinct. It’s a measure of similarity for the two sets of data, with a range from 0% to 100%. The higher the percentage, the more similar the two populations.

Formula : J(X,Y) = |X∩Y| / |X∪Y|

Jaccard-Distance: A similar statistic, the Jaccard distance, is a measure of how dissimilar two sets are. It is the complement of the Jaccard index and can be found by subtracting the Jaccard Index from 1.

Formula : D(X,Y) = 1 – J(X,Y)

Jaccard index follow the Triangle inequality property

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

 
## Using Cosine similarity

Cosine similarity is a metric used to measure how similar the documents are irrespective of their size. Mathematically, it measures the cosine of the angle between two vectors projected in a multi-dimensional space. The cosine similarity is advantageous because even if the two similar documents are far apart by the Euclidean distance (due to the size of the document), chances are they may still be oriented closer together. The smaller the angle, the higher the cosine similarity.

The Formula is given by:

  
![image](https://user-images.githubusercontent.com/26432753/72297979-fe4f8b00-3654-11ea-85a2-9076552a187f.png)

 
1. Took 3 short documents about which you might want to know their similarity. Produce 5 variants on one of the documents and see how the cosine similarity changes. Three short docs for calculating cosine similarity are shown below.

 ![image](https://user-images.githubusercontent.com/26432753/72297984-01e31200-3655-11ea-9f7c-b35d5ee140a6.png)


2. Now pairwise similarities are calculated from get_cosine method 

Below is the output after calculating each pair cosine value.

 ![image](https://user-images.githubusercontent.com/26432753/72297992-060f2f80-3655-11ea-9922-c921249e60f4.png)


Variants of d3 doc are:


 ![image](https://user-images.githubusercontent.com/26432753/72297999-09a2b680-3655-11ea-988a-de8708f9c233.png)
 

Calculating the cosine distance of doc3 from doc4 to doc8. 

**Output:**

![image](https://user-images.githubusercontent.com/26432753/72298017-12938800-3655-11ea-8d75-98a4c56ad3e5.png)

 
All pairwise distance from each document:


![image](https://user-images.githubusercontent.com/26432753/72298027-17f0d280-3655-11ea-8555-aa63ba6dbd26.png)



![image](https://user-images.githubusercontent.com/26432753/72298033-1c1cf000-3655-11ea-90bd-ca9d58c4e4ed.png)         

 

Plot the similarity differences on a graph showing their cosine similarity score. 
The graph shows the cosine similarity score of document 3 with all other documents. The graph shows clearly that the documents are similar when the cosine score is high.

When the cosine angle between documents is less more is the similarity hence the cosine score. Hence the intuition was appropriate that when the score is less, the similarity is also low.


![image](https://user-images.githubusercontent.com/26432753/72298041-20e1a400-3655-11ea-92f8-cfc03a25e7eb.png)


Using another python package **sklearn.metrics.pairwise.cosine_similarity** that computes cosine similarity and euclidean distance.

![image](https://user-images.githubusercontent.com/26432753/72298048-250dc180-3655-11ea-8760-287426389f29.png) 


Fig1: Plot for Cosine Score                     


![image](https://user-images.githubusercontent.com/26432753/72298054-2939df00-3655-11ea-8c72-7f0f263e2028.png)


Fig2: Plot for Euclidean Distance

 

Cosine similarity of doc3 with all other documents are calculated using the library specified above. It internally calculates Term frequencies (TF) for most occurring terms using fit_transform inside CountVectorizer and then using cosine similarity function. Calculating the cosine manually and through inbuilt libraries are related but values are changing because of the tf-IDF values differ when calculated manually and via CountVectorizer. Fig 1 shows the Cosine Score.

 

Moreover, Euclidean distance is opposite to the cosine similarity. It measures the length between two sample points. It considers the magnitude whereas cosine considers the angle between the vectors.

Hence we use cosine similarity when the magnitude is not of much importance. Fig 2 shows the Euclidean distance.
