# Customer Churn Analysis – Project Team 7

ACS Work Integrated Learning: Data Analytics (WILDA26_09)

## Goal
Segment telecom customers with K-Means clustering, predict churn with an
Artificial Neural Network (ANN), and recommend targeted retention strategies.

## Team
| Member | Role |
|---|---|
| Saurabh Desale | Project Manager |
| Harjot | Data Engineer |
| Dilina | Data Analyst – Clustering |
| Shivani | Data Analyst – Predictive Modelling |
| Shehroz | Business Analyst |

## Dataset
Dataset_ATS_v2.csv – 7,043 telecom customers, 10 columns, 26.5% churn rate.

## Folder structure

### Data_Preparation
| Folder | Contents | Owner |
|---|---|---|
| raw_data | Original dataset (Dataset_ATS_v2.csv). Do not edit | Saurabh |
| preprocessed_data | Cleaned and encoded dataset, plus the preparation notebook | Harjot |
| train_test_sets | Training, validation and test sets (70/15/15 stratified split), plus a split summary of size and churn mix | Harjot |
| documentation | Scaling techniques document with code snippets, and the cleaning log | Harjot |

### Clustering_Analysis
| Folder | Contents | Owner |
|---|---|---|
| optimal_clusters | Elbow method chart and the reason we chose k = 4 | Dilina |
| kmeans_model | Trained K-Means model (kmeans_model.pkl), scaler (scaler.pkl) and notebook | Dilina |
| cluster_visualisations | Labelled cluster charts and a business insights document | Dilina, Shehroz |

## How we work
Everyone uploads their work directly to the **main** branch, into the folder
for their deliverable. Saurabh checks each upload against the rubric.

## Rules
- Never edit files in raw_data.
- Use clear file names, e.g. train_set.csv, elbow_chart.png.
- Write a short, clear message for every commit.

## Links
- Jira: https://saurabhdesale1999.atlassian.net/jira/software/projects/T7/boards/2/timeline
- Confluence: [add Data Repository link]
