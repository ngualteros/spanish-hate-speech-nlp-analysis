
# Spanish Hate Speech — NLP & Linguistic Feature Analysis

## Overview

This project explores Natural Language Processing (NLP) techniques to analyze linguistic and statistical differences between Spanish-language comments labeled as hate speech and non-hate speech.

Developed as part of my Master's degree in Artificial Intelligence at Universidad Internacional de La Rioja (UNIR), the project uses Python and spaCy to process text, extract linguistic features, identify named entities, and compare patterns across the two categories.

The objective is to investigate whether linguistic characteristics can provide useful information for distinguishing between hateful and non-hateful comments.

This project focuses on exploratory analysis and feature extraction rather than training a hate speech classification model.

## Technologies

- Python
- spaCy
- pandas
- Matplotlib
- Jupyter Notebook
- Natural Language Processing (NLP)
- Named Entity Recognition (NER)
- Tokenization
- Lemmatization
- Morphological Analysis
- Exploratory Data Analysis (EDA)

## Dataset

The project uses a Spanish-language comment corpus with existing hate speech intensity labels.

The original dataset contains the following fields used in the analysis:

- `CONTENIDO A ANALIZAR`: Text content.
- `INTENSIDAD`: Hate speech intensity label.

Comments with an intensity greater than zero are considered part of the hate speech group, while comments with an intensity equal to zero belong to the non-hate speech group.

The analysis uses a subset of up to 100,000 records for several processing tasks, balancing computational requirements and execution time.

The original dataset is not included in this repository due to its size and pending redistribution permission verification.

See `data/README.md` for dataset setup instructions.

## Project Structure

```text
spanish-hate-speech-nlp-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── 01_text_feature_analysis.ipynb
├── data/
│   └── README.md
└── results/
    └── .gitkeep
```

## Methodology

### 1. Data Loading and Preprocessing

The dataset is loaded using pandas, with the following preprocessing steps:

- Read semicolon-separated CSV records.
- Use Latin-1 encoding for dataset compatibility.
- Remove records with missing text values.
- Reset DataFrame indices.
- Prepare the dataset for linguistic analysis.

### 2. Text Processing with spaCy

The project uses the pretrained Spanish language model `es_core_news_md`.

Linguistic processing includes:

- Tokenization.
- Word counting.
- Lemmatization.
- Named Entity Recognition.
- Morphological feature extraction.

### 3. Statistical Text Analysis

The notebook investigates:

- Total number of corpus records.
- Total word count.
- Average number of words per comment.
- Word-count distributions.
- Linguistic differences between hate and non-hate comments.

### 4. Named Entity Recognition

Named Entity Recognition is used to identify and analyze entities in Spanish-language comments.

The analysis compares:

- Percentage of comments containing named entities.
- Percentage of comments containing person entities.
- Distribution of recognized entity types across both groups.

### 5. Morphological Analysis

The project examines grammatical characteristics of text, including combinations of:

- Masculine singular.
- Masculine plural.
- Feminine singular.
- Feminine plural.

These features are compared between comments labeled as hate speech and non-hate speech.

### 6. Lemmatization and Frequency Analysis

The notebook extracts and compares frequent lemmas from both groups.

Python's `collections.Counter` is used to calculate frequencies and identify the most common lemmas.

### 7. Exploratory Visualization

The project includes statistical analysis and visualizations using Matplotlib to investigate relationships between linguistic features and hate speech labels.

## Key Findings

The original exploratory analysis investigates whether comment length, named entities, morphological characteristics, and lemma frequencies differ between the two groups.

One observation discussed in the notebook is that longer comments appear more frequently in the non-hate group in the analyzed data.

This is an exploratory observation and does not establish a reliable classification rule or causal relationship.

The project does not report predictive classification performance because no hate speech classifier was trained.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/ngualteros/spanish-hate-speech-nlp-analysis.git
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Install the Spanish spaCy Model

```bash
python -m spacy download es_core_news_md
```

### 5. Prepare the Dataset

Place the original CSV file inside the `data/` directory:

```text
data/02Dataset_sin_procesar.csv
```

Update the dataset path in the notebook to:

```python
filename = "../data/02Dataset_sin_procesar.csv"
```

### 6. Run the Notebook

```bash
jupyter notebook
```

Open:

`notebooks/01_text_feature_analysis.ipynb`

Execute the cells sequentially.

**Note:** The original notebook contains computationally intensive loops and was developed using the academic environment. Execution time depends on dataset size and available hardware.

## Future Improvements

Potential improvements include:

- Optimize large-scale text processing using `nlp.pipe()`.
- Reduce repeated linguistic processing operations.
- Organize feature extraction into reusable Python functions.
- Add automated tests for text preprocessing.
- Evaluate whether extracted features improve a supervised classification model.
- Document processing times and resource consumption.
- Improve reproducibility across environments.

These enhancements are proposed future work and are not claimed as completed implementations.

## Academic Context

This project was developed in April 2025 as part of the Natural Language Processing course of the Master's in Artificial Intelligence at Universidad Internacional de La Rioja (UNIR).

The implementation builds on an academic activity using spaCy and includes my analysis, code modifications, statistical exploration, and written explanations.

## Author

**Nicolás Gualteros Pérez**

Systems Engineer | Master's in Artificial Intelligence

AI Engineering | Machine Learning | NLP | AI Automation

LinkedIn: https://www.linkedin.com/in/nicogualteros
