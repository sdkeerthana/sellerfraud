# Seller Fraud Detection 🔍

A PySpark-based machine learning project for detecting **fraudulent/spam seller reviews** on Amazon using the Electronics product review dataset.

## 📌 Overview

This project analyzes Amazon product reviews to classify them as **spam (fraudulent)** or **non-spam (genuine)** using distributed data processing with Apache Spark.

## 📂 Dataset

- **Source**: Amazon Product Review Spam and Non-Spam Dataset (Kaggle)
- **Category**: Electronics
- **Format**: JSON

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.7 | Core language |
| Apache Spark (PySpark) 3.4.4 | Distributed data processing |
| Kaggle | Dataset & notebook environment |

## 📓 Notebook

The main analysis is in [`seller-fraud.ipynb`](./seller-fraud.ipynb).

### Key Steps

1. **Data Loading** — Load Amazon Electronics JSON reviews via Spark
2. **Data Cleaning** — Extract & clean the `_id` field, drop unused columns, rename columns
3. **Feature Engineering**:
   - `helpfulTotalRatio` — ratio of helpful upvotes to total votes (%)
   - `reviewUpvotes` — raw upvote count
   - `reviewLength` — character length of review text
   - `summaryLength` — character length of review summary
   - `isWeekend` — whether the review was posted on a weekend
4. **Text Preprocessing** — Lowercasing and punctuation removal from `reviewText` and `summary`
5. **Classification** — Binary classification (`class`: 0 = spam, 1 = genuine)

## 🚀 Getting Started

### Prerequisites

```bash
pip install pyspark
```

### Running the Notebook

1. Open `seller-fraud.ipynb` in Jupyter or Kaggle
2. Update the dataset path to your local path:
   ```python
   df = spark.read.json("/path/to/Electronics.json")
   ```
3. Run all cells sequentially

## 📊 Features Used

| Feature | Description |
|---------|-------------|
| `reviewText` | Full text of the review (cleaned) |
| `summary` | Short summary of the review (cleaned) |
| `productRating` | Star rating (1–5) |
| `helpfulTotalRatio` | % of users who found the review helpful |
| `reviewUpvotes` | Number of helpful upvotes |
| `reviewLength` | Length of review text |
| `summaryLength` | Length of review summary |
| `isWeekend` | Whether review was posted on weekend |

## 📄 License

This project is for educational and research purposes.
