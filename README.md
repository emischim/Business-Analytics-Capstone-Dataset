
---

## 🧾 Project Overview

Modern software development often suffers from **vague or ambiguous requirements**. This project explores issue tracking data from **Facebook**, **Stripe**, and **PayPal** GitHub repositories to:
- Detect patterns in requirement reporting
- Engineer features such as readability and clarity scores
- Prepare data for potential classification of “clear” vs. “unclear” issues

---

## 📌 Data Sources

Data was collected from the following GitHub repositories using the GraphQL API:
- `facebook/react`
- `stripe/stripe-python`
- `paypal/PayPal-PHP-SDK`

Only issues posted **on or before June 16, 2025** were included to maintain data consistency across runs.

---

## 🧼 Data Cleaning & Preprocessing

- Removed irrelevant columns (e.g., `id`)
- Dropped missing or empty issue bodies
- Removed duplicate entries based on `title` + `body`
- Filtered out placeholder text (e.g., “test”, “dummy”)
- Normalized body text (lowercase, stripped whitespaces)

---

## 🏗️ Feature Engineering

The following features were engineered:
- `word_count` – Total words in the issue body
- `readability_score` – Calculated using textstat’s Flesch Reading Ease
- `vague_score` – Presence of vague terms like “some,” “might,” “various”
- `clarity_score` – Composite metric based on readability, length, and vagueness
- `comment_bucket` – Grouped issues by number of comments (0, 1–2, 3–5, 6+)

---

## 📈 Exploratory Data Analysis (EDA)

Key visualizations include:
- Source distribution pie chart
- Issue count by state
- Word count and comment distributions
- Clarity scores and outlier detection
- Word clouds and vague term frequency

---

## 📌 Next Steps (for final project)

- Label data into “clear” and “unclear”
- Apply NLP classification models (e.g., Logistic Regression, SVM)
- Use clarity insights to support automated requirement quality checks

---

## 🧑‍💻 Author

**Emmanuel Isa**  
Graduate Certificate in Big Data Analytics  
Nexford University

---

## 📬 Contact

For questions or suggestions, please feel free to open an issue or reach out via [LinkedIn](https://www.linkedin.com).
