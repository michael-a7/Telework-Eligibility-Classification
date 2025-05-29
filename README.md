# Comparison of Machine Learning Classification Models on USAJobs Data

# Overview

This Python project compares the results of four different classification models on job listings retrieved from the USAJobs.gov dataset. The goal is to evaluate the relationship between a
job's **telework eligibility** and the following independent variables:
- Listed territory (state or territory code)
- Listed minimum pay
- Whether the job is listed in multiple locations

As demonstrated in the iPython file, the high accuracy and F1 scores of the **K-Nearest Neighbors** and **Decision Tree** indicate that  **certain job features (location, minimum pay, single/multi-state status) are provide meaningful predictive value in ensuring whether a job is telework eligible**.

**The results of this analysis may be useful for job seekers, recruiters, and policy analysts in estimating fair wage values or identifying telework trends across states (among other use cases).**

---

## Project Workflow
**1. Setup and Data Extraction**
- Retrieve data from the USAJobs.gov API
- Compile the data into a Pandas dataframe

The file `usa_jobs_2025-05-05_22-00-27.json` is included in this repository to ensure reproducibility of the analysis.

**2. Dataset Cleaning**
- Unnest nested values
- Merge and derive necessary variables
- Drop irrelevant columns
- Create a boolean field indicating whether a job is listed in multiple states

**3. Exploratory Data Analysis (EDA)**
  - Visualize trends including:
    - Distribution of starting pay
    - Job listings by state/territory
    - Comparison of single vs. multi-state listings
    - Frequency of telework-eligible jobs

**4. Data Preparation for Modeling**
  - Perform train/test split
  - Apply K-Fold target encoding to the CountrySubDivisionCode (stat/territory) feature

**5. Machine Learning Classification Tests**
  - Models used:
    - Logistic Regression
    - K-Nearest Neighbors
    - Decision Tree Classifier
    - Support Vector Machine
- Produce accuracy scores, weighted precision scores, weighted recall scores, and weighted F1 scores for each model

**6. Summary**
- Compare scores for each model
- Draw conclusions

## Tech Stack
- **Backend:** Python 3 (via [Google Colab](https://colab.research.google.com/))
- **Libraries:** Pandas, Numpy, scikit-learn, Matplotlib, requests, json, category_encoders, re, datetime
- **Data Source:** [USAJobs.gov](https://www.usajobs.gov/) API

## Acknowledgments
- Data retrieved from [USAJobs.gov](https://www.usajobs.gov/) API
- Methodology for retrieving best n for K-Nearest Neigbors model was adapted from *Introduction to Machine Learning With Python (2017)* by Müller and Guido, (pg 38-40)
- In addition, work and documentation for this project were created using assistance from AI tools (ChatGPT, Gemini). This assistance was mainly for the purpose of troubleshooting and ensuring adherence to best practices.
