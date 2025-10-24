COVID-19 Clinical Trials — EDA & Machine Learning Project

Overview
---------
This project explores a real-world dataset of COVID-19 clinical trials collected from ClinicalTrials.gov. 
The goal is to:
1. Perform Exploratory Data Analysis (EDA) to uncover trends in global COVID-19 trials — such as study phases, status, and locations.  
2. Build a basic Machine Learning (ML) model to predict a study’s status (e.g., Completed, Recruiting, or Active) using structured trial features.

It’s designed as a portfolio-quality internship project demonstrating practical data cleaning, visualization, and beginner ML modeling skills.

Dataset
-------
Source: ClinicalTrials.gov COVID-19 Studies
File: data/covid_clinical_trials.csv
Rows: ~5,700
Columns: ~25

Key Columns:
- Status – Current trial progress (Completed, Recruiting, etc.)
- Phases – Study phase (Phase 1–4)
- Conditions – Type of disease or condition studied
- Enrollment – Number of participants
- Study Type – Observational or Interventional
- Country – Extracted from Locations
- Gender, Age, Sponsor, Study Designs, etc.

Project Structure
-----------------
COVID-19 Clinical Trials (EDA + ML)/
│
├── data/
│   └── covid_clinical_trials.csv
│
├── covid_eda_ml.ipynb        ← Main notebook (EDA + ML)
├── requirements.txt           ← Required libraries
├── README.txt                 ← Project documentation

Exploratory Data Analysis (EDA)
-------------------------------
Steps performed:
1. Loaded and inspected data (shape, types, nulls)
2. Cleaned columns and handled missing data
   - Dropped irrelevant fields (NCT Number, URL, Study Documents)
   - Filled missing categorical values with labels like "Missing_<col>"
   - Imputed numeric Enrollment using median  
3. Created new feature Country extracted from Locations
4. Simplified Status into 3 major categories (Completed, Recruiting, Active/Other)

Visual insights:
- The United States, France, and UK had the highest number of trials.  
- Most studies were in Phase 2 or Phase 3.  
- Majority of studies were targeted at adult participants.  
- Enrollment sizes varied massively — highly skewed distribution.

Machine Learning Model
----------------------
A simple Random Forest Classifier was trained to predict the Status of a trial.

Features used:
- Enrollment (numeric)
- Phases
- Study Type
- Country
- Gender

Results:
- Accuracy: ~70–75% (varies per random seed)
- Top predictive factors: Phases, Country, and Enrollment

This ML section shows the ability to preprocess mixed-type data, encode categorical features, and evaluate a baseline classifier.

Key Insights
------------
- Most trials were registered in high-income countries (U.S., Europe).
- Trial activity peaked during mid-2020 — early vaccine and drug research phase.
- Majority of trials were interventional and focused on adult populations.
- The model can moderately predict trial status using simple metadata — better text features could boost accuracy.

Next Steps (Improvement Ideas)
------------------------------
1. Perform feature engineering on text fields (Title, Interventions) using TF-IDF.  
2. Apply cross-validation and hyperparameter tuning (GridSearchCV).  
3. Visualize feature importance using SHAP or Permutation Importance.  
4. Build a simple Streamlit dashboard for visual insights.  

Tech Stack
-----------
Category      | Tools Used
---------------|-------------
Language       | Python 3.x
Libraries      | Pandas, NumPy, Matplotlib, Scikit-learn
IDE            | Jupyter Notebook
Domain         | Data Analytics & Machine Learning

Author
-------
Vanisha Soni  
Data Analytics Intern | Guru Nanak Dev University, Amritsar  
Focus: EDA, Data Visualization, Machine Learning  
