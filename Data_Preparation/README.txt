DATA_PREPARATION - Stage 2 Deliverable 2-1
Customer Churn Analysis, Project Team 7 (WILDA26_09)
Prepared by Harjot Kaur, Data Engineer (Jira T7-30 to T7-34)

WHAT IS IN THIS FOLDER

raw_data/
  Dataset_ATS_v2.csv            Original file, never edited (7,043 rows, 10 columns)

preprocessed_data/              PREPROCESSED DATASET
  ats_cleaned.csv               Cleaned data with original labels (7,043 x 10)
  ats_encoded.csv               Cleaned and encoded, unscaled (7,043 x 13: 12 features + Churn)
  ats_clustering_ready.csv      Encoded and standardised on all rows, for K-Means (Clustering_Analysis)
  cleaning_log.csv              All 9 preparation steps with reasons
  T7-30_Load_Data_and_Quality_Check.ipynb                   Quality check (missing values, duplicates, consistency)
  T7-31_to_T7-33_Clean_Encode_Scale_Split_Handover.ipynb    Cleaning, encoding, scaling and splitting
  figures/                      Charts from the quality check

train_test_sets/                TRAINING AND TESTING SETS
  ats_train.csv                 4,930 rows (70%), churn 26.5%
  ats_val.csv                   1,056 rows (15%), churn 26.5%
  ats_test.csv                  1,057 rows (15%), churn 26.6%
  scaler_params.csv             Training mean and SD used for scaling
  Train_Validation_Test_Sets_Note (.docx and .pdf)   Size and churn mix of each set

documentation/                  SCALING TECHNIQUES DOCUMENTATION
  Scaling_Techniques_Harjot_Kaur (.docx and .pdf)    Technique chosen, reasons, code snippets, results

requirements.txt                Python packages needed

KEY POINTS
- Missing data: none found in any of the 10 columns (checked in T7-30).
- 260 records with MultipleLines = Yes and PhoneService = No recoded to No.
- 302 exact duplicate rows kept (no customer ID; same profile and churn rate as the rest).
- Categorical variables encoded: binary fields as 1/0; InternetService and Contract one-hot encoded.
- Stratified 70/15/15 split (random_state = 42) keeps the 26.5% churn rate in every set.
- tenure and MonthlyCharges standardised (StandardScaler) with the scaler fitted on the training set only.

HOW TO RE-RUN
pip install -r requirements.txt, open preprocessed_data in Jupyter and run T7-30 first, then T7-31 to T7-33.
Paths are relative, so keep the folder structure as it is. The second notebook rebuilds every CSV file above.
