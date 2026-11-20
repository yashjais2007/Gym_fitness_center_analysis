# 🏋️‍♂️ Project 12: Gym & Fitness Center Membership Analytics

## 📌 Overview
This project evaluates member check-in logs, group fitness class attendance, workout duration patterns, and membership tier performance for a health and wellness center. The analysis uses **Python**, **Pandas**, and **NumPy** to uncover peak facility hours, high-demand fitness classes, revenue distribution, and low-engagement members to drive data-backed facility scheduling and retention strategies.

---

## 📂 Dataset Description
* **File:** `12_gym_membership.csv`
* **Columns:**
  * `Checkin_ID`: Unique identifier for each gym visit
  * `Member_ID`: Unique identifier for each gym member
  * `Membership_Tier`: Member plan level (`Basic`, `Gold`, `Platinum`)
  * `Gender`: Member gender (`Male`, `Female`, `Other`)
  * `Checkin_Time`: Timestamp of facility entry (`YYYY-MM-DD HH:MM:SS`)
  * `Workout_Duration_Mins`: Length of the workout session in minutes
  * `Fitness_Class`: Group class attended (`Spin`, `Strength`, `HIIT`, `Zumba`, `Yoga`, or `None` for solo workouts)
  * `Monthly_Fee`: Monthly subscription fee paid by the member

---

## 🛠️ Technologies Used
* **Python 3.x**
* **Pandas** (Data cleaning, datetime feature extraction, grouping, and aggregation)
* **NumPy** (Statistical calculations, percentiles, and conditional labeling)

---

## 📋 Project Tasks Completed
1. **Data Loading & Inspection:** Loaded `12_gym_membership.csv` while preserving `"None"` class strings and inspected schema, dimensions, and sample records.
2. **Data Quality & Deduplication:** Identified missing values and removed duplicate `Checkin_ID` entries.
3. **Missing Value Imputation:** Imputed missing `Workout_Duration_Mins` values using **median imputation** to prevent skew from extreme workout durations.
4. **Datetime Feature Engineering:** Converted `Checkin_Time` to datetime objects and extracted `Weekday` and `Hour` of visit.
5. **Core Engagement Metrics:** Calculated total valid check-ins and overall average workout duration.
6. **Membership Tier Analysis:** Compared total visits, unique active members, average workout duration, and visits per member across `Basic`, `Gold`, and `Platinum` tiers.
7. **Peak Traffic Identification:** Ranked check-ins by hour of day and day of week to identify peak gym hours and busiest days.
8. **Fitness Class Popularity Ranking:** Filtered out solo sessions (`None`) and ranked group fitness classes by total attendance.
9. **Gender Duration Comparison:** Compared average and median workout durations between `Male` and `Female` members.
10. **Monthly Revenue by Tier:** Deduplicated member-tier records to calculate accurate monthly recurring revenue across tiers.
11. **Low-Engagement Detection:** Flagged members logging fewer than 2 visits per calendar month for retention outreach.
12. **NumPy Statistical Profiling:** Computed median, sample variance (`ddof=1`), and quartiles (`Q1`, `Q2`, `Q3`) of workout durations using NumPy.
13. **IQR Outlier Detection:** Used the Interquartile Range (`Q3 - Q1`) method to identify unusually short or unusually long workout sessions.
14. **Workout-Intensity Classification:** Categorized sessions into `Short` (`< 45 mins`), `Moderate` (`45–90 mins`), and `Extended` (`> 90 mins`) using `np.select()`.
15. **Actionable Recommendations:** Generated five data-driven facility management and member retention recommendations.

---

## 📊 Expected Deliverables
* Peak-hour and busiest-day schedule summary
* Group fitness class popularity ranking table
* Membership tier visit and monthly revenue comparison
* Low-engagement member count and list (`< 2 visits/month`)
* Five actionable facility management and retention recommendations

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com
   cd gym-membership-analytics
   ```
2. Install required dependencies:
   ```bash
   pip install pandas numpy
   ```
3. Place `12_gym_membership.csv` in the project root directory and run the script or Jupyter Notebook:
   ```bash
   jupyter notebook project_12.ipynb
   ```
