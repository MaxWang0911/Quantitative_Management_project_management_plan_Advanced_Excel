# Advanced Excel Project Selection Model for Ewing Natural Gas

> 📌 **Real-world capital planning optimisation** using advanced Excel modelling, linear programming, and quantitative risk analysis.

---

## 🏢 Business Background

Ewing Natural Gas, a $50B energy company, must select a portfolio of capital projects to fund over 3 years. Each proposed project comes with:

- Multi-year capital expenditure (CapEx) schedules  
- Net Present Value (NPV) forecasts  
- Strategic importance from various business units  

The **Project Development Manager** faces two key challenges:
1. Stay within a **strict capital budget**: No more than $4B/year, $10B total over 3 years.
2. Ensure **equitable project representation** across functional areas.

The total cost of all proposed projects exceeds the budget. Hence, **optimisation and risk-aware decision-making are essential.**

---

## 🔍 Problem Statement

Cliff Erland, the project manager, must determine:

- ✅ Which projects to select over 3 years
- ✅ How to maximise total NPV
- ✅ How to stay within the budget **with 95% confidence**, considering CapEx and NPV uncertainty
- ✅ How to ensure each business unit is represented

---

## 📊 Analytical Approach

### ✅ Step 1: Deterministic Model (Baseline)

- **Tool**: Excel Solver (Simplex LP)
- **Objective**: Maximize total NPV
- **Constraints**: 
  - Annual CapEx ≤ $4B
  - Total CapEx ≤ $10B
  - Binary decision variables (0 or 1) per project
  - Each functional unit must have ≥ 1 approved project

**Result**:
- Selected 9 projects  
- Total NPV: **$1,769M**  
- Budget respected: Yearly CapEx: 3.58B, 3.30B, 3.08B → Total: 9.97B

---

### 🎲 Step 2: Risk Modelling (Beta-PERT)

All CapEx and NPV inputs are modelled with uncertainty:

| Parameter | Distribution | Range                |
|----------|--------------|----------------------|
| CapEx    | Beta-PERT    | -15% to +30%         |
| NPV      | Beta-PERT    | -20% to +15%         |

- Used **RAND + BETAINV** to simulate 1,000 iterations per project
- Calculated expected total NPV and confidence intervals
- Evaluated **risk of exceeding budget caps**

**Findings**:
- Per-year budget risk: very low  
- 3-year budget overrun probability: **88.7%**
- Exceeding budget by >5%: **7.2%**
- Simulated NPV mean: ~1,755M with tight CI

---

### 🧠 Step 3: Optimisation Under Uncertainty

Objective: **Maximise expected NPV while ensuring 95% budget feasibility**

#### Solution 1: Cash Reserve (Most Practical)
- Add buffer to expected CapEx
- Use mean values for NPV
- Optimised with Excel Solver
- **Result NPV**: **$1,635M**

#### Solution 2: Genetic Algorithm
- Convert simulated values to fixed samples
- Optimise using Evolutionary Solver in Excel
- **Result NPV**: **$1,620–1,625M**

#### Solution 3: Integer Programming (Infeasible)
- Same logic as above but too complex for Excel Solver due to scale
- Not recommended

---

## 📌 Key Takeaways

- ✅ **Advanced Excel techniques** like Solver, BETAINV, data tables, and stochastic simulation can solve complex real-world decisions
- ✅ Integrating **uncertainty into capital planning** leads to better-informed and risk-aware decisions
- ✅ Simplex LP performs well in deterministic cases, while evolutionary methods help under uncertainty
- ✅ Cash-reserve models offer a **practical compromise between risk and return**

---


## 📘 Reference

Winston, W. L., & Albright, S. C. (2017). *Practical Management Science* (5th ed.). South-Western Cengage Learning.

---

## ✅ Summary

This project is a complete **quantitative management case study** applied to a real-world corporate investment problem. It demonstrates how to:

- Translate qualitative constraints into mathematical models  
- Build and solve models using **advanced Excel tools**  
- Incorporate uncertainty via simulation and probability constraints  
- Provide actionable, data-driven recommendations for executives

---
