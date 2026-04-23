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

### 3. Download the Dataset

The raw datasets and model files are stored externally to keep the repository lightweight and prevent IDE performance issues. 

1. **Download the data files** from this [Google Drive Folder](https://drive.google.com/drive/folders/1WXoNUfb0tDS4we7RhfbtkjfiT_2oZUMi?usp=drive_link).
2. Place the following `.csv` files directly into the root directory of this project:
   - `description.csv`
   - `diets.csv`
   - `medications.csv`
   - `precautions_df.csv`
   - `symtoms_df.csv`
   - `workout_df.csv`

### 4. Prepare the Data Models

Before running the web application, you must train the machine learning models to generate the required preprocessed artifacts. Run the training script:

```bash
python model_training.py
```

This will generate the following artifacts (which are ignored by Git to maintain repository health):
- `hybrid_model.pkl`
- `vectorizer.pkl`
- `encoder.pkl`
- `merged_df.csv`

### 5. Run the Application

Once the `.pkl` models and `merged_df.csv` file have been generated, start the Streamlit web server:

```bash
streamlit run app.py
```

The application will be available in your browser at `http://localhost:8501`.

## Important Note regarding `.gitignore`

This project uses a strict `.gitignore` policy. **Do not commit `.pkl` or `.csv` files** to the repository. These files should be maintained locally or downloaded from the provided external link to ensure the IDE environment remains stable and the repository stays under the 100MB Git limit.

## Medical Disclaimer

⚠️ **Medical Disclaimer**: The predictions provided by this system are based on symptoms only and are not a substitute for professional medical advice. Always consult a healthcare professional for proper diagnosis and treatment.
