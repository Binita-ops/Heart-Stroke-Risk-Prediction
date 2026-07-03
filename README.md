The project encompasses a comprehensive data engineering and model development pipeline:

Data Preprocessing and Cleaning: The system handles data quality by identifying and remediating missing or placeholder values. Specifically, entries with zero values in critical health metrics—such as Cholesterol and RestingBP—are replaced with the mean values of the respective features to maintain data integrity.  

Feature Engineering: To accommodate categorical variables, the system applies one-hot encoding using pandas.get_dummies, effectively transforming non-numeric features like Sex, ChestPainType, and ST_Slope into structured boolean/integer indicators.  

Pipeline and Model Training: The dataset is partitioned into training and testing sets using a stratified split to ensure consistent distribution of the target variable. The system employs StandardScaler to normalize numerical input features, which is critical for algorithms sensitive to input scale.  

Comparative Algorithmic Analysis: The project evaluates the predictive performance of several machine learning classifiers, including:
Logistic Regression  
K-Nearest Neighbors (KNN)  
Gaussian Naive Bayes  
Decision Tree Classifier  
Support Vector Machine (SVM)  
Model Serialization: The most effective model (Logistic Regression) is serialized alongside its associated pre-processing scaler and feature column list using joblib, enabling efficient deployment and consistent inference on new, unseen data.
