# Balanced-fraud-Detection-Model

Project Overview

This project is a Streamlit-based web application powered by a machine learning model designed to detect fraudulent financial transactions. The model is a LogisticRegression classifier that is trained on a synthetic dataset of financial transactions.  

The model is encapsulated within a Scikit-learn Pipeline, which includes preprocessing steps like StandardScaler for numerical features and OneHotEncoder for categorical features. This pipeline is then serialized using joblib into a file named fraud_detection_pipeline.pkt.  

The model is encapsulated within a Scikit-learn Pipeline, which includes preprocessing steps like StandardScaler for numerical features and OneHotEncoder for categorical features. This pipeline is then serialized using joblib into a file named fraud_detection_pipeline.pkt.  

The Streamlit app, Fraud_detection.py, loads this pre-trained pipeline to make real-time fraud predictions based on user input.

Dataset

The model was trained on a synthetic dataset for financial fraud detection. The dataset contains various transaction details, such as:

* step: The time step of the transaction.

* type: The type of transaction (e.g., CASH_IN, CASH_OUT, TRANSFER, etc.).

* amount: The amount of the transaction.

* oldbalanceOrg: The sender's balance before the transaction.

* newbalanceOrig: The sender's balance after the transaction.

* oldbalanceDest: The receiver's balance before the transaction.

* newbalanceDest: The receiver's balance after the transaction.

* isFraud: The target variable, indicating a fraudulent transaction.

* isFlaggedFraud: A flag set by the system for certain transactions.

link for Dataset : https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset?resource=download

Model Analysis

The analysis_model.ipynb Jupyter notebook provides a detailed exploration of the data and the development of the machine learning pipeline. Key findings from the analysis include:

* Data Exploration: The dataset is relatively clean with no missing values. The target variable (isFraud) is highly imbalanced, with a very small percentage of fraudulent transactions.

* Feature Engineering: New features, balanceDiffOrig and balanceDiffDest, were created to capture the difference between old and new balances, which can be indicative of fraud.

* Model Training: A LogisticRegression model was chosen, and its class_weight parameter was set to balanced to address the class imbalance issue.

* Evaluation: The model achieved a high accuracy score, but the confusion matrix and classification report reveal its performance in identifying the minority class (fraudulent transactions). The recall for fraudulent transactions is high, indicating the model is good at catching fraud, while the precision is lower due to false positives.

 Installation and Setup

1. Clone the repository:

git clone <your-repository-link>
cd Balanced-fraud-Detection-Model

2. Install the required libraries:

pip install -r requirements.txt
(Note: You will need to create a requirements.txt file listing all dependencies.)

3. Run the Streamlit application:

streamlit run Fraud_detection.py

How to Use the Application

1. Open the web application: Once the Streamlit app is running, open your web browser and navigate to the local URL provided in the terminal (usually http://localhost:8501).

2. Enter transaction details: Use the input fields to enter the details of a transaction you want to check. You can select the transaction type from a dropdown menu and enter numerical values for the balances and amount.

3. Click "Predict": Press the "Predict" button to get a real-time prediction from the model. The app will indicate whether the transaction is "Fraud" or "Not Fraud."

File Descriptions

* Fraud_detection.py: The main Python script for the Streamlit web application.

* fraud_detection_pipeline.pkt: The pre-trained machine learning pipeline, saved using joblib.

* analysis_model.ipynb: A Jupyter Notebook containing the data exploration, model training, and evaluation code.

* .gitattributes: A Git LFS configuration file.

* requirements.txt: (To be created) A file listing the Python dependencies required for the project.

This README.md file provides a detailed overview of your project, making it easy for others to understand and run your code. It's a great way to showcase your work on GitHub.

