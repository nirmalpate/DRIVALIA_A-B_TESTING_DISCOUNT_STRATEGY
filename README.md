# DRIVALIA_A-B_TESTING_DISCOUNT_STRATEGY
This README covers both iterations of the Drivalia Pricing Strategy A/B Test. The first focused on **Volume (Conversion)**, while the second focused on **Profitability (Revenue)**.

---

# Drivalia Dynamic Pricing & Utilization A/B Tests

This repository contains the experimental design, simulation code, and statistical analysis for two distinct A/B tests aimed at optimizing fleet utilization and revenue through tiered pricing.

## 📊 Test 1: Utilization Optimization (The "Volume" Test)

**Primary Goal:** Increase car utilization from 60% to 85%.

* **Success Metric:** Conversion Rate (Utilization %).
* **Guardrail Metric:** Total Revenue (to ensure deep discounting doesn't destroy value).
* **Hypothesis:** Offering a 20% discount relative to competitors will lower the barrier to entry and drive utilization to the 85% target.
* **Sample Size:**  per group (Calculated to detect a large delta in proportions).
* **Statistical Method:** * **Chi-Square Test** for Conversion.
* **T-Test** for Revenue.



---

## 💰 Test 2: Revenue Maximization (The "Value" Test)

**Primary Goal:** Increase Average Revenue Per User (ARPU) while maintaining high utilization.

* **Success Metric:** Average Revenue Per User (ARPU).
* **Guardrail Metric:** Conversion Rate (to ensure price adjustments don't tank utilization).
* **Hypothesis:** Implementing tiered duration discounts (10% off for 2 days, 20% off for 3 days) will increase the Average Order Value (AOV) and total revenue.
* **Sample Size:**  per group (Calculated to detect a difference in means amidst high variance).
* **Statistical Method:**
* **Welch's T-Test** for Revenue (Primary).
* **Chi-Square Test** for Conversion (Guardrail).



---

## 🛠️ Implementation Details

### Pricing Logic

* **Base Price:** Randomly generated between €50 - €90.
* **Treatment Discount:** 20% flat discount on the daily rate.
* **Duration Incentives:**
* 1 Day: No additional discount.
* 2 Days: 10% discount on the total.
* 3 Days: 20% discount on the total.



### Key Learnings on Statistical Power

* **Metric Sensitivity:** Conversion is a binary metric (0 or 1) and requires much smaller sample sizes to reach significance.
* **Revenue Variance:** Revenue is highly volatile. Outliers (e.g., a single 3-day high-end rental) can skew results in small samples.
* **The "Wash" Effect:** In Test 1, while utilization hit 85%, the p-value for revenue remained high (>0.05), indicating that the volume gain and price cut were effectively balancing each other out (neutral revenue impact).

---

 
