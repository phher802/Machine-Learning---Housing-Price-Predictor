# Housing Price Prediction with Machine Learning

## Overview

This project demonstrates a complete end-to-end machine learning workflow for predicting housing prices using historical data.
A baseline Linear Regression model is trained on structured housing features to estimate median house values and evaluate predictive performance on unseen data.

The goal of this project is to showcase:

- Data cleaning and preparation
- Feature/target separation
- Train–test evaluation
- Model interpretation and limitations

---

## Dataset

The dataset is based on California housing data and includes features such as:

- Median income
- Housing age
- Average rooms
- Population
- Household information

The target variable is:

- <mark>median_house_value</mark> — the median home price for a given area

_Note: The dataset includes missing values and categorical features, which are handled as part of the preprocessing pipeline._

---

Project Structure

```
ml-housing-price-predictor/
├── data/
│ └── housing.csv
├── housing_price_model.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Machine Learning Workflow

### 1. Data Loading

The dataset is loaded from a CSV file using pandas.

### 2. Data Cleaning

- Rows with missing values are handled via preprocessing
- Categorical features are excluded for this baseline model to keep the feature space numeric

_In production systems, categorical encoding and imputation pipelines would typically be used._

### 3. Feature and Target Selection

- Features (X): All numeric housing attributes
- Target (y): Median house value

This separation prevents data leakage and ensures valid evaluation.

### 4. Train–Test Split

The data is split into training and testing sets to simulate predicting prices on unseen data.

### 5. Model Training

A Linear Regression model is trained on the training dataset to learn relationships between housing features and prices.

### 6. Evaluation

Model performance is evaluated using:

- R² score
- Visual comparison of actual vs predicted prices

---

## Results & Interpretation

- The model captures the overall trend between housing features and prices.
- Predictions are compressed toward the mean, which is expected for a linear baseline model.
- High-value homes are often underestimated due to dataset constraints and linear assumptions.
- A visible price cap in the dataset creates a vertical clustering of actual values.

This model serves as a baseline, establishing a reference point for more advanced models such as tree-based or ensemble methods.

## Limitations

- Linear Regression assumes linear relationships and cannot capture complex interactions.
- The model is trained on California-specific data and does not generalize directly to other regions without retraining.
- Volatile or rapidly changing market conditions are not explicitly modeled.

---

## Real-World Applicability

In practice, models like this are used for:

- Baseline valuation estimates
- Risk and anomaly detection
- Decision support for analysts
- Monitoring market trends over time

Rather than predicting exact prices, the model provides probabilistic guidance and relative comparisons.

## Future Improvements

- Categorical feature encoding (e.g. one-hot encoding)
- Missing value imputation using pipelines
- Non-linear models (Random Forest, Gradient Boosting)
- Feature scaling and interaction terms
- Regional generalization with geographic features

---

## Technologies Used

- Python
- pandas
- scikit-learn
- matplotlib
- Jupyter Notebook

## How to Run

```
git clone <repo-url>
cd ml-housing-price-predictor
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python -m notebook
```

Open <mark>housing_price_model.ipyb</mark> and run all cells

---

Key Takeway
This project demonstrates how machine learning models learn patterns from histornical data, evaluate performance on unseen samples, and support real-world decision-making through reproducible pipelines.
