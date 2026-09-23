# Duolingo Tracker
### Automated App Feature & User Satisfaction Intelligence Dashboard

Explore the Dashboard by [https://app.powerbi.com/links/rBx5uoXC8J?ctid=4517da72-c8f7-4cec-b2fc-fda9fe4354f9&pbi_source=linkShare]

## Problem Statement
App reviews hold a large amount of unstructured user feedback, but reading thousands of them manually makes it hard to spot recurring product issues. A product team needs to know which features users talk about most, which topics get the lowest ratings, and whether feedback shifted around a notable product update.

## Project Objective
Turn raw Google Play review text into structured, decision-ready product insights through an automated pipeline and an interactive Power BI dashboard.

## Key Achievements
* Analyzed **10,000 Google Play reviews** (Aug 19, 2024 – Apr 9, 2025) for Duolingo.
* Built an end-to-end pipeline: Python cleaning → sentiment + rule-based topic classification → SQL Server → Power BI.
* Designed a 4-table SQL Server model (`reviews`, `review_topics`, `versions`, `product_events`) with relationships and validation checks.
* Reduced classification false positives by moving from substring matching to regex word boundaries.
* Handled a sampling-pattern change around Jan 13, 2025 by analyzing time trends separately instead of assuming one consistent sample.
* Skills used: Python (Pandas, Regex, VADER), SQL Server, Power BI, DAX, data modeling, EDA, KPI design.

## Tech Stack
`Python` `Pandas` `VADER` `Regex` `SQL Server` `Power BI` `DAX`

## Pipeline
Raw Reviews → Python Cleaning → Sentiment + Topic Classification → CSV → SQL Server → Power BI Model → DAX Measures → Dashboard

## Project Overview
* 📊 **Executive Overview:** Total reviews, average rating, positive/negative %, weekly average rating, rating and sentiment distribution, most discussed topics.
* 🧩 **Feature Intelligence:** Topic mention volume, negative review share and average rating by topic, topic summary matrix.
* 🌙 **Update Impact:** Dark Mode case study comparing Before (Feb 26 – Mar 5), Event Window (Mar 6 – Mar 13) and After (Mar 14 – Mar 20, 2025), with daily mention trend and real review examples.
* 🎯 **Product Action Center:** Topic performance summary, volume vs. average rating, high negative-share topics, dynamic insight cards.

## Data Preparation
* **Sentiment:** Star rating is the primary label (1–2 Negative, 3 Neutral, 4–5 Positive). VADER sentiment is kept as a separate signal since it sometimes disagreed with ratings.
* **Topics:** Rule-based regex classification into Lessons, Pricing, Ads, Hearts/Lives, Practice, Streak, Bugs, Subscription, AI, Dark Mode, XP and Gems. A review can belong to multiple topics, so topic percentages are not mutually exclusive.

## Key Findings
* **10,000** reviews, **3.28** average rating, **51.2%** positive, **34.7%** negative.
* Most discussed topics: Lessons (2,495), Pricing (2,009), Ads (1,886), Hearts/Lives (1,820), Practice (1,482), Streak (1,002).
* Lowest average ratings by topic: Dark Mode (1.81), Subscription (2.21), Hearts/Lives (2.30), Pricing (2.32), XP (2.37), Bugs (2.38).
* Dark Mode mentions spiked around Mar 6–10, 2025, and average rating dipped from 3.52 (before) to 3.31 (event window).

> These are descriptive associations in the sample. The analysis does not establish that any feature or update caused a rating change.

## Challenges & Learnings
* **Unstructured text:** converted free-text reviews into structured topic and sentiment signals.
* **False positives:** short keywords like "ads" and "AI" matched inside unrelated words; fixed with word-boundary regex.
* **Unreliable text sentiment:** kept star-based sentiment as primary, NLP as secondary.
* **Sampling shift:** treated post-Jan 13, 2025 data separately for weekly trends.


## Data Source
Publicly available Google Play reviews for the Duolingo app.
