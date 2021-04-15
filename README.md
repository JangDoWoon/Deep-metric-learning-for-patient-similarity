# Patient similarity
Patient similarity measurement is a fundamental and important task in healthcare and can help you make decisions without the additional time and cost of a physician. Measuring a pair of patients based on historical information can be applied to a variety of medical applications, such as cohort analysis and personalized drug recommendations. Healthcare data EHR has high complexity, irregular, and sequential characteristics. So how to get patient similarity properly becomes a major problem. Recently, studies have been conducted mainly to measure similarities between patients through supervised learning.
# Dataset
2002-2013, using 12 years of Korean EHR data provided by NHIS. EHR data consists of medical events that occur every patient's visit. The variables you want to use consist of demographic, digest, and media.
# Flowchart
![image](https://user-images.githubusercontent.com/67357059/114868490-edca2980-9e30-11eb-8bc8-791c4602ad56.png)
# Data Preprocessing
This project assumes that patients are similar if they have the same complication of diabetes.
![image](https://user-images.githubusercontent.com/67357059/114868955-6f21bc00-9e31-11eb-86da-7072cace6fa9.png)
# Doc2Vec
Doc2vec is an NLP tool for representing documents as a vector and is a generalizing of the word2vec method. Simply put, Doc2vec combines the information in the document with Word2vec. The word2vec algorithm uses a neural network model to learn word associations from a large corpus of text. Once trained, such a model can detect synonymous words or suggest additional words for a partial sentence. As the name implies, word2vec represents each distinct word with a particular list of numbers called a vector. The vectors are chosen carefully such that a simple mathematical function (the cosine similarity between the vectors) indicates the level of semantic similarity between the words represented by those vectors.
![image](https://user-images.githubusercontent.com/67357059/114870016-a0e75280-9e32-11eb-86d8-918482705770.png)
# Siamese Network
A Siamese neural network is an artificial neural network that uses the same weights while working in tandem on two different input vectors to compute comparable output vectors.Often one of the output vectors is precomputed, thus forming a baseline against which the other output vector is compared. In our project, Give the patient pair to the CNN model as input. EHR data has sequential characteristics, so Conv1D was used to contain patient sequential information.
![image](https://user-images.githubusercontent.com/67357059/114870422-1fdc8b00-9e33-11eb-812f-0ea689253cdf.png)
# K-nearest neighbors
The training examples are vectors in a multidimensional feature space, each with a class label. The training phase of the algorithm consists only of storing the feature vectors and class labels of the training samples. In the classification phase, k is a user-defined constant, and an unlabeled vector (a query or test point) is classified by assigning the label which is most frequent among the k training samples nearest to that query point. A commonly used distance metric for continuous variables is Euclidean distance. For discrete variables, such as for text classification, another metric can be used, such as the overlap metric (or Hamming distance). In the context of gene expression microarray data, for example, k-NN has been employed with correlation coefficients, such as Pearson and Spearman, as a metric. Often, the classification accuracy of k-NN can be improved significantly if the distance metric is learned with specialized algorithms such as Large Margin Nearest Neighbor or Neighbourhood components analysis. A drawback of the basic "majority voting" classification occurs when the class distribution is skewed. That is, examples of a more frequent class tend to dominate the prediction of the new example, because they tend to be common among the k nearest neighbors due to their large number. One way to overcome this problem is to weight the classification, taking into account the distance from the test point to each of its k nearest neighbors. The class (or value, in regression problems) of each of the k nearest points is multiplied by a weight proportional to the inverse of the distance from that point to the test point. Another way to overcome skew is by abstraction in data representation. For example, in a self-organizing map (SOM), each node is a representative (a center) of a cluster of similar points, regardless of their density in the original training data. K-NN can then be applied to the SOM.
![image](https://user-images.githubusercontent.com/67357059/114870729-7944ba00-9e33-11eb-8ad5-040dc9cf0503.png)
# Conclusion - Deep Metric Learning
Patients with the same complications have a short distance. Also, the loss of the Training Set and Test Set is reduced.
![image](https://user-images.githubusercontent.com/67357059/114871103-e5272280-9e33-11eb-8732-f7b32569f1ed.png)
# Conclusion - Clustering
After KNN progression, patients without complications enter Cluster0 or ClusterN obtain the probability that the data entered ClusterN has Complications N. Put each patient in a random cluster to see if Metric Learning and Clustering are appropriate and calculate the probability.
![image](https://user-images.githubusercontent.com/67357059/114871349-2a4b5480-9e34-11eb-89c2-64339486ed2f.png)
# Code detail
*Clustering.ipynb is the code about Clustering after clustering
*Complication_labeling.ipynb is the code about complication labeling before doc2vec
*embedding_doc2vec.ipynb is the code about doc2vec fot each patient visit
*siamese_model.ipynb is the code about siamese network model to get the similarity about patient
*similarity_labeling.ipynb is the code about similarity labeling about pair patient
# References
*Koch, Gregory, Richard Zemel, and Ruslan Salakhutdinov. "Siamese neural networks for one-shot image recognition." ICML Deep Learning Workshop. Vol. 2. 2015.
