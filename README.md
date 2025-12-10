# Marketing Attribution Analysis with PySpark

# 🎬 Marketing Attribution Analysis with PySpark

## Project Overview

This project addresses a Data Science challenge focused on quantifying the real-world impact of email marketing campaigns on customer purchasing behavior (movie ticket sales).

The solution was built for **scalability and performance** using **Apache PySpark** as the core engine for processing large, disparate datasets (transactions, emails, customer profiles, and movie releases).

## Key Technologies

* **Big Data Engine:** PySpark (Spark SQL, Spark MLlib)
* **Language:** Python 3.x
* **Libraries:** Pandas, Matplotlib, Seaborn

## Technical Highlights (PySpark Focus)

The use of PySpark was mandatory to handle the demanding feature engineering required to create a robust model training set.

1.  **Massive Feature Engineering Pipeline:**
    * **Customer-Day Grid:** A foundational **`crossJoin`** was implemented in Spark SQL to create a massive analytical table (one row per Customer per Day), allowing for daily behavioral modeling.
    * **Window Functions:** Complex feature extraction was performed using **`pyspark.sql.window.Window`** to calculate time-series metrics efficiently, such as:
        * Rolling count of emails received in the last 3 days.
        * Customer's cumulative spend in the last 30 days.

2.  **Distributed Machine Learning (Spark MLlib):**
    * Predictive models were trained using Spark's distributed ML framework (`pyspark.ml`):
        * **Classification:** `LogisticRegression` to predict the daily **Purchase Likelihood**.
        * **Regression:** `LinearRegression` to estimate the **Purchase Amount**.

3.  **Optimization:** The data pipeline was designed to leverage Spark's distributed processing and efficient DataFrame operations, minimizing the use of less performant Python UDFs.

## 📊 Business Outcomes and Conclusions

The analysis provided strategic insights by isolating the impact of marketing efforts from organic customer behavior:

* **Minimal Direct Impact:** The study showed that while emails maintain customer engagement, they have a **minimal direct lift** on immediate ticket purchases.
* **Key Drivers:** **Customer loyalty/recency** and the **Movie Release schedule** are 10x more influential on sales than email frequency or timing.
* **Recommendation:** Marketing efforts should shift from broad email pushes to a strategy focused on **high-value customer segmentation** and **strong alignment with weekend and new movie releases**, utilizing emails as a supportive, loyalty-building tool.

## 🚀 Setup and Execution

### Prerequisites

You must have, **Apache Spark**, and **PySpark** installed and configured in your environment (or use a cloud-based service like Databricks, AWS EMR, or a Colab/Jupyter environment configured for Spark).

### Dependencies

Install the required Python libraries using the `requirements.txt` file:

```bash
pip install -r requirements.txt
