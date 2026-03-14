# Instructor Effectiveness Modeling (EdTech)

## Overview

This project analyzes instructor performance on an EdTech platform using learner outcome, engagement, and feedback data. The objective is to define **Instructor Effectiveness**, aggregate batch-level data to instructor-level insights, and build a machine learning model to classify instructors into effectiveness tiers.

The focus of this analysis is not only predictive performance but also **interpreting which factors influence instructor effectiveness**.

---

## Problem Statement

EdTech platforms often run the same course across multiple batches taught by different instructors. Each instructor may teach multiple batches and courses over time.

The goal of this project is to:

* Analyze learner outcomes, engagement, and feedback metrics
* Define an **Instructor Effectiveness Score**
* Aggregate batch-level data to instructor-level metrics
* Train a machine learning model to classify instructors into effectiveness tiers
* Interpret which factors influence instructor effectiveness

---

## Dataset Description

Each row in the dataset represents a **course batch** taught by an instructor.

### Identifier Columns

* `batch_id` – Unique ID for a course batch
* `instructor_id` – Unique instructor identifier
* `course_id` – Course identifier

### Learner Outcome Metrics

* `completion_rate` – Fraction of learners who completed the course
* `dropout_rate` – Fraction of learners who dropped out
* `avg_score_improvement` – Average improvement between pre- and post-assessment
* `avg_quiz_score` – Average quiz score for the batch

### Engagement Metrics

* `avg_watch_time` – Normalized average video watch time
* `assignment_submission_rate` – Fraction of learners submitting assignments
* `forum_activity_rate` – Fraction of learners active in discussions

### Feedback Metrics

* `avg_feedback_score` – Average learner feedback rating
* `feedback_response_rate` – Fraction of learners submitting feedback

---

## Methodology

### 1. Exploratory Data Analysis (EDA)

Initial analysis was performed to:

* Understand feature distributions
* Identify correlations between variables
* Detect anomalies or missing values

Visualization tools such as **histograms and correlation heatmaps** were used.

---

### 2. Defining Instructor Effectiveness

An **Instructor Effectiveness Score** was defined using a weighted combination of learner outcomes, engagement, and feedback metrics.

Key signals considered:

* Course completion
* Learning improvement
* Student engagement
* Learner feedback

The score was then converted into **three effectiveness tiers**:

* Low
* Medium
* High

---

### 3. Aggregation to Instructor Level

Since instructors may teach multiple batches, batch-level metrics were aggregated using the **mean** for each instructor.

This provides a stable estimate of an instructor's overall performance across different course batches.

---

### 4. Machine Learning Model

A **Random Forest Classifier** was used to predict instructor effectiveness tiers.

Reasons for choosing Random Forest:

* Works well with structured tabular data
* Captures non-linear relationships
* Robust to noise and overfitting
* Provides feature importance for interpretability

---

### 5. Model Evaluation

Model performance was evaluated using:

* **Accuracy**
* **Precision**
* **Recall**
* **Confusion Matrix**

These metrics help understand how well the model predicts instructor effectiveness tiers.

---

### 6. Key Findings

Feature importance analysis revealed that the most influential factors were:

* Average quiz score
* Dropout rate
* Completion rate
* Score improvement

These variables reflect **learning outcomes and student retention**, which are strong indicators of teaching effectiveness.

Engagement and feedback metrics also contributed but to a lesser extent.

---

## Limitations

This model has several limitations:

* Course difficulty may influence completion and dropout rates
* Feedback scores may contain student bias
* Differences in student background are not captured
* Teaching style and instructional quality cannot be fully measured using numerical metrics

---

## Future Improvements

Additional data could improve this analysis, such as:

* Instructor experience and qualifications
* Course difficulty level
* Student demographics
* Instructor responsiveness to student questions
* Class size

Including these factors would allow for a more comprehensive evaluation.

---

## Technologies Used

* Python
* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
* Jupyter Notebook / Google Colab

---

## Conclusion

This project demonstrates how machine learning can be used to estimate instructor effectiveness using learner outcome, engagement, and feedback metrics. While the model provides useful insights, it should be used as a **decision-support tool rather than a definitive measure of instructor performance**.

The analysis highlights the importance of **student learning outcomes and engagement metrics** in evaluating teaching effectiveness within EdTech platforms.
