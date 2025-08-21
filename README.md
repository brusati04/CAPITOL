# Natural Language Processing exam

# CAPITOL : Classifying American Political Ideologies Through Online Language
**Exam Date: July 2025**

📚 "Text Classification: Democrat vs. Republican" - A Natural Language Processing (NLP) Project 

In our NLPexam project, we address the challenge of building a binary classifier that predicts whether a given tweet reflects a Democrat or Republican political stance. Our work emphasizes data preprocessing, vectorization, word embeddings, and the comparative evaluation of traditional machine learning models and deep learning architectures.

## Table of Contents

- [Introduction](#introduction)
- [Data](#data)
- [Methodology](#methodology)
- [Models](#models)
- [Results](#results)
- [Issues Encountered](#issues-encountered)
- [Project Recap](#project-recap)
- [Final Conclusion](#final-conclusion)
- [Contributing](#contributing)

## Introduction

The main goal of this NLP project was to develop a binary classification system capable of distinguishing between Democrat and Republican tweets. The project involved thorough text preprocessing, model implementation, and evaluation using classical machine learning and deep learning approaches.

## Data

The dataset used for this project is the PoliticalTweets dataset, which contains thousands of labeled tweets written by American politicians. Each tweet is annotated as either “Democrat” or “Republican.” The dataset is relatively balanced in terms of class distribution, which allowed for straightforward training without the need for heavy resampling techniques.

## Methodology

We followed a structured approach to text classification, which involved:
- Data cleaning: lowercasing, punctuation removal, and filtering short tweets.
- Stopword removal to eliminate common non-informative words.
- Transformation of text into numerical features using two main strategies:
    - TF-IDF Vectorization for traditional models.
    - Word Embeddings (GloVe, FastText) for deep learning models.
- Data splitting into training and test sets (typically 80/20).

## Models

We implemented and evaluated the following classification models:
1. **TF-IDF + XGBoost**: A gradient boosting classifier applied to sparse textual data.
2. **TF-IDF + Logistic Regression**: A strong linear baseline for text classification tasks.
3. **GloVe + LSTM**: A deep learning model that combines pretrained GloVe word embeddings with Long Short-Term Memory units to capture word dependencies.
4. **FastText + LSTM**: Similar to the GloVe model but using FastText embeddings, which incorporate subword information.

## Results

Each model was evaluated using accuracy, precision, recall, F1-score, and confusion matrices. Among the models, TF-IDF + Logistic Regression achieved the highest performance overall. Deep learning models (LSTM-based) also performed well, with FastText + LSTM slightly outperforming the GloVe variant. XGBoost delivered decent results but was slightly less competitive in this context.


## Issues Encountered

Throughout the project, we faced limited computational resources on Deepnote, which led us to reduce the dataset to 30,000 samples to ensure manageable training times. Library compatibility issues also slowed down model experimentation. Additionally, downloading large pre-trained models like GloVe increased setup time and disk usage within the constrained cloud environment.

## Project Recap

In summary, our project involved several key steps, preprocessing political tweet data, applying various vectorization and embedding techniques, implementing both classical and deep learning models, and evaluating their performance. This hands-on experience enhanced our understanding of NLP workflows and highlighted how different textual representations and algorithms influence classification outcomes.

## Final Conclusion

Although the performance varied across models, all approaches demonstrated the ability to identify political affiliation in text with reasonable accuracy. Logistic Regression with TF-IDF stood out for its simplicity and effectiveness. Meanwhile, LSTM models with embeddings offered strong performance while also capturing sequential patterns in language. The project provided us with practical experience in implementing and evaluating a real-world NLP task using multiple modeling techniques.

## Contributing

If you have suggestions for improvements, new experiments, or alternative embeddings to try, feel free to open an issue or submit a pull request. Let’s continue improving this project together!