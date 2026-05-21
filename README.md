# Cross-Domain Named Entity Recognition

## Project Overview

This project investigates cross-domain degradation in Named Entity Recognition (NER) systems using transformer-based models.

The main objective is to analyze how a model trained on structured text performs when transferred to noisy social-media text and explore methods to mitigate the degradation.

The experiments were conducted using the English Web Treebank (EWT) dataset and the Tweebank Twitter dataset.

---

## Research Question

> What factors cause NER models to fail when transferred from EWT to social-media text (Tweebank), and how can this degradation be mitigated?

---

## Datasets

### English Web Treebank (EWT)
- Structured and relatively clean text
- Used for training and in-domain evaluation

### Tweebank
- Twitter/social-media dataset
- Contains noisy text including:
  - hashtags
  - mentions
  - abbreviations
  - inconsistent capitalization
  - emojis
  - informal sentence structures

Used for cross-domain evaluation.

---

## Models

### Baseline Model
- BERT-based token classification model
- Trained on EWT

### Mitigation Model
- BERTweet model
- Designed specifically for Twitter/social-media text

---

## Experiments

### 1. In-Domain Evaluation
Train and evaluate on EWT.

### 2. Cross-Domain Evaluation
Train on EWT and evaluate on Tweebank.

### 3. Text Normalization Mitigation
Apply preprocessing and normalization techniques before evaluation.

### 4. BERTweet Mitigation
Replace BERT with BERTweet to better handle noisy Twitter-style language.

---

## Main Findings

The experiments demonstrate significant performance degradation when transferring from structured text to social-media text.

The largest performance drop was observed for ORG entities.

Main contributing factors include:
- inconsistent capitalization
- abbreviations
- hashtags and usernames
- noisy sentence structures
- domain-specific vocabulary

Text normalization produced minimal improvement, while BERTweet showed better robustness on social-media content.

---

## Repository Structure

```text
Baseline.ipynb
│
├── Baseline training and in-domain evaluation on EWT
│

CrossDomain_EWT_to_Tweebank.ipynb
│
├── Cross-domain evaluation on Tweebank
├── Analysis of performance degradation
└── First mitigation strategy using text normalization
│

Mitigation_BERTweet.ipynb
│
└── Second mitigation strategy using BERTweet
```

---

## Technologies Used

- Python
- PyTorch
- HuggingFace Transformers
- Jupyter Notebook
- seqeval
- scikit-learn

---

## How to Run

Install required libraries:

```bash
pip install transformers datasets torch seqeval scikit-learn pandas numpy matplotlib
```

Run the notebooks in the following order:

1. Baseline.ipynb  
2. CrossDomain_EWT_to_Tweebank.ipynb  
3. Mitigation_BERTweet.ipynb

---

## Authors

- Nicolai Alonso Kofoed
- Patrycja Zdyb
- Aryan Anvekar
- IT University of Copenhagen
- Bachelor in Data Science
