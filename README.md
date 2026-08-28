# Dry Bean Variety Classification Using Machine Learning

## Project Title

**Dry Bean Variety Classification Using Machine Learning**

## Objective

The objective of this project is to develop a machine learning classification system that can automatically identify different varieties of dry beans based on their physical and geometric characteristics.

Multiple machine learning classification algorithms were trained and evaluated. Hyperparameter tuning was then performed on the best-performing model to improve its classification performance.

## Dataset Used

**Dataset Name:** Dry Bean Dataset

**Source:** UCI Machine Learning Repository

**Original Source:** https://archive.ics.uci.edu/dataset/602/dry+bean+dataset

The dataset contains **13,611 dry bean samples** belonging to **7 different varieties**:

- BARBUNYA
- BOMBAY
- CALI
- DERMASON
- HOROZ
- SEKER
- SIRA

The dataset contains **16 numerical features** describing the physical and geometric characteristics of the beans.

### Features

The input features include:

- Area
- Perimeter
- MajorAxisLength
- MinorAxisLength
- AspectRation
- Eccentricity
- ConvexArea
- EquivDiameter
- Extent
- Solidity
- roundness
- Compactness
- ShapeFactor1
- ShapeFactor2
- ShapeFactor3
- ShapeFactor4

The target variable is **Class**, which represents the dry bean variety.

## Project Workflow

The project was implemented using the following workflow:

1. Data collection
2. Data loading and inspection
3. Data cleaning
4. Descriptive statistical analysis
5. Exploratory Data Analysis (EDA)
6. Correlation analysis
7. Outlier detection using boxplots and the IQR method
8. Target encoding using LabelEncoder
9. Train-test split using stratification
10. Feature selection using SelectKBest with ANOVA F-score
11. Feature scaling using StandardScaler
12. Machine learning model training
13. Model evaluation
14. Confusion matrix analysis
15. Hyperparameter tuning
16. Final model selection
17. Saving the trained model and preprocessing objects

## Exploratory Data Analysis

EDA was performed to understand the structure and distribution of the dataset.

The following analyses were performed:

- Dataset inspection
- Missing-value checking
- Descriptive statistics
- Class distribution analysis
- Feature correlation analysis
- Correlation heatmap
- Outlier detection using boxplots
- IQR-based outlier identification

Potential outliers were retained because they may represent genuine physical measurements of dry beans rather than data-entry errors.

## Feature Selection

Feature selection was performed using:

**SelectKBest with ANOVA F-score**

The top 10 features were selected based on their statistical relationship with the target classes.

The feature selector was fitted only on the training data and then applied to the test data.

## Feature Scaling

The selected features were standardized using **StandardScaler**.

The scaler was fitted on the training data and then used to transform both the training and testing data.

## Models Used

Five machine learning classification algorithms were evaluated.

### 1. Logistic Regression

Logistic Regression was selected as a baseline classification algorithm because it is simple, efficient, interpretable, and suitable for multiclass classification.

### 2. Decision Tree

Decision Tree was selected because it can model nonlinear relationships and is easy to interpret.

### 3. Random Forest

Random Forest was selected because it combines multiple decision trees and can capture complex relationships between features and classes.

### 4. Support Vector Machine (SVM)

SVM was selected because it is effective for classification problems with complex decision boundaries and works well with scaled numerical features.

### 5. K-Nearest Neighbors (KNN)

KNN was selected as a distance-based classification method. Feature scaling is important for KNN because predictions depend on distances between observations.

## Initial Model Results

The initial models achieved the following test accuracies:

| Model | Accuracy |
|---|---:|
| Logistic Regression | 90.89% |
| Decision Tree | 87.40% |
| Random Forest | 90.41% |
| SVM | 90.41% |
| KNN | 90.38% |

Logistic Regression achieved the highest initial test accuracy.

## Hyperparameter Tuning

Hyperparameter tuning was performed for Logistic Regression using **GridSearchCV**.

The following parameters were tested:

- C: 0.01, 0.1, 1, 10, 100
- Solver: lbfgs, liblinear

Three-fold cross-validation was used with **macro F1-score** as the scoring metric.

The tuned Logistic Regression model was selected as the final model.

## Key Results

The final tuned Logistic Regression model achieved the following results on the test set:

| Evaluation Metric | Score |
|---|---:|
| **Accuracy** | **91.63%** |
| **Macro Precision** | **93.33%** |
| **Macro Recall** | **92.77%** |
| **Macro F1-score** | **93.01%** |
| **Weighted F1-score** | **91.66%** |

### Best-Performing Model

**Tuned Logistic Regression** was selected as the final model.

It achieved:

- **91.63% test accuracy**
- **93.01% macro F1-score**
- **91.66% weighted F1-score**

The tuned Logistic Regression model performed better than the other evaluated models.

## Confusion Matrix

A confusion matrix was generated for the final tuned Logistic Regression model to examine the classification performance for each of the seven dry bean varieties.

The confusion matrix is included in the Jupyter/Colab notebook.

## Saved Model

The final trained model was saved using **joblib**.

The repository contains the following saved objects:

- `logistic_model.pkl` — final tuned Logistic Regression model
- `feature_selector.pkl` — SelectKBest feature selection object
- `scaler.pkl` — StandardScaler preprocessing object
- `label_encoder.pkl` — LabelEncoder used for the target classes

These files allow the trained model and its preprocessing steps to be reused without retraining.

## Conclusion

The Dry Bean Variety Classification project successfully developed a machine learning system for classifying seven varieties of dry beans using their physical and geometric characteristics.

Five classification algorithms were compared. Logistic Regression achieved the best initial performance, and hyperparameter tuning further improved its performance.

The final tuned Logistic Regression model achieved **91.63% accuracy** and a **93.01% macro F1-score** on the test dataset.

These results demonstrate that machine learning can effectively classify dry bean varieties based on their measured physical characteristics.

## Future Work

Several improvements can be explored in future work:

- Advanced feature selection techniques
- More extensive hyperparameter optimization
- Ensemble learning methods
- Cross-validation with additional evaluation metrics
- Real-world image-based dry bean classification
- Deployment as an interactive web application using Streamlit

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Jupyter Notebook / Google Colab
- Streamlit

## Repository Contents

```text
Dry-Bean-Classification/
│
├── Dry_Bean_Classification.ipynb
├── Dry_Bean_Dataset.csv
├── logistic_model.pkl
├── feature_selector.pkl
├── scaler.pkl
├── label_encoder.pkl
├── app.py
├── requirements.txt
└── README.md
```

## Author

**Jaina George**
