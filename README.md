# ⚽ Women's vs Men's FIFA World Cup: Are Women's Matches More High-Scoring?

![FIFA Banner](soccer-pitch2.jpg)

This data analysis project investigates whether **women's FIFA World Cup matches** are more high-scoring than **men's**, based on official match results since January 1, 2002. Using statistical hypothesis testing and visualizations, we explore whether this common observation holds true.

---

## 📊 Objective

> Are more goals scored in women's FIFA World Cup matches than in men's?

To answer this, we perform a one-sided **Mann–Whitney U test** with a significance level of **10% (α = 0.10)**.

---

## 🧪 Hypotheses

- **Null hypothesis (H₀)**: The mean number of goals scored in women's matches is **equal** to men's.
- **Alternative hypothesis (H₁)**: The mean number of goals scored in women's matches is **greater** than men's.

---

## 📁 Dataset

The data was scraped from a reliable online source and contains the following:

- `men_results.csv` — all official men's FIFA World Cup matches since 2002
- `women_results.csv` — all official women's FIFA World Cup matches since 2002
- Columns used:
  - `date`
  - `home_team`
  - `away_team`
  - `home_score`
  - `away_score`
  - `tournament`
  - `goals_scored` = home_score + away_score
  - `group` = men / women

---

## 📉 Visualizations

We compared the **distribution of total goals per match** using histograms and KDE plots.

- Men’s matches mostly score **1–3 goals**, with fewer high-scoring games.
- Women’s matches also peak around **2–3 goals**, but show a **heavier right tail**, indicating more frequent high-scoring games.


---

## 🧠 Normality Check (Shapiro-Wilk Test)

Both distributions significantly deviate from normality:

| Group   | p-value          | Normal?     |
|---------|------------------|-------------|
| Men     | 8.89 × 10⁻¹³     | ❌ No       |
| Women   | 3.89 × 10⁻¹³     | ❌ No       |

✅ Therefore, we use a **non-parametric test**.

---

## 📊 Mann–Whitney U Test (One-sided)

```python
p-value: 0.00511 → reject the null hypothesis.
