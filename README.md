# Sampling Methods for Business Population in Sector G – R Project

## Summary

This project compares two sampling methods—simple random sampling without replacement (OSU) and stratified random sampling without replacement with Neyman allocation (STOSU)—for estimating key parameters in a simulated population of companies in Sweden's industry sector G (Wholesale; repair of motor vehicles and motorcycles).  
Estimated parameters include total turnover, average investments, total number of employees, and a domain analysis focused on small companies (≤ 20 employees).  
After drawing a sample of about 4,500 companies, results show that STOSU provides more accurate estimates and significantly lower variance for totals compared to OSU. The report analyzes these findings and discusses possible improvements such as ratio estimation and alternative domains.  
The conclusion is that stratification is effective when correlated auxiliary variables are available and that sample design is crucial for precision and accuracy.

---

## Project Structure

- **Data:** Simulated Excel data of companies in sector G, segment 46 (Wholesale).
- **Analysis:** Estimation of total turnover, average investments, total employees, and domain-specific estimates for small companies.
- **Sampling Methods:**
  - OSU: Simple random sampling without replacement.
  - STOSU: Stratified sampling by company size (number of employees) with Neyman allocation.
- **Statistical Tools & Packages:**  
  - R, with `sampling` and `rio` packages.
  - Functions: `strata`, `getdata`, `HTestimator`, `varest`.

---

## Research Questions

1. How well does OSU estimate total turnover, average investment, and total employees in a domain?
2. What are the effects of STOSU compared to OSU on point estimates, variance, and precision for key variables?
3. What added value does domain estimation for companies with ≤ 20 employees provide?
4. Which sampling method is most suitable for analyzing company structure in a population with varying sizes and industry distribution?

---

## Key Results

- **True values** (from the full population, with scope=1) are calculated for comparison.
- **Sample size:** About 4,500 companies (from a population of ~39,654).
- **OSU Results:**  
  - Provides unbiased estimates but tends to over/underestimate totals and mean investments, with higher variance.
- **STOSU Results:**  
  - Stratification by company size dramatically reduces variance and increases precision.
  - Neyman allocation assigns more samples to strata with higher variability (large companies).
  - Estimates for the domain of small companies (≤ 20 employees) are much closer to true values.
- **Domain Estimation:**  
  - Analysis for small companies highlights differences in resource distribution between small and large firms—important for economic policy and reporting.

---

## Conclusions

- Stratified sampling with Neyman allocation improves accuracy and lowers variance.
- Correlation between auxiliary and study variables is key for efficient sample design.
- Ratio estimation or other models could further improve precision if auxiliary register data is available.
- Domain analysis is valuable for understanding subgroups, especially small businesses.
- Method choice substantially impacts both precision and reliability of survey estimates.

---

## How to Run

1. Place the simulated Excel data file in the project directory.
2. Use the provided R script (`analysis.R`) to run the sampling, estimation, and variance calculations.
3. Required packages: `sampling`, `rio`.
4. The script includes all code for OSU and STOSU designs, HT estimators, variance calculations, and domain analysis.

---

## Files

- `analysis.R`: Main R script for data import, sampling, estimation, and analysis.
- `data.xlsx`: Simulated company data for sector G.
- `README.md`: Project explanation and instructions.

---

## Variable Definitions

- **nace:** 4-digit industry code (SNI2007).
- **Turn_admin:** Turnover (can be zero).
- **N_emp:** Number of employees.
- **scope:** 1 = in target population, 0 = outside.
- **turn:** Reported turnover in the survey.
- **inv:** Investments reported in the survey.
- **emp_sbs:** Number of employees reported in the survey.

---
