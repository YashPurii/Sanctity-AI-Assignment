# Sanctity-AI-Assignment

# **Predicting Student Success in Online Courses: A Data Science Case Study**

## **Table of Contents**
- [Introduction](#introduction)
- [Approach](#approach)
  - [1. Data Generation]( &#8203;:contentReference[oaicite:0]{index=0}&#8203;
  - [2. Data Preprocessing](#2-data-preprocessing)
  - [3. Model Building and Training](#3-model-building-and-training)
  - [4. Feature Importance](#4-feature-importance)
  - [5. Model Evaluation](#5-model-evaluation)
  - [6. Insights and Suggestions](#6-insights-and-suggestions)
- [Technologies Used](#technologies-used)
- [How to Run the Project](#how-to-run-the-project)
- [Results](#results)
- [Conclusion](#conclusion)

---

## **Introduction**

This project focuses on predicting whether a student will successfully complete an online course or drop out based on their demographic, engagement, and historical performance data. Early identification of students at risk of dropping out allows online platforms to offer support and improve overall student success rates.

The repository contains:
- **Python code** to implement a machine learning model that classifies students based on their likelihood to complete or drop out of a course.
- **A detailed report** explaining feature importance and recommendations for interventions to support at-risk students.
  
The report and code can be used by online learning platforms to improve student retention through data-driven insights.

---

## **Approach**

The process is divided into six key stages: data generation, preprocessing, model building, feature importance, model evaluation, and insights.

### **1. Data Generation**

Since real-world data is unavailable for this case study, synthetic data simulating the following categories was generated:
- **Student Profile Data**: Includes demographic information such as age, gender, major, academic year, and region.
- **Engagement Data**: Logs the number of weekly logins, videos watched, time spent on the platform, and quiz scores during the course.
- **Historical Data**: Tracks the number of courses started, completed, and average scores across all courses.

This synthetic data allows us to closely simulate a real-world scenario in an online education environment.

### **2. Data Preprocessing**

The next step involves cleaning and preparing the data for model training:
- **Label Encoding**: Categorical variables such as gender, major, and region were encoded as integers to be used in machine learning algorithms.
- **Feature Scaling**: Continuous variables (e.g., time spent on platform, logins) were standardized using **StandardScaler** to improve model performance.
- **Train-Test Split**: The data was split into training (80%) and testing (20%) sets to evaluate the performance of the models on unseen data.

### **3. Model Building and Training**

Several machine learning models were trained to predict whether a student would complete the course:
- **Random Forest Classifier**: The first model built was a Random Forest Classifier, known for its flexibility and high performance on classification tasks.
- **Hyperparameter Tuning**: The Random Forest was optimized using `GridSearchCV` to find the best combination of hyperparameters (e.g., number of trees, depth of trees, etc.).
- **XGBoost and LightGBM**: Additional ensemble models, **XGBoost** and **LightGBM**, were also trained and compared with the Random Forest model.
  
The best-performing model (tuned Random Forest) was selected based on accuracy, precision, recall, and F1 score.

### **4. Feature Importance**

To understand which factors drive student success, the **Random Forest feature importance** was analyzed:
- **Engagement Metrics**: Features like average quiz scores, time spent on the platform, and videos watched were key predictors of success.
- **Historical Data**: Past course performance (courses completed and started) played an important role in predicting future course completion.
- **Demographic Data**: Factors like gender, age, and region had less influence, indicating that engagement and performance metrics are more significant.

### **5. Model Evaluation**

The tuned Random Forest model achieved the following results:
- **Accuracy**: 70.50%
- **Precision**: 70.35%
- **Recall**: 100%
- **F1 Score**: 82.60%

The model is highly effective at identifying students who will complete the course (100% recall), but there is room for improvement in precision to reduce false positives.

### **6. Insights and Suggestions**

Based on the model and feature importance analysis, the following recommendations were made:
1. **Monitor Time Spent on Platform**: Time spent is highly predictive of success. Students with low engagement should be flagged early for intervention.
2. **Track Quiz Scores**: Low quiz scores should trigger additional support, such as tutoring or additional learning materials.
3. **Encourage Video Engagement**: Increasing video views is correlated with higher completion rates. The platform should provide reminders or personalized video content.
4. **Personalized Messages**: For students who start but do not complete many courses, personalized motivational messages can help re-engage them.

---

## **Technologies Used**
- **Python**
- **Pandas**: Data manipulation and analysis.
- **NumPy**: Numerical operations.
- **Scikit-learn**: Machine learning library for classification models, hyperparameter tuning, and evaluation.
- **Matplotlib**: Data visualization for feature importance.
- **XGBoost and LightGBM**: Ensemble learning methods for comparison.

---
