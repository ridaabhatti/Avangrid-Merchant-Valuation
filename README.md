# Avangrid Merchant Renewable Valuation – P75 Risk Model
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<yourusername>/avangrid-merchant-valuation/blob/main/Avangrid_P75_RenewableValuation.ipynb)

## Overview
This project builds a transparent, data-driven valuation framework for renewable assets whose PPAs have expired. It estimates risk-adjusted fixed prices (P75) where the hedge has a 75% probability of outperforming merchant market revenues.

## Assets Modeled
- ERCOT Wind (sample dataset)
- Framework extendable to MISO and CAISO markets

## Valuation Period
2026–2030 (5 years)

## Model Outputs
- Expected generation by month (Peak and Off-Peak)
- Four fixed prices ($/MWh) for each asset:
  - Real-Time Hub-settled
  - Real-Time Busbar-settled
  - Day-Ahead Hub-settled
  - Day-Ahead Busbar-settled
- Price breakdown includes:
  - Hub forward price
  - Historical basis adjustment
  - P75 risk adjustment

## Methodology
1. Integrated 3 years of hourly generation and price data.
2. Simulated hourly generation and basis spreads via Monte Carlo.
3. Applied hub forward prices to create 5-year (2026–2030) revenue paths.
4. Calculated P75 prices as the 25th percentile of merchant outcomes.
5. Aggregated results monthly for expected generation and fixed prices.

## Assumptions
- Historical generation and basis patterns represent future risk.
- Flat hub forward prices (can be adjusted).
- Discount rate = 0 (nominal $/MWh).
- Risk appetite = P75 (configurable to P50, P90).
- Ignores Capex, O&M, and REC values per prompt.

## How to Run
**Option 1 – Colab:**  
Click the “Open in Colab” button above and run all cells.  
Upload `HackathonDataset_ERCOT.csv` when prompted.

**Option 2 – Local:**  
Clone this repo and install packages:
