# Machine-Failure-Prediction---Python
Predictive Maintenance ML: An analysis of machine failure prediction using multiple classifiers (Logistic Regression, Random Forest, SVM) with resampling techniques to address class imbalance. Identifies key features affecting equipment failure and compares model performance through ROC curves and F1 scores.

# Executive Summary: Predictive Maintenance Model for Manufacturing Equipment
## Business Context
Manufacturing equipment failures significantly impact operational efficiency through costly downtime and unplanned maintenance. Our predictive modeling framework addresses this challenge by identifying potential failures before they occur, enabling proactive maintenance scheduling that reduces downtime costs and extends equipment lifespan.
## Project Overview
This analysis developed machine learning models to predict equipment failures using sensor data from manufacturing operations. The dataset contained operational parameters including temperature readings, rotational speed, torque measurements, and tool wear times. We implemented and compared multiple modeling approaches to find the optimal predictive solution for identifying equipment failures in an environment with highly imbalanced data (where normal operations vastly outnumber failure events).
## Methodology
Our analytical approach followed a structured data science workflow:

### 1. Data Preprocessing

Cleaned the dataset by handling missing values and removing duplicate records
Transformed variables, including temperature conversion from Kelvin to Celsius
Created new engineered features like temperature difference to enhance predictive power
Removed irrelevant variables to ensure model focus on meaningful predictors


### 2. Exploratory Analysis

Identified significant class imbalance (9,652 normal operations vs. only 348 failure events)
Analyzed feature distributions and correlations to understand data patterns
Discovered critical relationships between operational parameters and failure events
Identified strong negative correlation between torque and rotational speed


### 3. Model Development

Addressed class imbalance through resampling techniques (SMOTE and SMOTEENN)
Developed and evaluated three classification algorithms:

Logistic Regression with different resampling approaches
Random Forest classification
Support Vector Machines with different resampling approaches


Optimized models through hyperparameter tuning and feature selection



## Key Findings

### 1. Performance Comparison

SVM with SMOTE achieved the highest recall (0.91), capturing most potential failure events
Random Forest delivered the best overall predictive balance with the highest F1-score (0.80)
Logistic Regression had high recall (0.89) but the lowest precision, resulting in excessive false alarms


### 2. Feature Importance

Random Forest identified the most critical operational parameters for failure prediction:

Torque (29.8% importance)
Rotational speed (25.8% importance)
Temperature difference (14.8% importance)


These findings provide maintenance engineers with specific operational metrics to monitor


### 3. Model Selection Tradeoffs

SVM model prioritizes minimizing missed failures but generates more false positives
Random Forest provides better balance between detecting failures and minimizing false alarms
Resampling techniques significantly improved model sensitivity to rare failure events



## Business Implications
This analysis provides a foundation for implementing predictive maintenance strategies in manufacturing environments. The optimal model selection depends on specific business priorities:

**SVM with SMOTE** is recommended when failure detection is paramount and false alarms are acceptable (higher safety requirements)
**Random Forest** offers the best overall performance for environments where false alarms have significant operational costs
**All models** demonstrate that monitoring torque, rotational speed, and temperature difference provides the strongest indicators of potential equipment failure

By implementing these predictive models, maintenance teams can transition from reactive to proactive maintenance approaches, potentially reducing downtime by up to 30%, extending equipment life, optimizing maintenance scheduling, and significantly reducing overall maintenance costs.
