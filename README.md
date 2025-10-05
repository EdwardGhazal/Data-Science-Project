# Project: Analysis of Hospital Data

## 1. Project Goal
The goal of this project is to analyze hospital admission data to uncover meaningful trends in patient demographics, medical results, and related factors. By identifying these patterns, the project aims to support data-driven decision-making and improve healthcare management strategies.

***
## 2. Dataset
This analysis is based on the **"Healthcare"** dataset, which contains over 50,000 anonymized appointment records.

* **Source:** [Kaggle](https://www.kaggle.com/datasets/prasad22/healthcare-dataset)
* **Contents:** Each record includes patient characteristics (age, gender, medical condition conditions) and healthcare details (date of admission, doctor, hospital).

***
## 3. Key Questions to Answer
This analysis seeks to answer the following questions:
* WWhat is the most significant finding regarding the distribution of patient test results, and what is the practical impact of this finding?
* Who are the patients we are dealing with, based on their age distribution?
* What is the primary conclusion drawn from the correlation heatmap of the numerical variables?
* What is the primary conclusion regarding the relationship between age and cancer rate as shown in the bar chart?
* What is the primary conclusion regarding the relationship between blood type and cancer rate as shown in the bar chart?

***
## 4. Setup & Usage
To run this analysis, you will need Python with the Pandas library.

1.  **Prerequisites:** Make sure you have the required library installed:
    ```bash
    pip install pandas
    ```
2.  **Data Cleaning:** Place the dataset (`Data.csv`) in the same directory as the analysis script. The initial Python script will load this data, clean column names, correct data types, and remove invalid records.

***
## 5. Inferred Database Schema (ERD)
This project uses a single CSV file. If the data were stored in a relational database, it would be structured with the following relationships:

* A **Patient** goes to one and only one **Hospital**.
* A **Hospital** have many **Doctors**.
* A **Patient** can have **Admissions**.
* A **Doctor** can treat many **Patients** across different **Admissions**.
* A **Hospital** can host many **Admissions** for different **Patients**.

**[Patients Table]**
* `Name` (Primary Key)
* `Gender`
* `Age`
* `Blood Type`
* `Medical Condition`
* `Insurance Provider`

**[Hospital Table]**
* `Name` (Primary Key)
* `Room Number` 

**[Doctor Table]**
* `Name` (Primary Key)
* `Hospital_Name` (Foreign Key)

**[Admission Table]**
* `patient_name` (Foreign Key)
* `doctor_name` (Foreign Key)
* `Nahospital_nameme` (Foreign Key)
* `date_of_admission`
* `discharge_date`
* `admission_type`
* `billing_amount`
* `medication_name`
* `test_results`