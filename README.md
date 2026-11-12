# CAPITOL: Classifying American Political Ideologies Through Online Language

Can you tell a **Democrat** from a **Republican** by their tweets alone? CAPITOL is a binary text classifier for tweets written by U.S. politicians. It compares sparse representations (**TF-IDF**) with dense word embeddings (**GloVe**, **FastText**), and classical ML models with **LSTM** networks.

Project for *Text Mining and Natural Language Processing* (BSc in Artificial Intelligence, University of Pavia, A.Y. 2024/25), July 2025.

📄 [Full report](docs/CAPITOL_report.pdf) · 📊 [Presentation](docs/CAPITOL_presentation.pdf)

## Results

| Representation | Model | Accuracy | Macro F1 |
|---|---|---|---|
| TF-IDF | **Logistic Regression** | **0.84** | **0.84** |
| FastText (self-trained) | LSTM | 0.82 | 0.83 |
| GloVe (pre-trained) | LSTM | 0.79 | 0.80 |
| TF-IDF | XGBoost | 0.78 | 0.78 |

A simple linear model on TF-IDF features won. Party-specific vocabulary is a strong signal, and a linear model on sparse features captures it well. FastText beat GloVe because its subword information copes better with hashtags, slang and misspellings.

## Data

The [PoliticalTweets](https://huggingface.co/datasets/Jacobvs/PoliticalTweets) dataset: tweets by American politicians labelled *Democrat* or *Republican*, with a roughly balanced class split (49.3% / 50.7%). We sampled 30,000 tweets to fit the compute limits of the Deepnote environment.

## Pipeline

1. **Preprocessing**: lowercasing, hashtag word-splitting (`wordninja`, e.g. `#BuildBackBetter` → "build back better"), emoji stripping, removal of punctuation and stopwords, and filtering of very short tweets.
2. **Representations**
   - Sparse: TF-IDF → Logistic Regression, XGBoost
   - Dense: GloVe (pre-trained) and FastText (trained on the corpus) → LSTM (128 units, dropout)
3. **Evaluation**: stratified 80/20 train/test split; accuracy, precision, recall, F1 and confusion matrices.

## Run it

```bash
git clone https://github.com/brusati04/capitol-political-tweets-nlp.git
cd capitol-political-tweets-nlp
pip install -r requirements.txt
jupyter notebook pre-processing.ipynb   # then main.ipynb
```

## Repository structure

```
├── pre-processing.ipynb   # dataset exploration and text cleaning
├── main.ipynb             # TF-IDF models, embeddings + LSTM, evaluation
├── Init.ipynb             # environment setup (Deepnote)
├── dataset.csv            # sampled dataset
├── requirements.txt
└── docs/
    ├── CAPITOL_report.pdf
    └── CAPITOL_presentation.pdf
```

## Authors

- **Lorenzo Brusati**
- **Ecaterina Tsuhuy**

Suggestions and pull requests are welcome.
