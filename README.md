# UK Road Collision Severity Prediction

A data mining and machine learning project for predicting road collision severity using the UK Road Safety Collision 2023 dataset.

This project focuses on building a complete machine learning workflow for a real-world classification problem with severe class imbalance.

---

## Project Overview

Road collisions can result in different levels of severity, such as fatal, serious, or slight collisions.

The goal of this project is to predict the severity of a road collision using road, environmental, and time-related features.

The target variable is:

- Fatal
- Serious
- Slight

The project includes:

- Data cleaning
- Exploratory data analysis
- Feature engineering
- Missing value handling
- Data leakage checking
- Class imbalance handling
- Model training
- Model comparison
- Evaluation using macro F1-score and recall
- Feature importance analysis

---

## Dataset

The dataset used in this project is the UK Road Safety Collision 2023 dataset from the UK Department for Transport.

The dataset is not included in this repository because of file size.  
Instead, the notebook downloads it automatically from the official source.

Dataset file used:

```text
dft-road-casualty-statistics-collision-2023.csv
