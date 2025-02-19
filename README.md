# Email Spam Classification

This project focuses on classifying emails as spam or not spam using machine learning models. The dataset used is `Emails.csv`, which contains email text and corresponding labels (spam = 1, not spam = 0).

## Project Overview

- **Objective**: Build and evaluate machine learning models to classify emails as spam or not spam.
- **Models Used**:
  - Logistic Regression
  - Naive Bayes (Multinomial)
- **Evaluation Metric**: Accuracy
- **Results**:
  - Logistic Regression Accuracy: **98.41%**
  - Naive Bayes Accuracy: **98.84%**

## Code Workflow

1. **Data Loading**:
   - The dataset is loaded using `pandas` and inspected using `emails.head()`.

2. **Text Preprocessing**:
   - The email text is vectorized using `CountVectorizer` from `sklearn.feature_extraction.text`.

3. **Model Training**:
   - The dataset is split into training and testing sets using `train_test_split`.
   - Two models are trained:
     - Logistic Regression
     - Naive Bayes (Multinomial)

4. **Model Evaluation**:
   - Both models are evaluated on the test set using accuracy scores.
   - Confusion matrices are generated to analyze model performance.

5. **Prediction**:
   - The models are tested on a new email: `"Hi, I am interested in your product. Please send me more information."`
   - Both models correctly classify the email as **not spam (0)**.

## Results

- **Logistic Regression Accuracy**: 98.41%
- **Naive Bayes Accuracy**: 98.84%

Both models perform exceptionally well, with Naive Bayes slightly outperforming Logistic Regression.

## How to Run the Code

1. Ensure you have the required libraries installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn

   
