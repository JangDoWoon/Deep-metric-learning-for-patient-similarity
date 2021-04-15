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
