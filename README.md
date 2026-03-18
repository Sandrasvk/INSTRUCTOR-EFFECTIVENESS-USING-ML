# Instructor Effectiveness Prediction

## 📌 Project Overview
I developed this project to classify instructors into tiers based on student performance data. The goal is to identify which instructors are most effective at driving student success.

## 🛠️ My 6-Step Workflow:

### 1. Exploratory Data Analysis (EDA)
I started by visualizing the data using KDE plots and Histograms. I checked the distribution of features like Completion Rate, Quiz Scores, and Forum Activity. I found that Score Improvement follows a normal distribution centered at 25 points.

### 2. Defining Instructor Effectiveness
In this step, I defined the target variable. I looked at how different metrics like student grades and engagement contribute to the final effectiveness_tier (Low, Medium, or High).

### 3. Data Aggregation
Since instructors teach many batches, I grouped the data by instructor_id:
* Numerical Features: I used .mean() to get the average performance across all batches.
* Target Variable: I used .mode() for the effectiveness_tier because I needed the most frequent classification.
* Merging: I merged these together to create a single dataset where each row is one instructor.

### 4. Machine Learning Model
I used a *Random Forest Classifier*. I dropped the ID and the target column from my Features (X) to make sure the model only learns from student behavior data.

### 5. Checking Class Imbalance
I ran y.value_counts() to see the distribution of tiers. I found that the classes (Low: 48, Medium: 38, High: 34) are relatively balanced, which means Accuracy is a reliable metric for this model.

### 6. Interpretation of Results
I used a *Confusion Matrix* to evaluate the model. I also used *Bar Plots* to visualize the results. 
* *Key Conclusion:* I prioritized *Recall*. It is better to correctly identify all high-performing instructors (even if it causes some false positives) than to miss a great instructor (false negative).

##  Libraries Used
* pandas
* seaborn
* matplotlib
* sklearn
  
## Platform used
Jupyter Notebook
