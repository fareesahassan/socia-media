# AI-Based Social Media Threat Intelligence for Cybersecurity Monitoring
An end-to-end prototype pipeline tat uses AI and NLP to automatically identify, classify, and structure cybersecurity-related information from noisy, informal socail media text-built as an MSc Cybersecurity project.
# Overview
Social media carries large volumes of cybersecurity discussion, but it's mixed with noise and written in informal, techinal language that's hard to process at scale. this project builds a two-stage pipeline to address that:
-Relevance filtering - its  a binary classification problem.The relevance filtering stage achieved approximately 96.54% accuracy.
-Fine-grained threat classification - an eleven-category fine-grained classifier comparing classical ML, sentence embeddings, and a multi-view stacking model. A tuned linear SVM performed best (54.3% accuracy, F1 0.537), outperforming SBERT/SecBERT embedding-based approaches.
# pipeline
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
# categories
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
# evalution 
evaluated the models using several metrics, including:
-	Accuracy 
-	Precision 
-	Recall 
-	F1-score 
-	Balanced accuracy 
-	MCC 
-	Confusion matrices
# tech stack
Language/Environment:Python, Google Colab
- Classical ML: scikit-learn (SVM, Random Forest, Logistic Regression)
- Embeddings: sentence-transformers (SBERT), Hugging Face Transformers (SecBERT)
- NLP: spaCy (NER), VADER (sentiment/urgency)
- Explainability: LIME
- Data access: kagglehub (programmatic dataset retrieval)
# dashboard
The dashboard is the final presentation layer of the project.
It brings together the outputs from the different stages of the pipeline.
It can present information such as:
- Threat classification 
-	Prediction confidence 
-	Extracted entities 
-	Urgency 
-	Risk level 
# results
There are two important results.
The relevance-filtering stage achieved approximately 96.54% accuracy.
The best result for the 11-class fine-grained classification task was approximately 54.31% accuracy using the tuned SVM. 

# conclusion
My project focuses on using AI and NLP to analyse social media content for cybersecurity threat intelligence. The system follows a two-stage pipeline. First, it filters cybersecurity-relevant content from general noise, achieving approximately 96.54% accuracy. Second, it performs fine-grained classification across 11 threat categories. I compared classical machine-learning models such as SVM, Random Forest and Logistic Regression, along with ensemble and transformer-based representations using SBERT and SecBERT. The best 11-class result was approximately 54.31% accuracy using a tuned SVM. I also implemented grouped cross-validation to reduce data leakage, entity extraction using NER and regex, urgency analysis, LIME explainability and a prototype dashboard. The main finding is that relevance filtering is relatively effective, while fine-grained classification is more difficult because of class imbalance, semantic overlap and the fact that cybersecurity posts can contain multiple concepts. 


