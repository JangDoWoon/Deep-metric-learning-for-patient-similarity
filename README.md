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
# Conclusion - Deep Metric Learning
Patients with the same complications have a short distance. Also, the loss of the Training Set and Test Set is reduced.
![image](https://user-images.githubusercontent.com/67357059/114871103-e5272280-9e33-11eb-8732-f7b32569f1ed.png)
# Conclusion - Clustering
After KNN progression, patients without complications enter Cluster0 or ClusterN obtain the probability that the data entered ClusterN has Complications N. Put each patient in a random cluster to see if Metric Learning and Clustering are appropriate and calculate the probability.
![image](https://user-images.githubusercontent.com/67357059/114871349-2a4b5480-9e34-11eb-89c2-64339486ed2f.png)
# Code detail
```
Clustering.ipynb is the code about Clustering after clustering
Complication_labeling.ipynb is the code about complication labeling before doc2vec
embedding_doc2vec.ipynb is the code about doc2vec fot each patient visit
siamese_model.ipynb is the code about siamese network model to get the similarity about patient
similarity_labeling.ipynb is the code about similarity labeling about pair patient
```
# References
Koch, Gregory, Richard Zemel, and Ruslan Salakhutdinov. "Siamese neural networks for one-shot image recognition." ICML Deep Learning Workshop. Vol. 2. 2015.
