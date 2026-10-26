# Multiple Disease Prediction

A Streamlit web app that predicts the likelihood of three conditions from manually entered health measurements, using pre-trained machine learning models saved as pickle files.

## What it does

The sidebar menu offers three prediction pages:

- **Diabetes Prediction** — enter 8 measurements (pregnancies, glucose, blood pressure, skin thickness, insulin, BMI, diabetes pedigree function, age) and get a diabetic / not diabetic result.
- **Heart Disease Prediction** — enter 13 measurements (age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, resting ECG, maximum heart rate, exercise-induced angina, ST depression, slope, major vessels, thal) and get a heart disease / no heart disease result.
- **Parkinsons Prediction** — enter 22 voice measurements (MDVP fundamental frequencies, jitter, shimmer, NHR, HNR, RPDE, DFA, spread, D2, PPE) and get a Parkinson's / no Parkinson's result.

Each page loads its model from `saved_models/` with pickle and shows the result when its test-result button is pressed. The sidebar and main-area styling come from `sidebar.css` and `style.css`.

## Tech stack

- Python with Streamlit for the web app and `streamlit-option-menu` for the sidebar navigation
- Pre-trained models loaded with pickle (`.sav` files in `saved_models/`)
- Datasets in `D.csv`, `H.csv` and `P.csv` at the repo root
- Custom CSS for the sidebar and content area

## How to run

```bash
pip install -r requirements.txt
streamlit run main.py
```

This launches the Streamlit app in your default web browser.

**Setup note:** `main.py` currently loads the three models from hardcoded Windows paths. Before running on another machine, update those three paths to point at the `saved_models/` files in this repo.

## Project structure

```
main.py           # Streamlit app: sidebar navigation and the three prediction pages
saved_models/     # Pre-trained diabetes, heart disease and Parkinson's models (.sav)
D.csv, H.csv, P.csv  # Datasets
collab files/     # Colab notebooks
streamlit/        # Streamlit-related files
sidebar.css       # Sidebar styling
style.css         # Main content styling
flowchart.jpg     # Project flowchart
requirements.txt  # Python dependencies
```

## Status

A completed student-style ML demo. Its predictions are model outputs for demonstration only — not a medical diagnosis, and not a substitute for professional medical advice.
