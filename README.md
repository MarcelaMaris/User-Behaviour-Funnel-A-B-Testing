<p align="center">
  <img src="cover_user.png" width="100%" alt="User Behaviour Funnel & A/A/B Testing cover">
</p>

## <img src="icons/funnel.png" width="50">  &nbsp;&nbsp;User Behaviour Funnel & A/A/B Testing — Food-Delivery App Analysis
<br>

![Python](https://img.shields.io/badge/Python-3.10%2B-0A3756?style=flat&logo=python&logoColor=F5F7FA&labelColor=E8AA3A)
![Pandas](https://img.shields.io/badge/Pandas-lib-0A3756?style=flat&logo=pandas&logoColor=F5F7FA&labelColor=E8AA3A)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-0A3756?style=flat&logo=jupyter&logoColor=F5F7FA&labelColor=E8AA3A)
![Experiment](https://img.shields.io/badge/Experiment-A%2FA%2FB%20Testing-0A3756?style=flat&logo=academia&logoColor=F5F7FA&labelColor=E8AA3A)
![Visualisation](https://img.shields.io/badge/Visualisation-Plotly%20%7C%20Matplotlib-0A3756?style=flat&logo=plotly&logoColor=F5F7FA&labelColor=E8AA3A)

> This project analyses **user behaviour** in a food-delivery startup app and evaluates the impact of a **UI font change**  
> through an **A/A/B experiment**.
>
> The analysis combines **product analytics** (conversion funnel) with **statistical testing** (two-proportion z-tests)  
> to assess whether the variant changed user behaviour.
>
> It is designed to mirror how a **Data Analyst / Product Analyst** would validate experiment integrity (A/A),  
> measure funnel drop-offs, and make evidence-based rollout decisions.

---

## <img src="icons/objectives.png" width="30">  &nbsp;&nbsp;Objectives

- Clean and prepare raw **event logs** for analysis (timestamps, dates, standardised columns).
- Understand user engagement through key metrics (events, users, coverage period).
- Build a **sequential conversion funnel** to quantify drop-offs across the user journey.
- Validate experimental integrity with an **A/A test** (control vs control).
- Test the impact of the UI change (new font) with **A/B comparisons** using z-tests.
- Apply **Bonferroni correction** to control false positives from multiple tests.

---

## <img src="icons/features.png" width="30">  &nbsp;&nbsp;Key Analyses & Features

- **Data Preparation:**  
  Renamed fields, converted UNIX timestamps to datetime, extracted dates, and ensured tidy event-level structure.

- **Reliability Cut (Data Quality):**  
  Trimmed early sparse data and analysed only the reliable period **from 2019-08-01 onwards**.

- **Experiment Group Balance:**  
  Verified that groups **246, 247, 248** had similar sample sizes after filtering.

- **Sequential Funnel Modelling:**  
  Built an ordered funnel enforcing event chronology:  
  *MainScreenAppear → OffersScreenAppear → CartScreenAppear → PaymentScreenSuccessful*.

- **Funnel Visualisation:**  
  Line chart and Plotly funnel chart to highlight the steepest drop-off points.

- **A/A/B Statistical Testing:**  
  Two-proportion z-tests for event-level participation rates, with Bonferroni correction for multiple comparisons:
  - A/A: **246 vs 247**
  - A/B: **248 vs 246**, **248 vs 247**, and **248 vs combined controls**

---

## <img src="icons/dataset.png" width="30">  &nbsp;&nbsp;Dataset

**Source:**  
Simulated event-log dataset from a food-delivery app (bootcamp scenario).

**Columns**
- `event_name` — event type (screen / action)
- `user_id` — anonymised device/user identifier
- `timestamp` — UNIX time
- `exp_id` — experiment group (246, 247, 248)

**Notes**
- The original file is tab-delimited (`.csv` with `\t` separator).
- Early dates were sparse; analysis focuses on the stable period from **2019-08-01**.

---

## <img src="icons/funnel.png" width="30">  &nbsp;&nbsp;Conversion Funnel

The sequential funnel (ordered by time) shows:

- **Main → Offers:** 56.6%  
- **Offers → Cart:** 42.1%  
- **Cart → Payment:** 25.7%  
- **End-to-end conversion:** **~6.1%**

This highlights a strong bottleneck in the later stages, especially **Cart → Payment**, where abandonment is most acute.

---

## <img src="icons/conclusions.png" width="30">  &nbsp;&nbsp;Key Findings

- The experiment was **well configured**, with balanced groups and a clean A/A validation.
- The funnel shows a steep drop-off, with only **~6%** of users reaching payment completion.
- The **A/A test (246 vs 247)** found no significant differences, supporting reliable randomisation.
- The **A/B comparisons** showed **no statistically significant differences** between the new font (248) and controls.
- Under a conservative multiple-testing approach (Bonferroni), results remain consistent:  
  **the font change did not meaningfully affect user behaviour**.

---

## <img src="icons/recommendations.png" width="30">  &nbsp;&nbsp;Recommendations

- **Prioritise checkout optimisation**  
  Investigate friction points in *Cart → Payment* (trust, payment options, form complexity, error states).

- **Test higher-impact UI/UX changes**  
  Font alone showed no measurable effect; future experiments could test CTA placement, navigation clarity, and checkout flow simplification.

- **Maintain experiment discipline**  
  Keep using A/A validation and multiple-testing control to avoid false positives and risky rollouts.

- **Operationalise funnel monitoring**  
  Track funnel conversion weekly and segment by device, traffic source, or cohort to pinpoint behavioural shifts.

---

## <img src="icons/impact.png" width="30">  &nbsp;&nbsp;Business Impact

- Provided evidence that a **cosmetic UI change** (font) is safe to roll out.
- Identified the primary conversion bottleneck for product prioritisation (**Cart → Payment**).
- Delivered a reusable framework for **experiment validation + funnel insight generation**.

---

## <img src="icons/techstack.png" width="30">  &nbsp;&nbsp;Tech Stack

- **Languages & Libraries:** Python (3.10), Pandas, NumPy  
- **Statistics:** SciPy / z-tests, Bonferroni correction  
- **Visualisation:** Matplotlib, Plotly  
- **Environment:** Jupyter Notebook  
- **Version Control:** Git & GitHub  

---

<p align="center">
  <sub>📊 Designed & developed by <b>Marcela Maris</b> — Data Analytics Portfolio</sub><br>
  <sub><i>Product Analytics • Funnel Analysis • Experimentation</i></sub>
</p>
