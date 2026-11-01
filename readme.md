# Sentiment Analysis — Model Comparison

A machine-learning and deep-learning project comparing traditional text classifiers with a GRU sequence model. The repository currently tracks Logistic Regression, Multinomial Naive Bayes and GRU artifacts, along with a label encoder and notebook.

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat-square&logo=python&logoColor=white)
![ML](https://img.shields.io/badge/Models-Scikit--learn%20%2B%20GRU-c34b2e?style=flat-square)

## Project page

[Open the Sentiment Analysis project page](https://aKmsdfhjb.github.io/Sentiment-Analysis-Model-Comparison/)

The published page is a project overview and artifact inventory. Live prediction is intentionally not enabled in the current repository snapshot because the tracked dataset is empty and required preprocessing artifacts (TF-IDF vectorizer and GRU tokenizer) are missing. The page does not fabricate model outputs.

## Models currently tracked

- Logistic Regression — models/logistic_regression.pkl
- Multinomial Naive Bayes — models/multinomial_nb.pkl
- GRU — models/gru_model.h5 and models/my_model.keras
- Label encoder — models/label_encoder.pkl

The original notebook also describes SVM and Random Forest training, but their serialized artifacts are not currently present in the repository tree.

## Reproducible pipeline

~~~mermaid
flowchart TD
 A[Dataset: Review and Sentiment] --> B[Remove missing and duplicate rows]
 B --> C[Clean text and normalize emojis]
 C --> D[Stratified train / test split]
 D --> E[TF-IDF features]
 D --> F[Token sequences]
 E --> G[Logistic Regression]
 E --> H[Multinomial Naive Bayes]
 F --> I[GRU neural network]
 G --> J[Evaluation and comparison]
 H --> J
 I --> J
 J --> K[Save model and preprocessing artifacts]
~~~

## Repository structure

- data/dataset.csv — dataset location; currently empty in the tracked repository.
- models/ — available serialized model artifacts.
- notebooks/Code.ipynb — original training and evaluation workflow.
- report/ — project reports.
- requirement.txt — original notebook dependencies.
- index.html — static project overview.
- .github/workflows/pages.yml — GitHub Pages deployment.

## What is needed to enable inference

1. Restore the licensed dataset with Review and Sentiment columns.
2. Re-run the notebook or a reproducible training script.
3. Save the TF-IDF vectorizer and GRU tokenizer beside the models.
4. Restore or retrain the SVM and Random Forest artifacts if those models are to be included.
5. Add a tested inference API and only then enable the prediction interface.

The notebook currently contains machine-specific Windows file paths; update them to repository-relative paths before rerunning it on another machine.

## Limitations

Reported training metrics are not repeated here because the dataset and complete preprocessing artifacts are not currently available to independently reproduce them. Model outputs are experimental and should not be treated as authoritative decisions.

## License and data

Confirm the dataset license and source before restoring or redistributing review text. Avoid committing personal or private customer information.
