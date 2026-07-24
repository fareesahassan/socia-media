# AI-Based Social Media Threat Intelligence for Cybersecurity Monitoring
An end-to-end prototype pipeline tat uses AI and NLP to automatically identify, classify, and structure cybersecurity-related information from noisy, informal socail media text-built as an MSc Cybersecurity project.
# Overview
Social media carries large volumes of cybersecurity discussion, but it's mixed with noise and written in informal, techinal language that's hard to process at scale. this project builds a two-stage pipeline to address that:
-Relevance filtering - its  a binary classification problem.The relevance filtering stage achieved approximately 96.54% accuracy.
-Fine-grained threat classification - an eleven-category fine-grained classifier comparing classical ML, sentence embeddings, and a multi-view stacking model. A tuned linear SVM performed best (54.3% accuracy, F1 0.537), outperforming SBERT/SecBERT embedding-based approaches.
# Pipeline
Social media data → Data cleaning → Relevance filtering → Feature extraction → 11-class threat classification → Entity extraction → Urgency analysis → Explainability → Risk prioritisation → Dashboard
# Datasets
I used multiple publicly available cybersecurity-related datasets for different parts of the project.
The datasets supported tasks including:
-	Relevance filtering 
- Fine-grained threat classification 
The project report identifies four datasets, including cybersecurity text datasets and a suspicious tweets dataset. The references include:
-	NLP Based Cyber Security Dataset 
-	Cyber Threat Dataset: Network, Text & Relation 
-	Cybersecurity Threat and Awareness Program Dataset 
-	Suspicious Tweets Dataset
# Categories
The 11 categories used in the classification task include:
1.	Indicator 
2.	Malware 
3.	Identity 
4.	SOFTWARE 
5.	TIME 
6.	Vulnerability 
7.	Threat Actor 
8.	Campaign 
9.	Attack Pattern 
10.	Location 
11.	Tools
# Algorithm/model
compared several modelling approaches.
These included:
-Support Vector Machine, or SVM 
SVM is a strong model for high-dimensional text classification.
When text is converted into TF-IDF features, the resulting feature space can contain a very large number of dimensions.
-Random Forest 
Random Forest is an ensemble of decision trees.
 included it to compare a tree-based approach with linear text classification methods such as SVM and Logistic Regression.
It can capture nonlinear relationships between features and provides a useful comparison against the linear models.
-Logistic Regression 
Logistic Regression is a strong baseline for classification problems, especially when using text representations such as TF-IDF.
It is relatively simple, interpretable and computationally efficient.
Using it gave me another classical machine-learning baseline against which I could compare the other approaches.
-Ensemble approaches
it combines models
-SBERT-based representations 
SBERT, or Sentence-BERT, generates sentence-level semantic embeddings.
SecBERT-based representations 
SecBERT is a transformer-based model designed for cybersecurity-related language.
-Multi-view stacking 
combined features
The purpose was to compare simpler classical approaches with more complex representation-based approaches. 
# Evalution 
evaluated the models using several metrics, including:
-	Accuracy- Accuracy tells us the percentage of predictions that were correct overall.
For example, if a model correctly predicts 80 out of 100 samples, the accuracy is 80%.
However, accuracy alone may not tell us how well the model performs on each individual class.
-	Precision
-Precision 
"When the model predicts a particular class, how often is that prediction actually correct?"
For example, if the model predicts 100 posts as Malware and 80 are actually Malware, the precision is 80%.
-	Recall
"Of all the actual examples belonging to a class, how many did the model successfully find?"
For example, if there are 100 actual Malware posts and the model correctly identifies 80 of them, the recall is 80%.
-	F1-score
F1-score combines precision and recall into a single measure.
It is useful when we want a balance between:
  -Avoiding incorrect predictions 
  -Finding as many actual examples as possible 
This is particularly useful when working with imbalanced datasets.
 -	Balanced accuracy
-	MCC
MCC stands for Matthews Correlation Coefficient.
It provides a balanced measure of classification quality and can be useful when the classes are imbalanced.
It considers the relationship between correct and incorrect predictions rather than looking only at accuracy.
-	Confusion matrices
A confusion matrix is a table that shows how the model's predictions compare with the actual classes.
It helps us see:
 -	Which classes were predicted correctly 
 -	Which classes were confused with each othe

# Tech stack
Language/Environment:Python, Google Colab
- Classical ML: scikit-learn (SVM, Random Forest, Logistic Regression)
- Embeddings: sentence-transformers (SBERT), Hugging Face Transformers (SecBERT)
- NLP: spaCy (NER), VADER (sentiment/urgency)
- Explainability: LIME
- Data access: kagglehub (programmatic dataset retrieval)
# Dashboard
The dashboard is the final presentation layer of the project.
It brings together the outputs from the different stages of the pipeline.
It can present information such as:
- Threat classification 
-	Prediction confidence 
-	Extracted entities 
-	Urgency 
-	Risk level 
# Results
There are two important results.
The relevance-filtering stage achieved approximately 96.54% accuracy.
The best result for the 11-class fine-grained classification task was approximately 54.31% accuracy using the tuned SVM. 

# Conclusion
This project shows that AI and NLP can efficiently analyze social media for cybersecurity threat intelligence. While fine-grained classification across 11 threat categories remained difficult, with the best accuracy of 54.31% using a tuned SVM, the suggested system achieved 96.54% accuracy in identifying cybersecurity-related posts. All things considered, the project offers a solid basis for automated cyber threat monitoring and identifies chances for further advancements in classification performance.


