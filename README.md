
# Moniepoint Customer Sentiment Analysis

This project was born out of a personal interest in the financial sector, specifically in understanding user perception of financial service providers. I focused on Moniepoint, a prominent fintech platform, and analyzed user reviews from its Google Play Store page using sentiment analysis techniques.

## 📌 Objective

To analyze customer reviews of the Moniepoint Business app to understand sentiment trends, highlight pain points, and evaluate customer satisfaction over time using NLP-based sentiment analysis.

---

## 🧾 Project Workflow

### 1. Data Collection
- **Tool Used:** `google_play_scraper`
- **Source:** Google Play Store (`com.moniepoint.business`)
- **Volume:** 5,000 most recent reviews
- **Features Extracted:** Username, Rating, Review Text, Date

### 2. Preprocessing
- Reviews were cleaned and transformed into a structured format.
- Renamed columns for clarity (e.g., `score` to `rating`, `at` to `date`).
- Data saved and reloaded from a CSV for easier handling.

### 3. Sentiment Analysis
- **Model:** `nlptown/bert-base-multilingual-uncased-sentiment`
- **Sentiment Score Range:** 1 (Very Negative) to 5 (Very Positive)
- **Label Mapping:**
  - 1–2 → Negative
  - 3 → Neutral
  - 4–5 → Positive

### 4. Labeling
- Added `sentiment score` and `sentiment` (category) columns to the dataset.

---

## 📊 Key Metrics and Visualizations

Each section includes insights along with the corresponding visualization.

### 1. Sentiment Distribution
- Shows the percentage of reviews that are Positive, Neutral, and Negative.
- **Insight:** Majority were positive, indicating strong general satisfaction.

![Sentiment Distribution](sentiment_distribution.png)

---

### 2. Rating vs Predicted Sentiment Score
- Compares actual user ratings with model-inferred sentiment.
- **Insight:** Some high-rated reviews still contained complaints.

![Rating vs Sentiment](rating_vs_sentiment.png)

---

### 3. Sentiment Over Time
- Tracks how sentiment changed week by week.
- **Insight:** Dips in sentiment may correlate with app issues or downtime.

![Sentiment Over Time](sentiment_over_time.png)

---

### 4. Frequent Negative Words
- Word cloud of most common terms in negative reviews.
- **Insight:** Common complaints related to failed transactions, delays, and poor customer support.

![Negative Word Cloud](negative_words_cloud.png)

---

### 5. Sample Reviews (Positive & Negative)
- **Positive Example:** "Very reliable app, fast settlements!"
- **Negative Example:** "Transfer failed but my account was debited. No response from support."

---

## 💡 Insights & Recommendations

- While most reviews are positive, negative ones show repeated issues with **transaction failures** and **poor response time** from support.
- Some users give high star ratings but express complaints, showing a mismatch between rating and satisfaction.
- Moniepoint can leverage this data to address common pain points and improve user experience.

---

## 📁 Project Structure

```
moniepoint-sentiment-analysis/
│
├── webscrape.ipynb            # Main analysis notebook
├── reviews.csv                # Collected review data
├── sentiment_distribution.png
├── rating_vs_sentiment.png
├── sentiment_over_time.png
├── negative_words_cloud.png
└── README.md                  # This file
```

---

## 🛠️ Tools Used

- Python
- pandas
- transformers (HuggingFace)
- matplotlib / seaborn / wordcloud
- google_play_scraper

---

## 📬 Contact

Feel free to reach out if you'd like to collaborate or have feedback on this project!

**Author:** Jude Chukwumba  
**LinkedIn:** [Jude on LinkedIn](https://www.linkedin.com)

