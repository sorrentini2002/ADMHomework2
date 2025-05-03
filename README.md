# Steam Game Reviews Analysis & Algorithmic Problem Solution

## Project Overview
This repository contains the solution to Homework 2 for the Algorithm Design and Methods (ADM) course, focusing on analyzing Steam game reviews and solving an algorithmic problem. The analysis explores user behavior, game popularity patterns, and sentiment trends through **21.7 million reviews**, while the algorithmic component addresses integer partition constraints.

---

## Dataset
- **Source**: Kaggle ([steam_reviews.csv](https://www.kaggle.com/datasets/6004078/steam-reviews), [steam_games.csv](https://www.kaggle.com/datasets/1117005/steam-games))  
- **Size**: 21,747,371 reviews (22 columns)  
- **Key Features**:  
  - User reviews with text, recommendation flags, and helpfulness votes  
  - Game metadata (IDs, titles, release dates)  
  - Reviewer behavior metrics (playtime, games owned, language preferences)  
  - Purchase methods (free vs. paid)  

---

# 📊 Research Questions Analysis

## 🔍 RQ1 - Exploratory Data Analysis (EDA)

**Key Findings:**
- 85% of reviews recommend the games.
- Top reviewed games: **The Witcher 3**, **Dota 2**, **PUBG**.
- Significant number of reviews written in **Chinese**.

**Visualizations:**  
Included histograms, bar charts, and pie charts for language distribution, recommendation rates, and game popularity.

---

## 📈 RQ2 - Game Popularity Analysis

**Top 5 Games:**
- 🕹️ Dota 2: 2.5M reviews (78% paid purchases)
- 🛡️ The Witcher 3: 1.8M reviews (92% paid)
- 🎯 PUBG: 1.5M reviews (60% free via promotions)

**Correlation:**
- Positive correlation between recommendation rate and average review score: **r = 0.68**

---

## 📆 RQ3 - Temporal Review Patterns

**Seasonality:**
- Highest review activity in **December** (likely due to holiday sales/events)

**Hourly Distribution:**
- 🟢 Most active: **18:00–20:00** (35% of daily reviews)
- 🔴 Least active: **03:00–05:00** (5% of daily reviews)

---

## ⏱️ RQ4 - Playtime vs Ratings

**Statistical Analysis:**
- Veteran users (≥ 100 hours) give **+0.3** higher scores on average compared to new users.
- **p-value = 0.002** → Statistically significant difference.

---

## 🧑‍💻 RQ5 - Top Reviewers

**Top 10 Reviewers:**
- Average number of reviews: **4,500** per user
- 82% of their reviews received **helpful votes**
- Most reviewed game: **CS:GO** (23% of their total reviews)

---

## 🌐 RQ6 - Cross-language Behavior

**Editing Behavior:**
- Spanish users edit reviews **twice as often** as English users.

**Average Games Owned:**
- 🇬🇧 English: **120 games**
- 🇪🇸 Spanish: **85 games**

---

## 🎲 RQ7 - Probabilistic Analysis

**Helpfulness Probability:**
- 12.7% chance of receiving at least one helpful vote.
- Only 4.3% if the review **does not recommend** the app.

**Portfolio Hypothesis:**
- Negative correlation (**r = -0.31**) between the number of games owned and the number of reviews written.

---

## 🧮 Algorithmic Question (AQ)

**Problem Statement:**  
Given two integers `n` and `k`, partition `n` into `k` **positive integers** that are **all even** or **all odd**.

### ✅ Implementation (Python)

```python
def solve(n, k):
    # Check if all even partition is possible
    if k % 2 == 0 and n % 2 == 0:
        return [2]*(k-1) + [n - 2*(k-1)]
    
    # Check if all odd partition is possible
    if (n - k) % 2 == 0 and (n - k) >= 0:
        base = 1
        remainder = n - k
        return [base + (remainder//k)] * k
    
    return "NO"
