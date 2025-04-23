# ☄️ Distributed Data Analysis & Mining of NASA Asteroid Dataset

## Risk Classification | Scalable Clustering | Big Data with Apache Spark
#### A Final-Year Project in Distributed Data Analytics & Mining (DDAM)

## 📌 Overview
This project leverages distributed computing and data mining techniques to analyze and classify asteroids from NASA's Jet Propulsion Laboratory (JPL) dataset. With over 950,000+ records and 45+ features, the objective was to identify potentially hazardous asteroids (PHAs), classify orbital patterns, and uncover hidden insights in high-dimensional astronomical data using Apache Spark.

## 🎯 Objectives
Predict and classify asteroids that pose a threat to Earth (PHA classification)

Apply clustering techniques to uncover new groupings beyond orbital classes

Handle extreme data imbalance with sampling strategies

Enable scalable big data processing using distributed computing

Perform risk analysis using machine learning models and interpret results

## 📁 Dataset
Source: NASA JPL Small-Body Database

Records: 958,524 asteroids

Attributes: 45 features (orbital parameters, diameters, velocities, etc.)

Final Optimized Dataset: 938,597 rows and 17 selected features after cleaning

## ⚙️ Tools & Technologies
Language: Python

Framework: Apache Spark (PySpark)

Libraries: pyspark.ml, scikit-learn, matplotlib, seaborn

Techniques: Feature Engineering, Clustering, Classification, Undersampling, Data Visualization

Platform: Jupyter Notebooks / VS Code

## 🔧 Workflow & Methodology
1. Data Preprocessing & Feature Engineering
Merged multi-source data into Spark DataFrames

Handled missing values using regression and statistical imputation

Reduced dimensions by selecting top 17 features using correlation analysis

Normalized and vectorized data for distributed ML processing

2. Classification of Hazardous Asteroids
Algorithms: Random Forest, Logistic Regression, SVM, Gradient Boosting

Addressed class imbalance using undersampling technique

Achieved 100% recall for PHA class by prioritizing true positive detection

Balanced high recall with acceptable precision for optimal risk signaling

3. Clustering for Orbital Grouping
Applied K-Means with optimal K=6 (based on Elbow and Silhouette Score)

Clustered based on physical and orbital features like eccentricity, magnitude, velocity

Revealed non-traditional asteroid groupings that differed from NASA’s orbital class labels

Spark’s distributed clustering scaled efficiently over hundreds of thousands of records

4. Visualization & Analysis
Visualized clusters in 2D (PCA) and 3D space

Generated heatmaps for feature correlation

Risk distribution and prediction confidence analyzed with bar/line charts

## 📈 Results & Highlights

Task	Technique Used	Highlight
PHA Classification	Random Forest	100% Recall, ~90% Precision
Clustering (K=6)	K-Means	Novel asteroid groupings discovered
Imbalance Handling	Undersampling	Enabled fair learning from minority class
Scalability	Apache Spark	Efficient on 950K+ records
## 🔍 Key Insights
Majority of PHA-labeled asteroids were missed in baseline models without imbalance handling

Clustering analysis suggested alternate asteroid groupings based on physical features

Spark provided necessary scalability and speed, enabling real-time processing simulations

High precision + recall models aid in early detection and risk forecasting of near-Earth objects

## 🧠 Learnings & Contributions
Hands-on experience with big data frameworks and real-world datasets

Tackled imbalanced classification challenges in a high-stakes scientific dataset

Developed end-to-end pipeline: from data ingestion to distributed model deployment

Contributed methodological insights for scalable asteroid risk analysis

## 👥 Authors
Amir Hassan


## 📫 Contact
## 📧 amirhassanunipi29@gmail.com
🔗 Let’s collaborate on https://www.linkedin.com/in/amirhassan786/
