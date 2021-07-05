# Corsali Machine Learning Technical Interview

This is our project-based technical interview for machine learning engineers. It gives us a chance to see your abilities and how you approach problems. It is designed to give you creative freedom as you develop a solution, and consists of a model implementation quesion as well as non-coding questions below. Please complete both the coding and non-coding questions.

Please FORK the repository or download as a zip file for your submission.

## Coding questions

Please build a content classification model that takes in a news headline as an input and predicts the category as an output. There are two datasets included: `news_dataset.json` which contains 200,000 headlines covering 41 categories, and `post_data.csv` which contains 400 sample posts on which the model will be used. The content classification model will predict one of the 41 categories from the news dataset. The goal is to create a performant and accurate model. You are welcome to use an off-the-shelf model, a pre-trained model, or a custom trained model, or any combination of them. Feel free to use any packages/tools/etc to build a great model.

Please write the code for the model in content_classification.py, and call it from main.py. Please report the accuracy of the model as evaluated on the test dataset, which you can choose to split any way you'd like.

## Non-coding questions

Please answer the non-coding questions below by editing this readme

1. You are given a dataset of 1500 company descriptions and must classify them into 6 categories. You train a logistic regression, but it only has 60% accuracy. Your task is to identify which types of data are underrepresented in the dataset in order to prioritize

The question is a bit vague. If the question is asking how to figure out which classes the model is classifying poorly, then,
checking the precision recall values for each class. Printing out the confusion matrix for instance, will help.

2. You are choosing the best way to represent a text company description as an input to a model. Describe the trade offs between bag-of-words, word embeddings, and any other representation you may choose.

Word embeddings that have been trained on a large corpus of text help capture semantic relationships amongst words in the vector space.
Also, they provide a more compact representation as compared to a one-hot-encoding for instance. However word embeddings might only
be effective if most of the words in the datset are present in the embedding. Furthermore, domain specific applications might require a customized
embedding, hence require more work to train our own embedding. 

Bag-of-words (BoW) is high dimensional and sparsely representation that fails to capture the semantic relationship between words. However it may perform better than
embeddings if the company desctioption dataset is small. Furthermore, if the company description texts are domain specific, (which they probably are), BoW could perform better.

3. You decide to use a recurrent neural network for the text classification task instead. You implement the model in PyTorch and find that it's very accuracte, but that the model evaluation is too slow. How would you accelerate the model prediction time?

Simplifying the model. For instance, if the model is a Deep RNN, I would reduce the number of layers, or the feature dimension.

## Submission

* Original code from https://github.com/andikarachman/News-Title-Classification/blob/master/News_Title_Classification.ipynb 
* I used Glove embeddings https://nlp.stanford.edu/data/glove.6B.zip. To run, you'd have to have to copy the Glove embedding/ folder in the main project directory.
* A more readable code is present in the content_classification.ipynb notebook file.

* Although I tried fine tuning the model, varying batch_size and learning rate, the best accuracy I got is only 32.7%. At this point, I would probably pick a different model and run more experiments to see if I can improve this result.
