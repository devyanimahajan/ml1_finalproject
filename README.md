## 👥 Predicting Employee Attrition using Machine Learning

Final project for **Machine Learning I (ADSP 31017)**  
* University of Chicago | Master's in Applied Data Science
* March 2025  

---

### 🌟 Overview

This project aims to address the business challenge of **employee attrition** at IBM by leveraging supervised and unsupervised machine learning techniques. Using an HR dataset, we identify employee profiles most at risk of leaving and propose tailored retention strategies based on our findings.

---

### 🌟 Dataset

- **Source**: IBM HR Analytics Employee Attrition Dataset  
- **Size**: 1,470 records × 34 predictors + 1 target column (`Attrition`)  
- **Preprocessing**:
  - Removal of constant/ID columns (e.g. `EmployeeNumber`)
  - Correlation-based feature pruning
  - Standard and Min-Max scaling
  - One-hot encoding for categorical variables

---

### 🌟 Methodology

#### ✨ Exploratory Data Analysis (EDA)

- Attrition is more likely among:
  - Employees in **Technical** and **Sales** roles
  - **Single** individuals
  - Those with **lower income** and **younger age**

#### ✨ Clustering

- **Technique**: K-Prototypes (optimal `k=3`)
- **Clusters Identified**:
  1. **Early-Career Researchers**
  2. **Mid-Career Technicians**
  3. **Senior Sales Executives**

Each cluster was profiled by demographics, compensation, experience, and satisfaction to guide targeted retention strategies.

#### ✨ Classification Models

- **Target**: Binary prediction of attrition
- **Imbalance Handling**: SMOTE (oversampling minority class from 16% to 50%)
- **Models Used**:
  - Logistic Regression (with forward selection and regularization tuning)
  - Random Forest Classifier
  - Gradient Boosting Machine (GBM)

#### ✨ Cluster-wise Regression

- Iteratively applied logistic regression within clusters to capture nuanced patterns
- Best recall performance among all models (70.2%) with slightly lower accuracy (75.2%)

---

### 🌟 Results

| Model Type              | Avg Accuracy | Avg Recall |
|-------------------------|--------------|------------|
| Logistic Regression     | 84.4%        | 36.7%      |
| Random Forest           | 89.9%        | 63.5%      |
| Gradient Boosting       | 88.7%        | 62.1%      |
| **Cluster-wise Regression** | 75.2%    | **70.2%**  |

- Tree-based models had the best overall accuracy
- Cluster-wise regression showed the best recall, highlighting effectiveness in capturing minority class

---

### 🌟 Key Takeaways

- Clustering uncovered meaningful employee subgroups linked to attrition
- Combining clustering with classification improved predictive performance
- Recommendations were tailored to cluster-specific employee profiles:
  - 🌱 **Young Innovators**: Promote engagement and innovation
  - 📈 **Mid-Career Sales**: Offer advancement and reduce burnout
  - 👨‍🏫 **Experienced Contributors**: Leverage expertise through mentoring and leadership

---

### 🌟 Repository Structure
- `Final Project Submission/`: EDA, clustering, and classification model development
- `test_data/`: Testing data, preprocessed from IBM HR attrition dataset
- `train_data/`: Training data, preprocessed from IBM HR attrition dataset
- `ML Final Project Presentation.pdf`: Final summary presentation
- `README.md`: Project overview and documentation
