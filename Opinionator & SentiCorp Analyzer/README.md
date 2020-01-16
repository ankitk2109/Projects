# Sentiment Analysis
  
### Following Tasks are performed. Also the accuracy is measured by removing stop words, normalizing, changing classifier and Increasing training set.

**Task1. Human Ratings Task:**

a)Get 3 opinion about the phone.

b)Get 3 different raters to rate these comments as positive, negative, neutral or can’t-say.

c)Take a 3 x 3 matrix and find the inter-rater reliability between your 3 raters using Kappa.

d)If we want to get the correlation between raters (using Pearson’s rho) what should we do?

Ans. Below are the opinions of three different people about there phone:
op1 = "Audio from this phone is merely OK and this seems to be a side-effect of having basically no room for speakers."

op2 = "The S Pen is the true headline feature for the Note series and it is pretty much the only flagship around that lets you draw and take notes with a pen on the display."

op3 = "Samsung has finally ditched the headphone jack from the Note’s design, meaning you’ll have to rely on wireless headphones or a pair with a USB-C connection."

a)Ratings are coded as shown,
Positive Rating : 1, Neutral Rating : 0, Negative Rating: -1 
The opinions are rated as below by three different raters.

![image](https://user-images.githubusercontent.com/26432753/72351072-91310980-36d7-11ea-94d0-839ce105c28f.png)


b)Inter-rater reliability: It is the degree of agreement among raters. It gives a score of how much homogeneity, or consensus, there is in the ratings given by judges[1].

Cohen's kappa coefficient (κ): It is a statistic that is used to measure inter-rater reliability (and also Intra-rater reliability) for categorical items. It is generally thought to be a more robust measure than simple percent agreement calculation, as κ takes into account the possibility of the agreement occurring by chance[2].

![image](https://user-images.githubusercontent.com/26432753/72351117-a1e17f80-36d7-11ea-8148-a5fe5ef70a91.png)

Po: Probability of observed Agreement
Pe: Probability of chance agreement

Below are the matrix that are being created for different pairs.

![image](https://user-images.githubusercontent.com/26432753/72351156-b3c32280-36d7-11ea-870a-3ba982eeee8e.png)

![image](https://user-images.githubusercontent.com/26432753/72351200-c89fb600-36d7-11ea-82e3-34eb1efba728.png)



The cohen kappa score is calculated as in python using sklearn. The values for each pair is shown below:

![image](https://user-images.githubusercontent.com/26432753/72351226-da815900-36d7-11ea-880d-0322538c97da.png)

As shown above, Inter-rater reliability for Rater 1 and Rater 2 is 0.5 which signifies that there is moderate agreement between the them. Rater 1 and Rater 3 have have cohen kappa value quals to 0, which signifies that there is slight agreement between these two. Rater 2 and Rater 3 have K = -0.5 which means there is no agreement between them.
Below is the matrix for kappa score of each opinion.

![image](https://user-images.githubusercontent.com/26432753/72351239-e240fd80-36d7-11ea-9816-6a2952bc2c4b.png)


c)Pearson’s rho: It is a measure of the strength of a linear association between two variables and is denoted by rho(r)[3].
It can take a range of values from +1 to -1.
A value of 0 indicates that there is no association between the two variables.
A value greater than 0 indicates a positive association that is, as the value of one variable increases, so does the value of the other variable.
A value less than 0 indicates a negative association; that is, as the value of one variable increases, the value of the other variable decreases.

![image](https://user-images.githubusercontent.com/26432753/72351260-f1c04680-36d7-11ea-9293-c4876b3e99c7.png)


Pearson’s Correlation Coefficient is given by:

![image](https://user-images.githubusercontent.com/26432753/72351313-03a1e980-36d8-11ea-8c9a-3354310761dc.png)


As shown above, Pearson correlation for Rater 1 and Rater 2 is 0.0 which signifies that there is no correlation between the them. Rater 1 and Rater 3 have have correlation equals to 0.86, which signifies that there is a positive correlation between these two. Rater 2 and Rater 3 have -0.49 which means there is negative correlation between them.

**Task2.  Based on this simple program that does sentiment analysis. **

a)Now considering a ways to improve the training by remove stopwords, changing classifier or increasing training set.

b) Implementing this or another solution in the program and measuring how precision and recall changes for the classifier.

Ans: The program does the following[6]:
i.Firstly we read sentences from two files which are already classified as positive and negative based on sentiments.
ii.We split the sentences based on lines.
iii.Now we break the sentences into lists of individual words as we would be analyzing the sentiments based on words. Also we create features ‘posFeatures’ and ‘negFeatures’ which consists of collection of positive and negative words along with the tags.
iv.The next step is to divide the features into training and testing sets.
v.Once that done we train the classifier on the training set.
vi.After the classifier is trained we predict the labels for the test set.
vii.Finally we evaluate the parameters such as accuracy of classifier, precision and recall for both positive and negative sets. 
a)Ways to improve the training:
i.We can remove the stops words.
ii.We can try changing the classifier.
iii.We can change the training and testing size.
b)Implementation:
i.Removing the stop words:

![image](https://user-images.githubusercontent.com/26432753/72351732-cee26200-36d8-11ea-92b8-ded123452596.png)

Since removing the stopwords, the reliability of this system is slightly reduced relative to that without eliminating stopwords because the meaning is the primary focus of semantic analysis.
So if the stopwords are removed the meaning shifts and therefore the precision reduces.  The precision for positive decreases whereas recall gets increased. Similarly for the, precision increases with minute difference but the recall gets decreased.

ii.Changing Classifier:
iii.

![image](https://user-images.githubusercontent.com/26432753/72351765-de61ab00-36d8-11ea-964c-a7cf1968e543.png)


The Classifier is changed to Support Vector Machine(SVM) but still the accuracy of the model is low as compared to that of Naive Bayes Classifier.The precision,recall for positive gets decreases.Also precision and recall for the negative gets decreased.

iv.Increasing Training set size.

![image](https://user-images.githubusercontent.com/26432753/72351805-f3d6d500-36d8-11ea-89ae-cee29b4bd83e.png)


If we increase the training set from 75% to 90%, accuracy gets increased to 79.02% with increase in precision and decrease in recall in case of positive. For the negative, precision slightly increases but recall goes to 80%

