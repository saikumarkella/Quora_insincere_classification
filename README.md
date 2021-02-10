# Quora_insincere_classification

### Problem statement :
Quora is a platform that empowers people to learn from each other. On Quora, people can ask questions and connect with others who contribute unique insights and quality answers. A key challenge is to weed out insincere questions -- those founded upon false premises, or that intend to make a statement rather than look for helpful answers.
You can find the Competations [here](https://www.kaggle.com/c/quora-insincere-questions-classification)

### Aim :
It is binary classification problem. We have to predict whether a question asked on Quora is sincere or not.

### Data Overiew :
It contains two types of Dataset:

        1. Train set : contains 3 columns (qid , question_text , target)  and has 1.3 Million rows.
        2. Test set : contain 2 Columns (qid , question_text , target) and has 0.37 Million rows.
        

### Exploratory Data Analysis :
**you can find the Analysis part is in this [notebook](https://github.com/saikumarkella/Quora_insincere_classification/blob/main/qiq-classification-logistic-regression.ipynb)**

***key Observations :**
- No missing and Duplicate values in the Dataset.
- Dataset was an Imbalanced with the Majority class has 92% and minority has only 8%
- From the WordCloud the most frequenct word in the sincere questions was ["best","student","India","life","people"] and similar way some of more frequest words in insincere questions were ["Trump","Muslim","Women","sex","girl"].
- In the dataset there are some non-english Characters.

### Data Preparations and Modelings 
For this problems i preformed different experiments and used different algorithms like traditional ML algos. deep learning models.

**Experiment 1:** 
[notebook](https://github.com/saikumarkella/Quora_insincere_classification/blob/main/qiq-classification-logistic-regression.ipynb)

**Data Preparations :**

                - Removing Staopwords
                - Removing puncutations
                - Removing numbers
                - Removing some special characters
                - Converting upper case to lowercase
          
**Statistical Features :**

                - Number of characters before preprocessing
                - Number of characters after preprocessing
                - Number of words before preprocessing
                - Number of Words after preprocessing
                - Number of stopwords
                - Number of punctuations
         
**using Holdout method for the model selection in a stratify way**

**Modelling and Results:**

| data | Model | F1_score |
|---|---|---|
|statistical features | Random Forest | 0.083 |
|TF_IDF vectorizer | Logistic Regression | 0.52 |
| TF-IDF | Naive Bayes| 0.45 |
| TF-IDF + Statistical Features | Logistic Regression | 0.43 |


#### Experiment 2 (Deep Learning models):
[notebook 2](https://github.com/saikumarkella/Quora_insincere_classification/blob/main/qiq-pretrained-embeddings-mlp-cnn.ipynb)

**Data Preparation :**

           - Using a Pretrained Embeddings for gettiing feature vector for each word . it preserve the semantic between the words.
           - Preprocessing techniques are done according to the Pretrained Embedding (Google News Embeedings ) like here not removed stopwords and didn;t change the cases
           
           
 **In this experiment didn't used any statistical Features**
 
**Modelling :**

| data | Model | F1_score |
|---|---|---|
|Pretrained Embeddings  | MultiLayer Perceptron | 0.588 |
|Prerained Embeddings | Convolutional Networks | 0.64 |


**Experiment 3:(deep learning models LSTM)**
[notebook 3](https://github.com/saikumarkella/Quora_insincere_classification/blob/main/quora-insincere-questions-classification-lstm.ipynb)


**Data Preparations :**

            - Using a pretrained ebeddings . Preproceesed the data according to this by anlyzing the out of vocabulary .
            
 **No statistical Features used here**
 
**Modelling :**

| data | Model | F1_score |
|---|---|---|
|Learning  Embeddings from scratch  | Bidirectional LSTM | 0.64 |
|Prerained Embeddings | Bidirectional LSTM | 0.677 |
 
 
