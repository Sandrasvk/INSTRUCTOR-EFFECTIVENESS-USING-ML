# Instructor Effectiveness Prediction

## Project Overview
I created this project to classify instructors into effectiveness tiers (High, Medium, Low) based on student engagement data. I used a dataset of 2,000 students to find patterns between student behavior and instructor performance.

## My Steps:

### 1. Data Visualization (EDA)
I used histograms and KDE plots to see the distribution of my data:
* *Completion Rate:* Most students finish 50-75% of the course.
* *Watch Time:* Very high, most students watch 100% of videos.
* *Forum Activity:* Very low, which means students aren't discussing much.
* *Score Improvement:* Follows a normal distribution (bell curve) centered around 25 points.

### 2. Grouping the Data (Aggregation)
Since instructors teach multiple batches, I had to aggregate the data to get one row per instructor:
* *Features:* I used .mean() for all numbers (quiz scores, watch time) to get a stable average.
* *Target:* I used .mode() for the effectiveness_tier to find the most frequent rank for each instructor.
* *Merging:* I merged these together on instructor_id to create the final training dataset.

### 3. Machine Learning Model
* *Model:* I used the RandomForestClassifier.
* *Preprocessing:* I dropped the instructor_id and the effectiveness_tier from my features (X) so the model doesn't see the answer.
* *Splitting:* I split the data into training and testing sets to verify accuracy.

### 4. Evaluation & Results
I used a *Confusion Matrix* to check my model's guesses:
* *Recall is Priority:* I prioritized Recall because it's better to "catch" every high-performing instructor (even if we get some false positives) than to miss a great instructor (false negative).
* *Class Imbalance:* I checked value_counts() and the classes (Low: 48, Medium: 38, High: 34) are balanced enough for Accuracy to be a good metric.

## Libraries
* pandas
* seaborn
* matplotlib
* sklearn
Platform : Jupyter Notebook
