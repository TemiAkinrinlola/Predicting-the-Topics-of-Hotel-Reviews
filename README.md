# Predicting-the-Topics-of-Hotel-Reviews
## Motivation

We live in the Information Age which as indicated by Wikipedia is a period in mankind's history portrayed by the move from mechanical creation to one dependent on the abundance of data .Thanks to the Information Age, the creation and propagation of documents is ever increasing. This document proliferation has forged a situation where we must integrate innovative technologies to be able to manage and handle the enormous volume of electronic documents on a day-to-day basis. 
Processing these documents typically necessitates utilizing our intellectual abilities to carry out the tasks of analysis, classification, modifications and deductions. However, as humans, we cannot feasibly carry out these tasks on the ever-escalating volume of unstructured text that is being produced. In an attempt to address this problem, several techniques are being developed. One of which is the technique of topic modeling.

Topic Modeling is an unsupervised machine learning technique effective at searching a collection of documents, rooting out words and phrasal patterns within them and instinctively grouping word and related phrases that best characterizes a set of documents. Topic modeling differs from topic classification, in the sense that, topic classification is a supervised machine learning technique with known classes while topic modeling is a form of unsupervised learning.Latent semantic analysis is one of the primary techniques in topic modeling. 

It is useful in exploring the relations between a collection of documents and the terms they comprise by generating a collection of concepts associated with the document and terms. The intuition of LSA is that words that are close in meaning will occur in similar fragments of text. It is important to note that LSA helps in obtaining the hidden features in documents. Therefore, the method is used to obtain the contextual meaning of words from the documents. After the input text is tokenized, every term in the text is denoted as a tuple containing term ID and term frequency. A matrix is produced in which each row represents the unique terms and the column represents the documents. Every cell signifies the term count in the corresponding document. The matrix of term -frequency counts gained from the term document matrix is then enhanced using the TF-IDF technique so as to give more weight to uncommon terms compared to recurrent terms across documents and also to common terms in certain documents. More conventionally, the entry is weighted by some importance of each word, for example the negative logarithm of the fraction of documents that contain it resulting in a TF-IDF weighting.The term-document matrix gets adjusted to include weights of each term in each document. The dimensionality reduction of the matrix is done by SVD (Singular Value Decomposition). SVD is applied to a matrix W representing the occurrence of words in the documents. SVD results in an approximation of W by the product of three matrices, one of which each word is represented as a low dimensional vector and another is a diagonal scaling matrix.It is important to note that while the LSA method is an automatic process and is dependent on the specification of k value for dimensionality reduction .k is an open, empirical parameter that represents optimal dimensionality (or number of topics or concepts).In many cases ,this dimensionality is intrinsic to the domain being calculated and therefore must be empirically determined.

This project uses the LSA approach to assign topics to the hotel reviews assigned by customers.

## Dataset
The dataset that was used in this project was obtained from Kaggle and can be found here at : https://www.kaggle.com/datafiniti/hotel-reviews. It contains distinct reviews of different hotels around the world.

## Data Exploration
The shape of the data:
![image](https://user-images.githubusercontent.com/67794705/89720990-25462380-d9d0-11ea-9e6d-ec56a8aa1bf9.png)

A look at the first few columns:
![image](https://user-images.githubusercontent.com/67794705/89720981-fc259300-d9cf-11ea-8292-fe9457496be4.png)

Here,we are only concerned about the column that contains the reviews text.

Tokenization from NLTK module is applied to the text reviews to obtain individual sentences.Then, a document -term matrix is created using Tfidf vectorizer on our sentences.An LSA pipeline is created to include tdidf vectorization,svd and row normalization.

![image](https://user-images.githubusercontent.com/67794705/89721121-b23dac80-d9d1-11ea-8c3d-a4ffcb0deb0c.png)

Kmeans clustering is applied to predict 10 different clusters.

![image](https://user-images.githubusercontent.com/67794705/89721156-02b50a00-d9d2-11ea-9eac-198962266f8d.png)

## Results
We tried to predict the cluster of new reviews:

![image](https://user-images.githubusercontent.com/67794705/89721169-2a0bd700-d9d2-11ea-999f-08f3c66faee4.png)
