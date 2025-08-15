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
- Removing Duplicates
- Normalize text (lowercase, remove emojies, punctuation, etc.).
- Extractiong Only English Text

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

1- **This [donut chart](https://github.com/KhaledNegm22/Reddit_Analysis/blob/main/most_popular_gpt.jpg)**, titled "Most Popular GPTs," illustrates the popularity of three different GPT models: ChatGPT, Gemini, and Grok, based on the number of mentions.

- ChatGPT is the most popular, accounting for 67.58% of the mentions. A tooltip shows this corresponds to 123 mentions.
- Gemini is the second most popular, represented by the blue segment.
- Grok is the least popular of the three, with 8.24% of the mentions, as shown in the black segment.

2- This **[horizontal bar chart](https://github.com/KhaledNegm22/Reddit_Analysis/blob/main/most_contributed_authors.jpg)**, titled "Most_contributing_authors," is a bar graph that shows the total contributions (posts and comments) for several authors.

- The most prolific contributors are currentscurrents, DigThatData, and Seankala.

3- This **[stacked bar chart](https://github.com/KhaledNegm22/Reddit_Analysis/blob/main/monthly_mentions_of_ml_subreddit_topics.jpg)**, titled "Monthly Mentions of ML Subreddit Topics," tracks the total number of mentions for three topics—DL (Deep Learning), GenAI (Generative AI), and ML (Machine Learning)—on an ML-related subreddit over time.

- The x-axis represents time, with specific months and years dating from 2012 to late 2024.
- The y-axis shows the "Total Mentions."

Each stacked bar represents the total mentions for a given month, broken down by topic.

**Key Observations**:

- Exponential Growth: There is a significant and accelerating increase in total mentions over the years, particularly from late 2022 onwards.
- Dominance of ML: Machine Learning (ML), represented by the green segment, consistently makes up the largest portion of the total mentions.
- Rise of GenAI: Mentions of Generative AI (GenAI), shown in yellow, begin to rise sharply in late 2023 and early 2024, contributing to the overall surge in discussion.
- DL's Steady Contribution: Deep Learning (DL), represented by the blue segment, also shows a steady increase in mentions, but its growth appears less dramatic compared to GenAI in the most recent periods.

### After running the pipeline, you will get:

- Cleaned & structured Reddit data in Bronze, Silver, and Gold layers.
- Three analytical Gold tables ready for visualization.
- Exported charts in JPEG format.
- Databricks dashboards for interactive exploration.
  
## 💡 Future Improvements

 ### Add sentiment analysis on posts/comments to answer more complex business questions.


 
