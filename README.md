# WiDS Datathon 2025: Unraveling the Mysteries of the Female Brain (Sex Patterns in ADHD) 🧠

## Team 
This team conists of 4 undergraduate students, all of whom are apart of the Break Through Tech 2024-2025 UCLA cohort.

**Team members:** Louise Marie Maganto, Souzen Khan, Zuleyka Urieta, Min Aung Paing
- Louise Marie: was in charge on training and hypertuning Neural Networks models and helped developed the Read me file.
- Souzen: was in charge on training and hypertuning Random Forest models and Read me file
- Zuleyka: was in charge on training and hypertuning Logistic Regression models and Read me file
- Min: Worked on training and hypertuning Extreme Graident Boosting and Neural Network models

## Project Highlights
The team tried the divide and conquer approach, trying four different machine learning models Neural Network, Random Forest, Logistic Regression and Extreme Graident Boosting to find the best model in predict the ADHD diagnosis and sex based on the data. Each model had the same data frames and it was up to each person's to hypertune their models. To address the imbalance dataset of sex and ADHD diagnosis random undersampling and random over sampling were used. Logistic Regression and Random Forest did not produce as great of results based on the leaderboard scores and model evaulation scores as such the focus shifted to Neural Networks. The data frame with random over sampling scored higher in accuracy when hypertuning the neural network data frame.

## Overview  
This repository contains our submission for the WiDS Datathon 2025, a global data science competition focused on advancing women's brain health research. The data utilized in this challenge was provided by the Healthy Brain Network and the Reproducible Brain Charts.  

This project is part of the **Break Through Tech AI Program** (UCLA site), which empowers students to apply AI/ML techniques to real-world challenges.  

## Challenge Objective  
The goal of this competition is to develop a **multi-outcome machine learning model** that predicts:  
1. **ADHD diagnosis** (1 = Yes, 0 = No)  
2. **Sex** (1 = Female, 0 = Male)  

Predictions are based on functional brain imaging data, socio-demographic information, emotional factors, and parenting data from children and adolescents.  

## Real World Significance  
ADHD affects about **11% of adolescents** (14% of boys and 8% of girls). However, girls with ADHD are often underdiagnosed due to differences in symptom presentation. This disparity can lead to **delayed interventions and long-term mental health challenges**.  

By leveraging **AI and machine learning**, we aim to help:  
- Improve **early identification** of ADHD in both males and females  
- Detect patterns to provide insights into **brain activity differences by sex**

## Dataset Overview
The **WiDS Datathon 2025** provides data to predict **ADHD diagnosis** and **sex** of adolescents using a combination of **functional brain imaging data** and **sociodemographic, emotional, and parenting information**. This is significant since evidence suggests that ADHD can often go undiagnosed in girls, as they tend to exhibit more inattentive symptoms which are harder to detect.

---

## Data Overview

### Training Data (1,200+ subjects)
- **Targets:**
  - **ADHD diagnosis** (0 = Other/None, 1 = ADHD)
  - **Sex** (0 = Male, 1 = Female)
  
- **Features:**
  - **Functional MRI Connectome Matrices**: Correlations between brain regions based on fMRI activity
  - **Metadata**: Handedness, parent education level, emotional scores, parenting styles (categorical and quantitative)

### Test Data (300+ subjects)
- Same data types as the training data, but without target labels

---

## Purpose & Scope
- **Building Predictive Models**: Using models such as **Neural Networks**, **Random Forest**, etc., to simultaneously predict ADHD diagnosis and sex based on brain imaging and socio-demographic information.
- **Understanding Mental Health Indicators**: Identifying patterns linking brain connectivity and personal attributes to ADHD diagnosis.
- **Practical Application**: Potential to develop diagnostic tools to assist in **early detection** and **intervention** for ADHD in adolescent females.

---

## Data Exploration and Preprocessing

The data exploration stages involved examining four separate datasets: **categorical**, **quantitative**, **functional connectome**, and **training solutions**. The primary goal was to prepare the data for predictions involving ADHD diagnosis and sex.

### Loading and Inspecting Data
- All the datasets were loaded into pandas DataFrames and inspected for basic structure.
- Missing values were identified and addressed.

### Handling Missing Values
- Missing values were handled based on the context:
  - In the **categorical data**, missing values in the `PreInt_Demos_Fam_Child_Ethnicity` column were replaced with a placeholder of `2.0`, which represented the option **"Decline to Specify"**.
  - In the **quantitative data**, missing values were filled with the **column mean** for numerical columns.

### Data Encoding
- **Categorical data** was converted to numerical format via **one-hot encoding**.
- Columns were converted to **object types** before encoding to avoid compatibility issues.

### Handling Class Imbalance
- **Random Over-Sampling**: Used to balance the ADHD and Sex labels by duplicating underrepresented examples.
- **Random Under-Sampling**: Used to reduce the number of overrepresented examples for balanced datasets.

---

## Data Visualization
Visualizations were created to understand the data distribution. These visualizations helped in identifying patterns and gaining insights into the data:

- **Count Plots**: Used for categorical variables
- **Histogram Plots with Kernel Density Estimation (KDE)**: Used for continuous numerical features
- **Pie Charts**: Created to visualize the distribution of **ADHD diagnoses** and **sex** labels.

### Visualizations from Data Exploration:
1. **Distribution of Patient Age When MRI Was Taken**
   
![image](https://github.com/user-attachments/assets/24e571c3-6bc7-41c3-a2ee-8d0b911eac93)

2. **ADHD Outcome and Sex Pie Charts**

![image](https://github.com/user-attachments/assets/a88d5f40-b724-4e60-81f4-a33e24248e5f)
![image](https://github.com/user-attachments/assets/f6e7b2bc-d760-419f-9668-936f8009e84a)

## Acknowledgments  
- **WiDS Datathon** organizers and sponsors  
- **Healthy Brain Network (HBN)** and **Reproducible Brain Charts (RBC)** for providing the dataset
- **The Break Through Tech AI UCLA Team** (Shahani Waas, Nicole Feliciano, Sofia Lee) for support
- **Our tutor, Rebecca Aurelia Dsouza,** for mentorship
- **The National Break Through Tech AI Team** 
---


