# MediScan - Disease Prediction System

MediScan is an advanced Disease Prediction and Health Recommendation System. It takes symptoms as input and uses a hybrid machine learning model to predict potential diseases, subsequently offering corresponding descriptions, dietary, medical, workout, and precaution recommendations.

The frontend is built with [Streamlit](https://streamlit.io/), making it interactive and user-friendly.

## Features

- **Symptom-based Disease Prediction**: Enter up to four symptoms to receive a predicted condition.
- **Hybrid Machine Learning Model**: Uses a voting classifier that combines Random Forest, XGBoost, and Gradient Boosting for highly accurate predictions.
- **Comprehensive Recommendations**: Provides treatment (medications), lifestyle (diet and workout), and actionable precautions.
- **Patient Records System**: Securely stores patient data locally in CSV format and allows exporting via CSV or Excel.

## Setup Instructions

### 1. Prerequisites

Ensure you have Python 3.8+ installed on your system.
This project uses several data and machine learning libraries including `pandas`, `scikit-learn`, `xgboost`, and `streamlit`.

### 2. Install Dependencies

Clone this repository and navigate to its root directory. Then install the required packages:

```bash
pip install -r requirements.txt
```

### 3. Prepare the Data Models

Before running the web application, you must train the machine learning models and generate the required preprocessed `.csv` and `.pkl` files.

Ensure the raw CSV data files are present in your directory:
- `description.csv`
- `diets.csv`
- `medications.csv`
- `precautions_df.csv`
- `symtoms_df.csv`
- `workout_df.csv`

Then run the training script:

```bash
python model_training.py
```

This will train the hybrid model and generate the following artifacts (note: these are `.gitignore`d intentionally to prevent large binary and data files from bloating the git history):
- `hybrid_model.pkl`
- `vectorizer.pkl`
- `encoder.pkl`
- `merged_df.csv`

### 4. Run the Application

Once the `.pkl` models and `merged_df.csv` file have been generated successfully, you can start the Streamlit web server:

```bash
streamlit run app.py
```

The application will be available in your browser at `http://localhost:8501`.

## Important Note regarding `.gitignore`

The generated files (`*.pkl` and `*.csv`) have been added to the `.gitignore`. **Do not commit these files** to the repository. They should be dynamically generated locally by running `python model_training.py` as detailed above.

## Medical Disclaimer

⚠️ **Medical Disclaimer**: The predictions provided by this system are based on symptoms only and are not a substitute for professional medical advice. Always consult a healthcare professional for proper diagnosis and treatment.
