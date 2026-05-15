# UK Road Collision Severity Prediction

This project predicts road collision severity using the UK Road Safety Collision 2023 dataset.  
It was completed as a Data Mining course project and focuses on building a full machine learning workflow for a real-world imbalanced classification problem.

## Project Overview

Road collisions can result in different levels of severity, including fatal, serious, and slight collisions.  
The goal of this project is to predict the severity of a collision using road, environmental, and time-related features.

The target variable is:

- Fatal
- Serious
- Slight

The project includes data cleaning, preprocessing, feature engineering, class imbalance handling, model training, evaluation, and final model comparison.

## Dataset

The dataset used in this project is the UK Road Safety Collision 2023 dataset.

After filtering and cleaning the data, the final dataset contained:

- 104,258 records
- 83,406 training records
- 20,852 testing records

The dataset was highly imbalanced:

| Severity | Count | Percentage |
|---|---:|---:|
| Fatal | 1,522 | 1.46% |
| Serious | 23,438 | 22.48% |
| Slight | 79,298 | 76.06% |

Because of this imbalance, accuracy alone was not enough to evaluate the models.

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- imbalanced-learn
- Jupyter Notebook

## Project Workflow

The project followed these main steps:

1. Load and explore the dataset
2. Clean missing and invalid values
3. Engineer new time-based features
4. Remove leakage-related columns
5. Split the data into training and testing sets
6. Apply preprocessing pipelines
7. Handle class imbalance
8. Train multiple classification models
9. Evaluate models using macro F1-score, recall, and confusion matrices
10. Analyze feature importance

## Feature Engineering

The project created useful time-based features such as:

- Month
- Hour
- Weekend indicator
- Time period

The time period feature was divided into:

- Morning
- Afternoon
- Evening
- Night

## Class Imbalance Handling

The dataset was highly imbalanced because slight collisions were much more common than fatal collisions.

Several imbalance-handling methods were tested:

- No imbalance handling
- Class weighting
- Random undersampling
- Random oversampling
- SMOTE

SMOTE achieved the best macro F1-score in the controlled imbalance experiment.

## Models Compared

The following models were trained and compared:

- Majority Baseline
- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

Macro F1-score was used as the main evaluation metric because the dataset was imbalanced.

## Final Results

The best final model was:

**Random Forest Class Weighted Regularized**

| Model | Accuracy | Macro F1 | Weighted F1 | Fatal Recall | Serious Recall | Slight Recall |
|---|---:|---:|---:|---:|---:|---:|
| Random Forest Class Weighted Regularized | 0.5891 | 0.3816 | 0.6308 | 0.3059 | 0.3933 | 0.6524 |
| Decision Tree SMOTE Regularized | 0.6612 | 0.3727 | 0.6630 | 0.1645 | 0.2280 | 0.7987 |
| Gradient Boosting Sample Weighted | 0.4985 | 0.3399 | 0.5729 | 0.6151 | 0.2905 | 0.5578 |
| Logistic Regression Class Weighted | 0.4857 | 0.3355 | 0.5602 | 0.6217 | 0.3040 | 0.5368 |
| Majority Baseline | 0.7606 | 0.2880 | 0.6572 | 0.0000 | 0.0000 | 1.0000 |

Although the Majority Baseline had high accuracy, it failed to detect Fatal and Serious collisions.  
This shows why macro F1-score and recall were more useful than accuracy for this project.

## Best Model

The Random Forest Class Weighted Regularized model achieved the best overall macro F1-score.

The most important features included:

- Speed limit
- Hour
- Month
- Number of vehicles
- Urban or rural area
- Road class
- Light conditions
- Road type

## Data Leakage Check

A diagnostic experiment showed that some outcome-related columns caused unrealistic 100% results.

These columns were removed from the final models to prevent data leakage and make the results more realistic.

Examples of leakage-related columns included:

- number_of_casualties
- enhanced_severity_collision
- collision_injury_based
- adjusted severity columns

## Conclusion

This project shows that predicting road collision severity is challenging because of severe class imbalance and the rarity of fatal collisions.

The final model improved minority-class prediction compared with the baseline model, but the results also show that collision severity prediction should be used as a decision-support tool, not as a replacement for official investigation or expert judgment.

## Files

- `project-code.ipynb` — Main notebook containing the full project code
- `project-report.pdf` — Final project report
- `requirements.txt` — Required Python libraries

## Author

Fares Aldeeb  
Bachelor of Science in Artificial Intelligence  
University of Prince Mugrin
