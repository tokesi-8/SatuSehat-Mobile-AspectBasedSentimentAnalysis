# SATUSEHAT Mobile ABSA

Aspect-Based Sentiment Analysis (ABSA) of Indonesian-language SATUSEHAT Mobile reviews collected from the Google Play Store.

## Research Objectives

This study aims to:
1. Identify the service aspects most frequently discussed by users.
2. Analyze Positive, Negative, and Neutral sentiment across each aspect.
3. Identify aspects with the highest number and proportion of negative reviews.
4. Compare IndoBERT with a TF-IDF + Logistic Regression baseline.

## Aspect Categories

| Code | Aspect |
|---|---|
| A1 | Registration, Login, and Verification |
| A2 | Performance and Stability |
| A3 | Main Features and Services |
| A4 | Data Accuracy and Synchronization |
| A5 | Interface and Ease of Use |
| A6 | Data Privacy and Security |
| A7 | User Services and Support |
| A8 | General |

Each review may contain multiple aspects. Each identified aspect is assigned its own sentiment label: **Positive**, **Negative**, or **Neutral**. Labels are based on review text, not star ratings.

## Dataset

Reviews are collected from the SATUSEHAT Mobile Google Play Store listing using `google-play-scraper`.

- **Period:** 1 March 2023 – 31 October 2026
- **Language:** Indonesian, including understandable Indonesian-English mixed reviews
- **Minimum length:** 5 words before preprocessing
- **Target size:** 5,000 eligible reviews

Duplicate, empty, irrelevant, spam, and non-eligible language reviews are excluded. Star ratings are retained as supplementary metadata only.

## Methodology

1. Data collection, filtering, and initial EDA
2. Pilot annotation by two annotators
3. Inter-annotator agreement measurement using Cohen's Kappa
4. LLM-assisted annotation followed by human validation
5. Annotated-data analysis and text preprocessing
6. 80:20 training-test split, with validation data drawn from the training set
7. Model training and hyperparameter tuning
8. Evaluation using Precision, Recall, and F1-score

## Models

- **Baseline:** TF-IDF + Logistic Regression
- **Proposed model:** Fine-tuned IndoBERT

The primary evaluation metric is **end-to-end aspect–sentiment Macro-F1**.

## Repository Structure
```
.
├── dataset/                  # Stores datasets collected and processed during the research
├── pilot_annotated_50/       # Contains pilot annotation data from two annotators for agreement evaluation
├── main_notebook.ipynb       # Main notebook covering data collection, EDA, Data Filtering, Data sampling, and pilot annotation
└── README.md                 # Provides an overview of the project, research objectives, methodology, and repository structure
```

## Contributors

- Tokesi Lukynawa
- Daniel Sebastian

School of Computer Science, Universitas Bina Nusantara Jakarta — 2026

## Project Status

This repository is under development. The notebook and dataset folders reflect the current implementation; research methods and documentation may be updated as the project progresses.
