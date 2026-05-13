# Malay-English Hallucination Detection

This project implements a supervised NLP model to detect hallucinated answers in Malay and English question-answer pairs.

## Dataset

The dataset used is `englishmalay_halueval.csv`.

The dataset contains:
- 1000 total samples
- 500 English samples
- 500 Malay samples
- 500 truthful samples
- 500 hallucinated samples

Labels:
- 0 = Truthful
- 1 = Hallucinated

## Method

The task is treated as a supervised binary text classification problem.

The model uses:
- TF-IDF text features
- Context-based numerical features
- Logistic Regression classifier

## Features Used

The input text combines:
- context
- question
- answer

Additional numerical features:
- answer length
- question length
- context length
- answer-context word overlap
- answer appears in context

## Tools and Libraries

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- SciPy

## Key Parameters

Train-test split:
- test_size = 0.2
- random_state = 42
- stratify = y

TF-IDF:
- max_features = 10000
- lowercase = True
- ngram_range = (1, 2)

Model:
- Logistic Regression
- max_iter = 1000
- random_state = 42

## Results

The model achieved:

| Metric | Score |
|---|---:|
| Accuracy | 0.985 |
| Precision | 0.990 |
| Recall | 0.980 |
| F1-score | 0.985 |

Confusion Matrix:

| | Predicted Truthful | Predicted Hallucinated |
|---|---:|---:|
| Actual Truthful | 99 | 1 |
| Actual Hallucinated | 2 | 98 |

## How to Run

1. Open the notebook `hallucination_detection.ipynb` in Google Colab.
2. Upload the dataset file `englishmalay_halueval.csv`.
3. Run all cells from top to bottom.
4. The model evaluation results will be displayed at the end.