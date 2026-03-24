# Rural Transit Cost Efficiency: DRT vs Fixed-Route
**Transportation Economics Project | Spring 2026**
**Author: Sarah Mvuma**

## Overview
This repository contains the analysis code, cleaned dataset, and output figures 
for a study comparing the economic efficiency of demand-responsive transit (DRT) 
and fixed-route motor bus service in rural and low-density regions using National 
Transit Database (NTD) data (2018–2024).

## Research Question
At what ridership level does fixed-route motor bus service become more 
cost-efficient than demand-responsive transit in rural markets?

## Key Finding
The break-even ridership threshold — where predicted average cost per trip 
converges across modes — is estimated at **1,240 annual passenger trips**. 
The median rural DR agency serves approximately 18,857 trips annually, 
well above this threshold, suggesting most rural agencies operating DRT 
may be doing so at a cost disadvantage relative to fixed-route service.

## Data Source
Federal Transit Administration — National Transit Database (NTD)  
Annual mode-level data, 2018–2024  
Download from: https://www.transit.dot.gov/ntd/ntd-data

**Files downloaded for each year (2018–2024):**
- Annual Database — Service Data
- Annual Database — Operating Expenses
- Annual Database — Fare Revenues

**To replicate:** Go to the NTD data page, select each year, check Service, 
Operating Expenses, and Fare Revenues, and download the Excel files. 
Place them in the same folder as the notebooks before running.

## Sample Description
| Item | Value |
|---|---|
| Years covered | 2018–2024 |
| Reporting module | Rural only |
| Modes included | Motor Bus (MB) and Demand Response (DR) |
| Agency–mode–year observations | 4,266 |
| Unique agencies | 451 |
| States represented | 38 |
| Main sample (excl. COVID years) | DR: 1,546 obs / MB: 1,507 obs |

## Variables Used
| Variable | Definition |
|---|---|
| UPT | Unlinked Passenger Trips — passenger output |
| VRH | Vehicle Revenue Hours — service supply |
| VRM | Vehicle Revenue Miles — supplementary supply |
| OE | Total Operating Expenses |
| Fare | Passenger Fare Revenue |
| AC | Average Cost per Trip (OE / UPT) |
| Cost_per_VRH | Cost per Revenue Hour (OE / VRH) |
| Productivity | Trips per Revenue Hour (UPT / VRH) |
| Subsidy_per_trip | Net public cost per trip (OE − Fare) / UPT |
| Farebox_recovery | Share of cost covered by fares (Fare / OE) |

## Repository Contents
| File | Description |
|---|---|
| `ntd_panel_builder.ipynb` | Data pipeline: loads, filters, merges, and cleans all NTD files into a 7-year panel |
| `ntd_panel_2018_2024.csv` | Final cleaned panel dataset — ready to run analysis on |
| `ntd_exploratory_plots.png` | Boxplots and log-log scatterplots by mode (2024) |
| `ntd_trends_2018_2024.png` | Time-series of median economic metrics by mode, 2018–2024 |
| `ntd_agency_map.png` | Geographic distribution of agencies in sample |

## How to Run
1. Download the raw NTD files as described above
2. Place them in the same folder as the notebooks
3. Run notebooks in this order:
   - `ntd_panel_builder.ipynb` — generates `ntd_panel_2018_2024.csv`
   - `ntd_regression_breakeven.ipynb` — runs all regressions
   - `ntd_fe_stats_map.ipynb` — generates fixed effects results and map

## Methods Summary
- **Cost-function framework:** Log-linear OLS, estimated separately by mode
- **Regression A:** ln(OE) ~ ln(VRH) + Year FE — supply-side scale elasticity
- **Regression B:** ln(AC) ~ ln(UPT) + Year FE — average cost scale elasticity
- **Agency FE specification:** Within-estimator robustness check
- **COVID robustness:** Full 2018–2024 sample with pandemic indicator variable
- **Break-even derivation:** Analytical solution from estimated coefficients
