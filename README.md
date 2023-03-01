# MultiLabel-Classification


you will identify tags for stack exchange Questions. This data is a subset of data available in Kaggle Competitions. 
The given dataset actually contains the different questions asked in the StackExchange website for various tech domains. We have fetched only those question that contains top 10 individual tags. Each question can have more than one tag. This means that this is a multi-label classification problem. These are the ten categories for tags in the data.

0	c#
1	java
2	php
3	javascript
4	android
5	jquery
6	c++
7	python
8	iphone
9	asp.net

There are two CSV files provided to you:


1.	Multilabel.csv – This has the following columns (you can delete any extra columns present):


●	Id – Id of the question
●	Title: Title of the Question
●	Body: Main Body of the Questions
●	Tags: Question Tags (This is your outcome variable)
●	Tag Number: Same as Tag. Here Tag is replaced by its index. For example, [2,3] means that this question is tagged as javascript and php.

You will use this data set to train your classification model. You will create train/valid/test splits from this data set. Use 60% for train, 20 % for the test, and remaining 20% for  validation dataset.


2.	raw_text.csv: This file has only Title and Body. You can think of this data as a large un-labeled dataset. You can use this data set to generate custom pre-trained embeddings. This data has 6,034,195 questions. 


Task 1: 

●	In this task, you will only use Multilabel.csv.
●	This is a baseline model without any embeddings. 
●	In this task, you will use the bag of word approach (e.g. tfidf vectorizer) to generate tensors. You will then use a TensorDataset class to create train/valid/test datasets. Finally create Data loaders.
●	Now you will use a simple feed-forward Neural Network. Start with a small fraction of train/valid datasets to find network configuration and a combination of hyperparameters that work. Finally, train the model on the complete dataset.
●	Evaluate your model using the appropriate metric. Provide reasoning for the metric chosen.
●	Remember, that this is a multilabel classification model. Use appropriate loss function. 




Task 2: 

●	In this task, also you will only use Multilabel.csv. 
●	Train the model using nn.EmbeddingBag layer. You will not use the tfidf vectorizer in this case. 
●	You will have to create a custom dataset for this task.
●	You will follow the same approach of starting with a smaller subset of the data to find a combination of hyperparameters that work.

Task 3 :  
Use raw_text.csv to generate cbow or skipgram or fasttext embeddings using gensim. Once you have trained your model, save the embeddings so that we can use these in our classification model later on. You can use a smaller subset for raw_text.csv if it takes too long.

---------------------------------------------------------------------------------------------------------------------



Task 4: 
Use pre-trained embeddings from the previous step (or pre-trained embeddings available online) in your classification pipeline in sklearn. You can use any classification model suitable for multi-label classification problems. Evaluate your model using the appropriate metric. 

Task 5: 
Use pre-trained embeddings in a Neural Network. In this task, use the embeddings as it is i.e., without fine-tuning them. The network should not update these weights (embeddings)

Task6: 
Use pre-trained embeddings in Neural Network. However, in this task, you will fine-tune pre-trained embedding while training your Neural Network.

