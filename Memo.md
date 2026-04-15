# FX Receivables Hedge Assessment – Solar Equipment Division

**Created by:** Treasury & Risk Management  
**Updated by:** teona5647  
**Date Created:** 2026-04-04  
**Date Updated:** 2026-04-04  
**Version:** 1.0  
**LLM Used:** None

---

## Executive Summary

Our solar equipment division has a confirmed EUR 3.9M receivable due in 12 months from a major European client. At today's spot rate (EURUSD 1.1525), this translates to approximately USD 4.5M in expected proceeds. However, currency fluctuations pose material risk to USD cash flow. EUR depreciation of just 5% would reduce proceeds by ~USD 225K. This memo evaluates three hedging strategies—forward contracts, put options, and a collar—to mitigate downside risk while preserving upside potential. We recommend proceeding with detailed financial modeling (Stage 2) to quantify trade-offs and finalize our hedging recommendation by Q2 2026.

---

## Background & Objectives

**The Exposure:**  
- **Currency & Amount:** EUR 3.9 million (equivalent to ~USD 4.5M at current spot)  
- **Timing:** Payment expected in 12 months (April 2027)  
- **Why It Matters:** FX volatility directly impacts our reported USD revenues and cash margins. A 5–10% EUR depreciation is realistic over a 12-month horizon, creating a potential USD 225–450K headwind.

**Objectives:**
1. Protect minimum USD proceeds (downside protection)
2. Evaluate the cost of hedging strategies relative to earnings volatility
3. Determine the optimal hedge ratio and instrument mix by Q2 2026
4. Establish a repeatable FX hedging framework for future international receivables

---

## Methods

We will evaluate three hedge families:

### **1. Forward Contract**
- **Approach:** Lock in the 1-year forward rate (~1.0875 EURUSD) to eliminate FX uncertainty.
- **Pros:** Simple, zero upfront cost, fully predictable USD proceeds (USD 4.24M fixed).
- **Cons:** No upside participation if EUR appreciates; inflexible if receivable is delayed or cancelled.

### **2. Put Option (EUR Put/USD Call)**
- **Approach:** Buy a put option with strike at/near spot (1.1525) and premium ~USD 0.015/EUR.
- **Pros:** Downside protection (floor) while retaining upside if EUR strengthens; capped maximum loss.
- **Cons:** Upfront premium cost (~USD 58.5K) reduces net proceeds; requires monitoring and discipline.

### **3. Collar (Put Sold/Call Bought)**
- **Approach:** Buy a protective put and sell a covered call at a higher strike to offset premium.
- **Pros:** Reduced or zero net cost vs. standalone put; predictable cost structure; intuitive for CFO communication.
- **Cons:** Caps upside gains; requires precise strike selection to balance cost and protection.

---

## Limitations & Next Steps

**Known Constraints:**
- Forward rates and option premiums may shift as we approach Stage 2 implementation (basis risk).
- Hedge effectiveness depends on timing of actual payment; delays may trigger basis mismatch.
- Accounting treatment (hedge accounting vs. mark-to-market) will affect P&L volatility.

**Immediate Next Steps:**
1. **Stage 2 (Excel Build):** Construct a sensitivity model comparing hedge outcomes across EURUSD scenarios (1.05–1.25).
2. **Assign ownership:** Treasury team to validate current market quotes and confirm counterparty capabilities.
3. **Stage 3 (Technical Spec):** Document assumptions and prepare scalable model for future receivables.
4. **Stage 4 (Final Recommendation):** Present quantified P&L impact and recommend optimal strategy to CFO by end of Q2 2026.

---

## References

1. Bloomberg L.P. (2026, April 3). *EURUSD spot exchange rate and forward quotes*, market close.
2. U.S. Federal Reserve. (2026). *Federal Funds Rate Target Range*, 5.25–5.50%.
3. European Central Bank. (2026). *Main Refinancing Operations Rate*, ~4.50%.
4. Investing.com. *EUR/USD Historical Data*, accessed April 4, 2026.
5. Shidler MBA Course Materials. *Foreign Exchange Risk Management Framework*.
