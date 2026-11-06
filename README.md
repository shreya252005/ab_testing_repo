# ab_testing_repo

# Ticketmaster Checkout Optimization: A/B Testing & Statistical Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_COLAB_NOTEBOOK_LINK_HERE)

## 📌 Project Overview
An end-to-end A/B testing simulation and statistical analysis pipeline built to evaluate the business impact of replacing an interactive stadium seating map with a streamlined "Quick Select" modal on a high-volume ticketing marketplace. 

This project demonstrates rigorous experimental design, data validation, hypothesis testing, iterative sample sizing, and advanced data visualization to support data-driven product decisions.

---

## 🔍 Iterative Experimentation & Sample Size Optimization
A key highlight of this project was addressing statistical power constraints:
* **The Initial Iteration ($N = 50,000$):** Initial simulation runs yielded a p-value of $0.182$, resulting in a failure to reject the null hypothesis (statistically non-significant). This underscored a critical real-world lesson: running tests with inadequate sample sizes risks **Type II errors (false negatives)**, where a genuinely beneficial product feature is prematurely killed because the test lacked the statistical power to detect the true effect.
* **The Optimized Iteration ($N = 60,000$):** By scaling the sample size to ensure sufficient statistical power for our Minimum Detectable Effect (MDE), the pipeline successfully detected a statistically significant conversion lift ($p = 0.000002$), proving that user choice paralysis is mitigated by the "Quick Select" modal.

---

## 📊 Methodology & Statistical Rigor
The analysis follows a robust data science workflow:
* **Experimental Design & Simulation:** Simulated user sessions split evenly (50/50 allocation) into Control (Interactive Map) and Variant (Quick Select) groups using pseudo-random hashing.
* **Sample Ratio Mismatch (SRM) Validation:** Executed a **Chi-Square Goodness-of-Fit Test** to verify traffic allocation integrity, yielding a clean split ($p = 0.94$).
* **Hypothesis Testing:** Utilized a **Two-Proportion Z-Test** to measure conversion rate lift.
* **Uncertainty Quantification:** Calculated **95% Wilson Score Intervals** to accurately capture proportion confidence boundaries.
* **Bootstrapping:** Performed $1,000$ bootstrap resamples to generate a distribution of relative lift (showing a robust mean relative lift of **18.01%**).

---

## 📈 Key Findings & Visualizations
The analysis pipeline generates three professional analytical charts to evaluate the experiment:
* **Conversion Rate Comparison:** Visualizes the baseline control (4.80%) versus variant (5.65%) lift backed by tight Wilson Confidence Intervals.
* **Cumulative Conversion Convergence:** Tracks running conversion averages over a 14-day window to guard against early-stopping bias and novelty effects.
* **Bootstrap Lift Distribution:** Illustrates the probability distribution of relative lift entirely to the right of zero.

> **Why This Matters for Companies:** In tech companies, product teams frequently misinterpret underpowered tests as proof that a feature "doesn't work." This project highlights the vital importance of **power analysis and sample size planning** before launching experiments, ensuring organizations don't discard high-impact UX improvements due to statistical noise.

---

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `scipy`, `statsmodels`, `matplotlib`, `seaborn`

---

## 🚀 How to Run
You can run, inspect, or modify the complete analysis interactively by clicking the **"Open in Colab"** badge at the top of this readme.

