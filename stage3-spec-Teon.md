# FX Hedge Model – Technical Specification

**Created by:** Anahi Teon  
**Updated by:** Anahi Teon  
**Date Created:** 2026-04-25  
**Date Updated:** 2026-04-25  
**Version:** 1.0  
**LLM Used:** None

**Role:** Financial Analyst / Treasury Analyst  
**Audience:** CFO or Director of Treasury  

**Purpose:** Provide a professional, quantitative specification outlining the analytical structure for evaluating FX hedging alternatives.

---

## 1. Problem Statement

Our company expects to receive a EUR-denominated payment in 12 months, specifically 3,900,000 EUR. This creates exposure to adverse movements in the EUR/USD exchange rate before settlement. The objective is to protect the USD value of this receivable, evaluating alternative hedging strategies to optimize proceeds and risk in a corporate treasury context.

---

## 2. Inputs (Known Variables)

| Variable            | Description                        | Unit         | Value      | Source           |
|---------------------|------------------------------------|--------------|------------|------------------|
| `FC_AMT`            | Foreign-currency receivable        | EUR          | 3,900,000  | Company data     |
| `S0`                | Spot Rate (USD per FC)             | USD/EUR      | 1.1525     | Market data      |
| `F0`                | Forward Rate (USD per FC)          | USD/EUR      | 1.0875     | Market data      |
| `R_USD`             | USD Interest Rate                  | Annual (%)   | 0.05375    | Market data      |
| `R_FC`              | Foreign Interest Rate (EUR)        | Annual (%)   | 0.045      | Market data      |
| `K_PUT`             | Put Option Strike                  | USD/EUR      | 1.1525     | Analytic choice  |
| `K_CALL`            | Call Option Strike                 | USD/EUR      | 1.1525     | Analytic choice  |
| `PREM_PUT`          | Put Premium (per FC)               | USD          | 0.015      | Scenario         |
| `PREM_CALL`         | Call Premium (per FC)              | USD          | 0.018      | Scenario         |
| `T_DAYS`            | Time Horizon                       | Days         | 365        | Contract         |

---

## 3. Assumptions & Constraints

- Interest rates are quoted annual, ACT/365 basis.
- All FX rates reflect direct USD/FC (EUR) conventions.
- Forward contract is for 1-year settlement.
- Option premiums are paid upfront, in USD, and not refunded.
- Transaction costs, taxes, and credit charges are excluded.
- Sensitivity analysis does not include dynamic hedging, early exercise, or other risk management overlays.

---

## 4. Calculation Flow

1. **Forward Hedge:** Multiply `FC_AMT` by `F0` to determine guaranteed USD proceeds at settlement.
2. **Money Market Hedge:** 
    - Discount the FC amount to present value using EUR rates: PV = FC_AMT / (1 + R_FC).
    - Convert PV to USD at spot rate: USD_PV = PV × S0.
    - Invest the USD amount at the USD interest rate for 1 year to obtain maturity value.
3. **Option Hedge (Put/Call):**
    - Compute total cost for put/call premiums: Premium × FC_AMT.
    - For each ending spot rate `S_T` in the analysis, calculate proceeds:
        - If `S_T` < `K_PUT`: exercise put.
        - If `S_T` > `K_CALL`: exercise call.
        - Else: convert at `S_T`.
    - Subtract total premiums paid from gross USD amount.
4. **Unhedged:** Calculate USD proceeds as FC_AMT × `S_T`.
5. **Sensitivity Analysis:** For each scenario value of `S_T`, compare proceeds across all hedge and unhedged strategies.
6. **Visualization:** Plot USD proceeds versus `S_T` (line chart), highlighting strategy differences.

---

## 5. Outputs

| Output                | Description                                | Format        | Purpose                                               |
|-----------------------|--------------------------------------------|---------------|-------------------------------------------------------|
| `USD_forward`         | USD proceeds from forward hedge            | Numeric       | Certainty benchmark                                   |
| `USD_mm`              | USD proceeds from money market hedge       | Numeric       | Cross-check, identifies inefficiencies                |
| `USD_put`             | USD proceeds from EUR put hedge            | Sensitivity table | Downside protection with limited upside           |
| `Summary Table`       | All scenarios, all strategies              | Table         | Full comparison and results by spot                   |
| `Chart_1`             | Line chart, proceeds vs. `S_T`             | Visual        | Communicates outcome by strategy                      |
| `Recommendation`      | Written recommendation based on analysis   | Paragraph     | Executive summary for decision                        |

---

## 6. Sensitivity Plan

- Vary `S_T` from approximately 1.095 to 1.210 in equal increments.
- At each `S_T`, compute unhedged, forward, MM, and option hedge USD proceeds.
- Tabulate and graph proceeds by strategy, highlighting breakevens and risk.
- Use ±5% around spot as scenario bounds, matching the observed table and chart.

---

## 7. Model Review — What Worked & What To Improve

- Calculation structure clear, variable naming entered as per standard, scenario analysis fully outputted.
- Model does not include transaction costs or credit spreads—should be added in future.
- Layout could benefit from dedicated named ranges for key input/output cells for audibility.
- Put hedge scenario table could be extended for call and complex option strategies.
- More granular scenario steps could improve sensitivity precision.
- Recommendation cell left for interpretative comment.

---

## 8. Limitations & Next Steps

- No modeling for dynamic/rolling hedges, credit risk, or accounting.
- Outputs are based on yearly settlement and do not cover partial hedges or window forwards.
- Next, refine model structure and formulas for future AI prompt use; consider adding new strategy scenarios.

---

# 🧭 Writing a Strong Specification

- Communicate clearly and use standardized variable names.
- Each input and output traceable to model; logic reproducible without ambiguity.
- Document assumptions and steps for AI/model rebuild in Stage 4.

---

## 🔗 How This Sets You Up for Later Stages

| Stage     | What This Spec Enables                                            |
|-----------|-------------------------------------------------------------------|
| **Stage 3** | Documents and refines model for optimal clarity and improvement.| 
| **Stage 4** | Feeds into AI prompt for automated or code-based implementation.| 

> *This spec, with included image ![image1](image1), serves as the bridge from financial analysis to robust, repeatable modeling and automation.*
