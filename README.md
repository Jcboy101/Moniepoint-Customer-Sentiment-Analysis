
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

![Screenshot 2025-06-11 150434](https://github.com/user-attachments/assets/bb1ccc66-f57b-4a4a-8d0a-524a52edeab1)

---

## 📊 Key Metrics and Visualizations

Each section includes insights along with the corresponding visualization.

### 1. Sentiment Distribution
- Shows the percentage of reviews that are Positive, Neutral, and Negative.
- **Insight:** Majority were positive, indicating strong general satisfaction.

![Screenshot 2025-06-11 133018](https://github.com/user-attachments/assets/47862139-c443-4a8b-9076-180a3ba48b95)


---

### 2. Sentiment Over Time
- Tracks how sentiment changed week by week.
- **Insight:** Dips in sentiment may correlate with app issues or downtime.

![Screenshot 2025-06-11 133054](https://github.com/user-attachments/assets/37ed8787-4286-4e5e-84fa-ca6cbb7a7fd5)


---

### 3. Frequent Negative and Positive Words
- Word cloud of most common terms in negative and positive reviews reviews.
- **Insight:** Common complaints related to failed transactions, delays, and poor customer support.
![Screenshot 2025-06-11 133121](https://github.com/user-attachments/assets/014b9855-5ac3-4954-a8de-ec96accf48a5)

![Screenshot 2025-06-11 133133](https://github.com/user-attachments/assets/aa3b72ae-c728-46fb-8ade-712dbb006477)

---

### 4. 🔍 Metric: Top Co-occurring Bigrams in Negative Reviews
To better understand recurring pain points in customer complaints, this metric focuses on identifying the most common bigrams (i.e., two-word combinations) that appear in reviews labeled as negative. Rather than analyzing single keywords, bigrams give clearer context about what exactly users are complaining about. For example, the phrase "login issue" is much more actionable than seeing just "login" or "issue" alone.

**🧠 Methodology:**
- Filtered the dataset to include only reviews tagged with a negative sentiment.
- Used CountVectorizer with an n-gram range of (2,2) to extract bigrams, while removing common stop words like "the" and "and".
- Counted the total occurrences of each bigram across all negative reviews.
- Selected the top 20 most frequent bigrams.
- Visualized the results in a horizontal bar chart using Seaborn.

![Screenshot 2025-06-11 133211](https://github.com/user-attachments/assets/cb9a8fb6-69df-479e-973c-e56664885579)

**📈 Key Insights:**
The most frequent bigrams often reflect highly specific and repeated issues users experience. Some examples might include:
- login issue" – Suggesting users face trouble accessing their accounts.
- network error" – Possibly pointing to server instability or app-side connectivity issues.
- account blocked" – Indicates a pattern of account restrictions that frustrate users.

These insights are incredibly valuable because they provide direct, actionable feedback. Product and support teams can use this information to investigate, prioritize, and resolve issues that consistently frustrate users.

---
##  5. Weekly Trend of Negative Reviews
Line chart showing how the number of negative reviews changes week by week.

Insight: This temporal analysis reveals spikes or drops in customer dissatisfaction over time. A consistent rise may indicate unresolved issues or recent app changes, while a decline could suggest effective interventions. Tracking these trends helps teams correlate negative sentiment with product updates, outages, or external events.

![Screenshot 2025-06-11 133228](https://github.com/user-attachments/assets/6c6ef6bd-92e2-4762-b5a0-5feb5b87b14d)

---
## 6. Keyword Mention Trends Over Time
Line plots tracking how often specific keywords (e.g., money, login, network, account, bad, update, slow) appear in reviews each week.

Insight: These trends highlight recurring user concerns. For instance, frequent spikes in login or network mentions may point to ongoing technical issues. Words like bad, slow, and update may reveal user frustration tied to specific app releases. Monitoring these patterns can guide targeted improvements in app performance and support.

![Screenshot 2025-06-11 133256](https://github.com/user-attachments/assets/875455b4-cc3d-4ed3-a24d-7fe0d773df73)


---
## 💡 Insights & Recommendations

- While most reviews are positive, negative ones show repeated issues with **transaction failures** and **poor response time** from support.
- Some users give high star ratings but express complaints, showing a mismatch between rating and satisfaction.
- Moniepoint can leverage this data to address common pain points and improve user experience.

---

## 📁 Project Structure

```
moniepoint-sentiment-analysis/
├── Moniepoint_woeking_file.ipynb      # Main analysis notebook
├── google_play_reviews.csv            # Collected review data
├── requirements.txt                   #packages
├──README.md                  # This file
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

