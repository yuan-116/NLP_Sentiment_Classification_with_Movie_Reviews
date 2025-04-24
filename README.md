# NLP_Sentiment_Classification_with_Movie_Reviews
Final project for IST 664: Natural Language Processing, demonstrating applied NLP techniques developed at Syracuse University


## 🧠 NLP Final Project: Sentiment Classification with Movie Reviews
**Author:** ChihHao Luca Yuan  
**Dataset:** Kaggle Sentiment Analysis on Movie Reviews  

This project tackles sentiment classification using a Kaggle competition dataset consisting of labeled movie review phrases. The goal is to evaluate and compare the effectiveness of different preprocessing and feature engineering techniques using the NLTK Naive Bayes Classifier and scikit-learn Random Forest.

---

### 📁 Dataset Overview
- Source: Rotten Tomatoes review dataset used in Stanford's NLP sentiment work
- Format: Each row contains a short phrase and its sentiment label (0 to 4)
- Used subset: 20,000 phrases (due to 16GB RAM constraint)

---

### 🧼 Preprocessing Steps
- Tokenization using `word_tokenize`
- Lowercasing for consistency
- Lemmatization using WordNet Lemmatizer
- Stopword removal (excluding negation words to preserve sentiment cues)

---

### 🛠️ Feature Engineering Experiments

| Feature Set                | Description                                             | Accuracy  | Best? |
|---------------------------|---------------------------------------------------------|-----------|--------|
| Bag-of-Words (baseline)   | 2,000 most common words                                 | 56.73%    |        |
| Without stopwords         | Excludes standard stopwords                            | 57.50%    |        |
| Lemmatized + Stopwords Removed | Preprocessed tokens                                | 57.58%    |        |
| Negation features         | Adds "NOT_" prefix to words after negators            | 51.53%    |        |
| Subjectivity Lexicon (SL) | Use of Subjectivity Lexicon for sentiment cues         | **57.60%** | ✔️     |
| Bigrams                   | Top 500 chi-squared scored bigrams                     | 57.58%    |        |
| POS-tagged Bigrams        | Bigrams formed on POS-tagged word sequences            | 56.23%    |        |
| POS tag counts            | Frequency of POS tags as features                      | 55.33%    |        |
| LIWC lexicon              | Positive/negative counts from LIWC sentiment lexicon   | 53.00%    |        |
| Bigrams + LIWC            | Combination of contextual and lexicon features         | 56.33%    |        |
| **Random Forest Classifier** | Scikit-learn ensemble model with preprocessing     | **63.07%** | ✔️     |

---

### 🔍 Observations
- ✔️ **Subjectivity Lexicon** delivered the best accuracy among Naive Bayes models.
- ✔️ **Random Forest Classifier** provided the highest overall accuracy.
- Negation features unexpectedly reduced accuracy, likely due to added noise.

---

### 📌 Reflection
Despite reviewing course materials in depth, implementing real-world NLP revealed new challenges:
- Hardware limitations (16GB RAM) impacted data scalability
- Feature combination was trickier than expected due to preprocessing incompatibilities
- Valuable lessons learned about pipeline design, overfitting, and trade-offs in feature design

---
