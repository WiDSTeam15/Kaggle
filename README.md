# WiDS Datathon 2025: Unraveling the Mysteries of the Female Brain (Sex Patterns in ADHD) 🧠

## Overview  
This repository contains our submission for the WiDS Datathon 2025, a global data science competition focused on advancing women's brain health research. The data utilized in this challenge was provided by the Healthy Brain Network and the Reproducible Brain Charts.  

This project is part of the **Break Through Tech AI Program** (UCLA site), which empowers students to apply AI/ML techniques to real-world challenges.  

---

## Team 
This team consists of 4 undergraduate students, all of whom are a part of the Break Through Tech 2024-2025 UCLA cohort.

**Team members:** Louise Marie Maganto, Souzen Khan, Zuleyka Urieta, Min Aung Paing
- Louise Marie: was in charge of training and hypertuning Neural Networks models and helped develop the Read Me file.
- Souzen: was in charge of training and hypertuning Random Forest models and Read Me file
- Zuleyka: was in charge of training and hypertuning Logistic Regression models and Read Me file
- Min: Worked on training and hypertuning Extreme Gradient Boosting and Neural Network models

## Project Highlights
The team tried the divide and conquer approach, trying four different machine learning models, Neural Network, Random Forest, Logistic Regression, and Extreme Gradient Boosting, to find the best model for predicting ADHD diagnosis and sex based on the data. Each model had the same data frames, and it was up to each person to hyper tune their models. To address the imbalance dataset of sex and ADHD diagnosis, random undersampling and random over-sampling were used. Logistic Regression and Random Forest did not produce as great of results based on the leaderboard scores and model evaluation scores. As such, the focus shifted to Neural Networks. The data frame with random over-sampling scored higher in accuracy when hypertuning the neural network data frame.

## Setup and Execution 
If you wish to run any of our models yourself, simply download the ipynb file of the corresponding model. You can run the file locally through Google Colab, Visual Studio, or your preferred IDE. You will need to have the necessary files downloaded as well, which can be found in this Github Repo in the "Supplemental files."

## Project Overview and Challenge Objective  
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
The **WiDS Datathon 2025** provides data to predict **ADHD diagnosis** and **sex** of adolescents using a combination of **functional brain imaging data** and **sociodemographic, emotional, and parenting information**. This is significant since evidence suggests that ADHD can often go undiagnosed in girls, as they tend to exhibit more inattentive symptoms, which are harder to detect.

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

## Model Selection, Hyperparameter Tuning, and Training Approach

### Model Selection
We chose a neural network model due to its ability to capture complex patterns in the dataset, which is particularly useful for ADHD classification. Given the nature of the data, which likely includes nonlinear relationships, a neural network provides a more flexible approach compared to traditional machine learning models like logistic regression or decision trees.

### Hyperparameter Tuning
Hyperparameter tuning was conducted to optimize model performance while mitigating overfitting and underfitting. Key parameters adjusted included:

- Number of Layers: We experimented with different architectures to balance model complexity and generalization.

- Learning Rate: A lower learning rate helped stabilize training and prevent drastic weight updates.

- Batch Size: Smaller batch sizes were tested to improve generalization, though larger batches were considered for efficiency.

### Training Approach
The model was trained using backpropagation with an adaptive optimizer (e.g., Adam) to adjust learning rates dynamically. The dataset was split into training and validation sets to monitor performance and adjust hyperparameters accordingly.

### Justification for Choices
- Neural networks were chosen for their ability to model complex relationships in ADHD-related data.

- Hyperparameter tuning was necessary to optimize learning and prevent overfitting due to dataset imbalance.

- The training approach focused on generalization, incorporating techniques to ensure the model performs well beyond the training data.

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

---

## Results & Key Findings

From our analysis, the type of model best suited for this data set and the problem is the neural network model, achieving 70%+ accuracy. The neural network model predicted that 91.78% of the participants making up the test data set are female, and 99.34% have ADHD. Among those with ADHD, 91.72% are female. With a decently high accuracy, we believe that our model predicts both gender and ADHD diagnosis fairly well. 

## Impact Narrative

Identifying brain patterns associated with ADHD can enhance research and clinical care by improving diagnostic accuracy, enabling early detection, and guiding personalized treatment strategies- especially for underrepresented groups. Machine learning models can help uncover differences in brain activity, connectivity, and structure in individuals with ADHD, leading to objective biomarkers. These insights can be used to refine interventions such as medication adjustments and behavioral therapies, ultimately improving patient outcomes and advancing our understanding of ADHD as a neurodevelopmental disorder.

## Next Steps & Future Improvements

The primary limitation of our model is the uneven dataset used for both training and testing, which resulted in overfitting and underfitting. As a result, the model’s real-world accuracy may be lower than expected. A potential improvement would be to further refine the neural network using a larger, more balanced dataset to enhance prediction accuracy and reveal underlying patterns associated with the target variables.

## Acknowledgments  
- **WiDS Datathon** organizers and sponsors  
- **Healthy Brain Network (HBN)** and **Reproducible Brain Charts (RBC)** for providing the dataset
- **The Break Through Tech AI UCLA Team** (Shahani Waas, Nicole Feliciano, Sofia Lee) for support
- **Our tutor, Rebecca Aurelia Dsouza,** for mentorship
- **The National Break Through Tech AI Team** 
---
