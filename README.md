# Semantic Similarity Detection on Quora Question Pairs
The objective of this project is to determine whether two questions are similar. 
<br>The Quora Question Pairs dataset was used which is available on Kaggle. 
## Exploratory Data Analysis
1. There are a total of 404290 question pairs in the dataset
2. The dataset is unbalanced. There are more non-duplicate questions than duplicate questions
4. Number of unique questions = 537933 ; Number of questions getting repeated = 111780
## Preprocessing 
In this project out of 404290 question pairs, random 30000 samples were used.
<br> Out of this, there were 18951 non duplicate question pairs and 11049 duplicate question pairs
<br> The following preprocessing steps were used 
1. Questions were converted to lower case
2. Hashtags were removed
3. Special characters were removed
4. Links were removed
5. Non-Ascii characters were removed
6. Punctations were removed
7. Digits were removed
8. Single letters were removed
9. Multiple spaces were removed
##
Number of Training samples = 24000 , Number of Test samples = 600 
## Feature Extraction 
Two methods were used for feature extraction. These were extracted uing sklean.feature_extraction.text.
1. Bag of words (BoW) 
2. Term frequency inverse document frequency (TfIdf)
   
## Model 
Three models were tested in this project 
1. Random Forest Model
2. XG Boost Model
3. Sentence Transformer + XG Boost

## Results
Since the data is imbalanced, F1 score metric and confusion matrix were used to evaluate the performance of the model 
### Random Forest + BoW
![rf_bow_f1](images/rf_bow_f1.png)
![rf_bow](images/rf_bow.png)
### XG Boost + BoW
![xgb_bow_f1](images/xgb_bow_f1.png)
![xgb_bow](images/xgb_bow.png)
### Random Forest + TfIdf
![rf_tfidf_f1](images/rf_tfidf_f1.png)
![rf_tfidf](images/rf_tfidf.png)
### XG Boost + TfIdf
![xgb_tfidf_f1](images/xgb_tfidf_f1.png)
![xgb_tfidf](images/xgb_tfidf.png)
### Sentence Transformer + XG Boost 
![Tran_xgb_f1](images/Tran_xgb_f1.png)
![Tran_XGB](images/Tran_XGB.png)
## Discussion 
The best performing model was Random Forest using TfIdf features which gave a F1 score of 0.74.
<br> To improve the current model, I would like to explore the following methods
1. Using Feature Engineering to develop meaningful features
2. Using Transformer models like BERT for feature extraction
