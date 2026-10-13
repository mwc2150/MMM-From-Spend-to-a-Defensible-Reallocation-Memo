# MMM: From Spend to a Defensible Reallocation Memo

Marketing mix modeling (MMM) homework for **GLUCOREN**, built for *Applied Data Science and AI in Pharma Commercial* (Columbia University, Fall 2026). The goal is to turn weekly spend and prescription data into a budget reallocation recommendation that a brand lead can act on and a quantitative reviewer can defend.

**Author:** Michael Chen

## What's here

```
Data/
  glucoren_weekly_mmm.csv          156 weeks of national TRx, channel spend, and controls
  glucoren_geo_lift_dtc_tv.csv     Geo holdout (difference-in-differences) for DTC TV
Deliverables/
  Homework1_Chen.ipynb             Full analysis, Parts A-E
  Homework1_Chen_PartE.ipynb       Part E (the memo) on its own
  Homework1_Memo_Chen.pdf          Part E rendered as a PDF
  output.png                       TRx decomposition chart used in the memo
```

## Approach

| Part | Topic |
|---|---|
| A | EDA and controls: logistic launch ramp (chosen by AIC), seasonality, formulary access / PBM controls |
| B | Geometric adstock and Hill saturation, with per-channel decay ranges |
| C | OLS MMM, grid search over decay and half-saturation by AIC, diagnostics (VIF, residuals), 104/52-week hold-out |
| D | Decomposition, average and marginal ROI, moving-block bootstrap ranges, calibration against the geo holdout |
| E | Reallocation memo: what to cut and grow on a fixed budget in conservative and aggressive postures, what the model misses, and a costed experiment |

Channels modeled: HCP detailing, conferences, digital, email, and DTC TV.

## Headline results

- Base accounts for about 61% of TRx; media accounts for about 39%, led by digital and detailing.
- Cut conferences and TV; grow email and detailing.
- Expected lift on a fixed total budget is about +2.4% (conservative) to +3.7% (aggressive), each with an 80% range.
- The least certain number is the detailing ROI, which is confounded with the launch ramp, PBM share, and digital through a shared time trend.

See the Part E memo for the full reasoning and the proposed detailing holdout experiment.

## Running it

Open `Deliverables/Homework1_Chen.ipynb` in Jupyter or VS Code. The notebook expects `Data/` one level up from `Deliverables/` and uses numpy, pandas, matplotlib, scipy, and statsmodels.

## AI usage

Claude (Claude Code in VS Code) was used as a debugging and explanation aid, and to split Part E into its own notebook and PDF. The memo writing is the author's own. A fuller disclosure is at the end of `Homework1_Chen.ipynb`.
