<p align="center">
  <img src="cover_user.png" width="100%" alt="E-Commerce Analytics Dashboard cover">
</p>

# 📱 User Behaviour Funnel & A/B Testing — Food App Analysis

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Statistics](https://img.shields.io/badge/Statistical_Testing-A/A/B-red)
![Visualization](https://img.shields.io/badge/Visualization-Plotly%20%7C%20Matplotlib-green)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview

This project was developed as part of the **Data Analytics Bootcamp at [TripleTen](https://tripleten.com)**.
It analyses **user behaviour** in a food-delivery app and evaluates the impact of a **font-style redesign** through an **A/A/B test**.

Two control groups (246 and 247) used the **original font**, and one test group (248) received the **new design**.
The analysis explores how users move through the **conversion funnel** and checks whether the new font affects user engagement or purchases.

💻 **Repository:** [https://github.com/MarcelaMaris/User-Behaviour-Funnel-A-B-Testing](https://github.com/MarcelaMaris/User-Behaviour-Funnel-A-B-Testing)


---

## 🎯 Objectives

* Clean and prepare raw **user event logs** from the app.
* Explore the **sales funnel** and identify drop-offs between stages.
* Validate data quality and experimental group balance through an **A/A test**.
* Run statistical tests (Z-test with Bonferroni correction) to compare event proportions.
* Determine whether the new font design (Group 248) significantly changes user behaviour.

---

## 🧭 Methodology

1. **Data Preparation** – Loaded, renamed, and formatted columns from `logs_exp_us.xlsx` (timestamp conversion, date extraction).
2. **EDA (Exploratory Data Analysis)** – Counted unique users/events, determined event frequency, and ensured coverage for all groups.
3. **Funnel Analysis** – Built a sequential funnel (`MainScreenAppear → OffersScreenAppear → CartScreenAppear → PaymentScreenSuccessful`) to visualise retention and loss between stages.
4. **A/A Testing** – Compared groups 246 and 247 using a two-proportion Z-test with Bonferroni correction to confirm randomisation validity.
5. **A/B Testing** – Tested whether the new font (group 248) influenced engagement or conversion compared with controls.

---

## 📊 Conclusions

* Approximately **7,500 users** recorded events; only ~6% reached the final payment step.
* The highest drop-off occurred between **Offers → Cart**, signalling a key optimisation point.
* **A/A test confirmed group equivalence**, validating experimental reliability.
* The **new font (group 248)** did **not produce statistically significant differences** in any stage of the funnel.
* Conversion funnel visualisation highlighted consistent user behaviour across all groups.

---

## 📝 Recommendations

* **Focus on mid-funnel optimisation**
  Prioritise UX improvements between offers and cart screens, where most users abandon the flow.
* **Test broader design changes**
  Font alone did not impact engagement; future tests could involve button layout, colours, or navigation clarity.
* **Maintain experiment discipline**
  Continue validating A/A consistency before A/B rollouts to ensure experimental reliability.
* **Monitor behaviour trends**
  Build a periodic funnel analysis to track shifts in conversion and friction points over time.

---

## 💡 Key Business Impact

* Provided data-driven evidence that **visual style adjustments** (font redesign) have minimal behavioural effect.
* Established a **reusable experimental framework** for future UI/UX tests.
* Identified the **main user loss point** in the funnel, enabling focused optimisation.
* Strengthened product decision-making with **statistical validation** rather than subjective design opinions.

---

## 🛠️ Tech Stack

* **Data Analysis**: Python, Pandas, NumPy
* **Statistical Testing**: SciPy, math, Bonferroni correction
* **Visualisation**: Matplotlib, Plotly (Funnel)
* **Environment**: Jupyter Notebook
* **Dataset**: `data/logs_exp_us.xlsx`

---

## 📘 Folder Structure

```
Project-11-Tripleten/
│
├── data/
│   └── logs_exp_us.xlsx
│
├── notebooks/
│   └── user_behavior_funnel_abtest.ipynb
│
└── README.md
```

