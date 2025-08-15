# 📊 Social Media Data Analytics Pipeline

## 📌 Overview
This project processes and analyzes social media data (posts & comments) to:
- Identify **top contributing authors**.
- Detect **trending topics** based on keywords.
- Track **category trends over time**.
- Organize the data into **Bronze → Silver → Gold** layers using **PySpark** and **Delta Lake**.

---

## 🛠️ Tech Stack

- **Databricks** → Unified analytics platform for running PySpark jobs, managing Delta Lake tables and creating Visualizations.
- **PySpark** → Distributed data processing.
- **Delta Lake** → Versioned data storage with ACID transactions.
- **SQL** → Aggregations & analytics.
- **GitHub** → Version control.


---

## 🔄 Data Pipeline

### Bronze Layer – Data Ingestion

- Load **raw posts** and **comments** from Reddit API (PRAW).
- Save them as **Delta tables** (`posts_bronze`, `comments_bronze`).

---

### Silver Layer – Data Cleaning & Transformation

- Remove unwanted patterns.

- Normalize text (lowercase, remove emojies, punctuation, etc.).

### Analytics (Gold Layer)

- Most Contributing Authors: Union posts & comments count per author.

- Trending Topics: Keyword mapping to categories (ML, DL, GenAI).

- Monthly Trends: Count mentions by month & category.

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## 📊 Example Outputs


Most Contributing Authors

| Author  | Total Posts | Total Comments | Total Activity |
| ------- | ----------- | -------------- | -------------- |
| user123 | 45          | 60             | 105            |


Trending Topics Over Time

| Month   | Category | Mentions |
| ------- | -------- | -------- |
| 2024-01 | ML       | 120      |
| 2024-01 | DL       | 80       |
 
**NOTE**: You can find the Visualization as jpeg file in the repo.

-----------------------------------------------------------


## 💡 Future Improvements

 ### Add sentiment analysis on posts/comments.


 
