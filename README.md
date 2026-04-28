# DPEL-Mini-Project
# Spotify Genre Classification & Feature Analysis (VibeRadar)

## Overview

This project implements a complete data pipeline for analyzing and classifying Spotify tracks using audio features. It combines data preprocessing, exploratory data analysis (EDA), and machine learning to predict music genres.

---

## Problem Statement

Music recommendation systems rely heavily on structured audio features. This project explores how numerical and textual features can be used to classify songs into genres and uncover patterns in musical characteristics.

---

## Dataset

- Source: Spotify Tracks Dataset (Kaggle)
- ~100,000 tracks across ~125 genres
- Features include:
  - danceability, energy, tempo, loudness
  - acousticness, instrumentalness, valence
  - metadata (artist, album, popularity)

---

## Approach

### 1. Data Preprocessing

- Controlled data degradation (for robustness testing)
- Missing value handling:
  - Mean imputation (numerical)
  - KNN imputation
  - Mode imputation (categorical)
- Duplicate removal (track-level and full-row)
- Outlier clipping
- Data type standardization

---

### 2. Feature Engineering

- Label Encoding for high-cardinality target (`track_genre`)
- One-Hot Encoding for binary features (`explicit`)
- TF-IDF vectorization on `artists`
- Standardization using `StandardScaler`

---

### 3. Exploratory Data Analysis

- Univariate:
  - Histograms, boxplots
- Bivariate:
  - Correlation heatmaps
  - Scatter plots
- Multivariate:
  - Radar plots

Example insight (from report):
- Loudness and energy show strong positive correlation  
- Acousticness negatively correlates with energy :contentReference[oaicite:0]{index=0}  

---

### 4. Model Building

Models used:

- Logistic Regression
- Random Forest Classifier

Pipeline includes:
- Numerical scaling
- TF-IDF transformation for text features

---

### 5. Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score (macro averaged)

---

## Results

| Model               | Accuracy | Precision | Recall | F1 Score |
|--------------------|---------|----------|--------|---------|
| Logistic Regression | ~75%    | ~77%     | ~71%   | ~72%    |
| Random Forest       | ~41%    | ~65%     | ~36%   | ~36%    |

Key Observation:
- Logistic Regression outperforms Random Forest due to high-dimensional sparse TF-IDF features :contentReference[oaicite:1]{index=1}  

---

## System Capabilities

- Genre prediction from input song
- Confidence score output
- Handles unseen songs using feature extraction pipeline

---


## Project Structure
├── spotify_tracks.csv
├── DPEL Mini Project.ipynb
├── DPEL Report.pdf
├── README.md
├── requirements.txt


---

## How to Run

### 1. Install dependencies
pip install -r requirements.txt


### 2. Run Notebook
Open:
DPEL Mini Project.ipynb


---

## Limitations

- Genre classification only (no full recommendation system)
- TF-IDF limited to artist metadata (no lyrics)
- No hyperparameter tuning
- Dataset artificially modified (controlled degradation)

---

## Future Improvements

- Use embeddings (audio + text)
- Add lyrics-based features
- Build full recommendation engine (cosine similarity)
- Deploy as API or web app
- Use deep learning models for classification

---

## Author

- Ishaan Chand
- Amey Gujar
- Ishaan Bhatt
- Dharmit Shah

---

## License

For academic and research use.



