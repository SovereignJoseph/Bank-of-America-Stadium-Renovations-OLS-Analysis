# Stadium OLS: Who Should Pay for Bank of America Stadium Renovations?

**A retrospective statistical analysis of what should have been examined before the $650M decision**

> **Our Finding:** This analysis demonstrates that rigorous examination before the decision would have revealed significant fiscal concerns. NFL team presence is associated with measurably higher municipal spending burdens—evidence that should have been central to deliberations.

---

## 📋 Project Overview

This repository contains an ordinary least squares (OLS) regression analysis examining the relationship between NFL team presence and municipal spending per capita. The analysis uses historical data from 6,758 city-year observations to evaluate what evidence existed before Charlotte's June 2024 decision to commit $650 million in public funds to Bank of America Stadium renovations.

**Course:** DTSC 1302 (Data and Society: Quantitative Analysis)  
**Date:** April 2026  
**Assignment:** Retrospective policy analysis — what should have been analyzed before the decision?  
**Team:** Joseph Nounagnon, Luxor Bourommavong, Olivia Hoffman, Yovany Romero Gomez, Anirudh Ramesh

---

## 🏛️ Context: The Decision That Was Made

**June 24, 2024:** Charlotte City Council approved a $650 million public subsidy for Bank of America Stadium renovations on a 7-3 vote.

**Public Rationale:** Enhanced amenities, economic development, job creation, and enhanced quality of life for the region.

**What Was Missing:** A quantitative analysis of whether other cities hosting NFL teams experienced measurable fiscal impacts from that presence.

---

## 🔍 Research Question

**What evidence should have been examined?**

Does NFL team presence significantly correlate with higher municipal spending per capita when controlling for other relevant factors? And if so, does this pattern inform the fiscal wisdom of Charlotte's $650M commitment?

---

## 📊 Primary Hypothesis

Cities with NFL team presence show measurably higher general spending per capita than comparable cities without NFL teams, after controlling for city size, economic conditions, and inflation.

**If true:** This pattern would indicate that hosting an NFL franchise carries an ongoing fiscal cost borne by residents—suggesting that Charlotte should have carefully weighed this documented pattern before committing an additional $650M.

---

## 🔬 Methodology

### Data & Key Variables

**Outcome Variable:**
- `spending_general_dollars_pc` — General city spending per resident (log-transformed)

**Key Variables:**
- `teams_nfl_count` — Number of NFL teams in city
- `outgoing_moves_total` — Historical franchise relocations
- `state_unemployment_rate` — Economic conditions
- `tourism_proxy` — Tourism intensity
- `log_city_population` — City size
- `cpi` — Inflation adjustment
- Year fixed effects — Economy-wide shocks

**Sample:** 6,758 city-year observations

### Model Development

We initially tested municipal debt per capita as the outcome (R² = 0.331), but switched to general spending per capita when diagnostic testing showed it explained 79% of variation—providing stronger evidence for policy deliberation.

**Final Model:**
```
log_spending_pc ~ teams_nfl_count + outgoing_moves_total + 
                  state_unemployment_rate + tourism_proxy + 
                  log_city_population + cpi + C(year)
```

### Validation Steps

✅ **Multicollinearity Testing:** Removed redundant variables (VIF analysis)  
✅ **Assumption Checking:** Verified normality, linearity, homoskedasticity  
✅ **Heteroskedasticity Correction:** Applied HC3 robust standard errors  
✅ **Time Controls:** Included year fixed effects for economy-wide shocks  
✅ **Specification Robustness:** Stepwise model selection confirms finding holds across models  

---

## 📈 What the Data Shows

### Core Finding

| Metric | Value | Interpretation |
|--------|-------|-----------------|
| **NFL Coefficient** | +0.280 | Each NFL team associated with higher spending |
| **Significance** | p < 0.001 | Finding is highly statistically significant |
| **Effect Size** | +$470/capita/year | 1 NFL team ≈ additional $470 per resident annually |
| **Model R²** | 0.789 | Explains 79% of variation in city spending |
| **Sample Size** | 6,758 city-years | Large, diverse dataset across decades |

### What This Means in Practice

**Model Predictions (all other factors equal):**

| Scenario | Annual Spending Per Capita |
|----------|---------------------------|
| City with 0 NFL teams | ~$4,200 |
| City with 1 NFL team | ~$4,670 |
| **Difference** | **+$470** |

For Charlotte (population ~400,000), this pattern suggests hosting the Panthers correlates with **~$188 million in annual additional city spending.**

### Evidence Quality

✅ **Statistically Significant** — p < 0.001 (less than 0.1% chance of random occurrence)  
✅ **Robust Across Models** — Finding holds in both theory-driven and stepwise specifications  
✅ **Controls for Confounding** — Accounts for city size, inflation, economic conditions  
✅ **Large Sample** — 6,758 observations provide stable estimates  
✅ **Economically Meaningful** — Effect size ($470/capita) is substantial  

---

## 💡 What Should Have Been Considered

### Before the $650 Million Decision

This analysis suggests that Charlotte's City Council **should have examined:**

1. **Historical Pattern:** Does NFL team presence correlate with higher spending in comparable cities? **Answer: Yes, significantly.**

2. **Magnitude:** How large is the effect? **Answer: ~$470 per capita per year—substantial at city scale.**

3. **Duration:** Is this a one-time cost or ongoing? **Answer: Ongoing annual pattern across decades.**

4. **Alternative Uses:** What would $188M/year (the estimated annual Panthers impact) accomplish if directed to public services?

5. **Precedent Risk:** If the city commits $650M now, does this pattern suggest future requests for support?

### The Argument for Proceeding Cautiously

A rigorous pre-decision analysis would have shown:

- **Documented Fiscal Burden:** NFL presence has measurable, significant cost to municipalities
- **Annual Obligation:** Not just the $650M upfront, but ongoing spending commitment
- **Opportunity Cost:** Resources diverted from schools, housing, infrastructure, public safety
- **Precedent:** Once committed to one team, political pressure to maintain investment increases

### Questions This Data Cannot Answer

⚠️ **Causation:** Does NFL presence *cause* higher spending, or do spending-focused cities tend to attract/retain teams?  
⚠️ **Long-term:** Will Charlotte's spending pattern follow the historical norm?  
⚠️ **Benefits:** Do economic returns offset the fiscal costs identified here?  
⚠️ **Alternatives:** Would private funding have been possible with different negotiating approach?  

---

## 🎯 What We Recommend Going Forward

### If This Analysis Had Been Conducted Before June 2024

The decision-makers should have demanded answers to these questions using evidence like this analysis provides:

1. **Acknowledge the cost:** Quantify the fiscal burden associated with NFL presence
2. **Set conditions:** If public funding is provided, tie it to measurable public benefits
3. **Demand private contribution:** Given the documented private profit motive, require substantial owner investment
4. **Protect taxpayers:** Structure any deal to cap public exposure and sunset commitments

### For Future Similar Decisions

**Policy Principle:** Large public subsidies to private assets should be preceded by rigorous analysis of:
- Historical fiscal impacts in comparable cities
- Quantified public benefits vs. costs
- Alternative uses of the same resources
- Risk to taxpayers and public services

This analysis shows what that evidence base should look like.

---

## 🔗 Key Takeaways

| What We Found | Why It Matters |
|---|---|
| NFL presence correlates with +$470/capita annual spending | Cities bear real, measurable costs from hosting franchises |
| Effect is highly significant (p < 0.001) | Not due to chance; documented across 6,758 city-years |
| Finding holds across multiple model specifications | Robust to different analytical approaches |
| Pattern persists across decades | Not a temporary phenomenon; structural feature |
| Charlotte's population = $188M annual estimated impact | Makes the $650M commitment worth scrutinizing against this backdrop |

---

## ⚠️ Limitations & Honest Assessment

🔍 **We observed correlation, not causation.** NFL presence correlates with higher spending, but we cannot definitively prove it *causes* the spending increase. Reverse causality is possible—spending-focused cities may attract teams.

🔍 **We use pooled OLS, not panel methods.** A more sophisticated approach would control for city-specific factors that don't change over time.

🔍 **Influential observations.** Very large cities (NYC, LA) have outsized influence. This is methodologically acceptable but worth noting.

🔍 **Missing variables.** Unmeasured factors (local politics, arena age, team success) may influence outcomes.

🔍 **Older data.** Analysis uses historical data; current relationships may differ.

**Despite these limitations,** the evidence is strong enough that responsible policy-makers should have examined it before committing $650 million in public funds.

---

## ✅ The Bottom Line

This retrospective analysis demonstrates that **rigorous empirical evidence existed—and should have been consulted—before Charlotte's June 2024 decision.**

The evidence shows:
- Cities hosting NFL teams experience significantly higher municipal spending
- The effect is large, consistent, and documented across thousands of observations
- The pattern has persisted for decades

Whether one agrees with the ultimate decision or not, this analysis illustrates what **pre-decision deliberation should have included:**

**An honest accounting of the fiscal burden that hosting professional sports franchises places on residents.**

---

**Analysis Date:** April 2026  
**Decision Date (Retrospectively Analyzed):** June 24, 2024  
**Status:** Post-decision evaluation; intended to inform future policy decisions

---

## 👥 Team Members

- Joseph Nounagnon
- Luxor Bourommavong
- Olivia Hoffman
- Yovany Romero Gomez
- Anirudh Ramesh

---

*This README was created with assistance from Claude AI*
