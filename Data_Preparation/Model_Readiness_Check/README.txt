MODEL READINESS CHECK - Stage 2, Data Preparation
Customer Churn Analysis, Project Team 7 (WILDA26_09)
Prepared by Shivani, Data Analyst (Predictive Modelling) (Jira T7-39)

PURPOSE
Checks that Harjot's training, validation and test sets (../train_test_sets) are ready for
the churn prediction model built in Stage 3. Harjot's files are read only, never changed.
No model is trained here.

WHAT IS IN THIS FOLDER
Model_Readiness_Check.ipynb       Notebook with saved outputs (run from this folder)
figures/
  set_composition.png             Size and churn mix of the training, validation and test sets
  scaling_check.png               Scaled tenure and MonthlyCharges, training vs test
outputs/
  set_composition.csv             Rows, share, churn counts and churn rate per set
  scaling_check.csv               Mean and SD of the scaled columns per set
  overlap_check.csv               Validation and test rows that match a training profile
  class_weights.csv               Balanced class weights from the training set
docs/
  Shivani_T7-39_ANN_Architecture_Proposal.docx   Proposed ANN design for Stage 3

KEY RESULTS
- Size: training 4,930 (70%), validation 1,056 (15%), test 1,057 (15%); total 7,043.
- Composition: churn 1,308 / 280 / 281 customers; churn rate 26.5% / 26.5% / 26.6%.
- 12 numeric features plus Churn in every set; same columns; no missing values.
- Scaling: training mean 0 and SD 1; validation and test close, so no leakage.
- 81 validation rows (7.7%) and 82 test rows (7.8%) match a training profile because the
  302 duplicates were kept. Recorded as a limitation; Stage 3 results will be shown with
  and without these rows.
- Class weights: 0.6806 (no churn), 1.8846 (churn). Naive baseline: 73.4% accuracy on the
  test set and 0% recall, so recall, precision and F1 will be reported, not accuracy alone.

RELATION TO THE EARLIER SUBMISSION
This folder builds on Shivani_ANN_Repository (Version 1.0, shared at Meeting 3), which holds the
Stage 1 charter section, the T7-39 notebook with the draft ANN and benchmark set-up, and the same
ANN Architecture Proposal (identical file in docs/). The figures here are the same as in that
notebook; this folder adds the size and composition tables, the two charts and the result CSV
files, and reads the sets directly from ../train_test_sets in this repository.

HOW THE SETS WILL BE USED IN STAGE 3
Training set: fit the model. Validation set: tuning and early stopping.
Test set: used once, for the final evaluation.

HOW TO RE-RUN
pip install -r ../requirements.txt, open this folder in Jupyter and run all cells.
Keep the folder inside Data_Preparation so the path ../train_test_sets works.
