# 📊 Social Media Data Analytics Pipeline (Reddit)

## 📌 Overview
This project processes and analyzes social media data (posts & comments) Using **Reddit API  (PRAW)** **Subreddit: r/Machine Learning** to:

- Identify **top contributing authors**.
- Detect **trending topics** based on keywords.
- Track **category trends over time**.
- Organize the data into **Bronze → Silver → Gold** layers using **PySpark** and **Delta Lake**.

---

## 🛠️ Tech Stack

- **Databricks** → Unified analytics platform for running PySpark jobs, managing Delta Lake tables and creating Visualizations.
- - **PRAW** – Reddit API client
- **PySpark** → Distributed data processing.
- **Delta Lake** → Versioned data storage with ACID transactions.
- **SQL** → Aggregations & analytics.
- **GitHub** → Version control.


---

## 🔄 Data Pipeline

### Bronze Layer – Data Ingestion

- Load **raw posts** and **comments**
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


-----------------------------------------------------------
🚀 How to Run
### 1️⃣ Create a Reddit API Account

Go to Reddit App Preferences.
Click Create another app... and choose Script, Fill in the required fields.

Copy the following to use it in the Ingestion & Profiling Notebook.
client_id, client_secret, user_agent

### 2️⃣ Run the Ingestion & Profiling Notebook (Bronze & Silver Layer):

This will:
- Ingest Reddit data via PRAW API.
- Perform profiling & cleaning.
- Store data in Bronze Layer and partially in Silver Layer.

### 3️⃣ Complete the Silver Layer & Create the Gold Layer by running reddit_medallion notebook:
This will:
- Continue processing Silver Layer data.
- Create Gold Layer tables: Most Contributing Authors, Most Trending Topics, Most Mentioned Gpt
- Prepare data for visualization.

### 4️⃣ Visualization:
- Output charts are saved as .jpeg files in the repo.

### After running the pipeline, you will get:

- Cleaned & structured Reddit data in Bronze, Silver, and Gold layers.
- Three analytical Gold tables ready for visualization.
- Exported charts in JPEG format.
- Databricks dashboards for interactive exploration.
  
## 💡 Future Improvements

 ### Add sentiment analysis on posts/comments to answer more complex business questions.


 
