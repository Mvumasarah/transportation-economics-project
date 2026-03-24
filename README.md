# Rural Transit Cost Efficiency: DRT vs Fixed-Route
**Transportation Economics Project | Spring 2026**

## Overview
This repository contains the analysis code and output figures for a study comparing 
the economic efficiency of demand-responsive transit (DRT) and fixed-route motor bus 
service in rural and low-density regions using National Transit Database (NTD) data.

## Data Source
Federal Transit Administration — National Transit Database (NTD)
Annual mode-level data, 2018–2024
Downloaded from: https://www.transit.dot.gov/ntd/ntd-data

## Sample
- 4,266 agency–mode–year observations
- 451 unique rural agencies
- 38 states
- Modes: Motor Bus (MB) and Demand Response (DR)

## Notebooks
| Notebook | Description |
|---|---|
| ntd_panel_builder.ipynb | Data pipeline: loads, filters, merges, and cleans NTD files |
| ntd_regression_breakeven.ipynb | Regression A, Regression B, break-even threshold, COVID robustness |
| ntd_fe_stats_map.ipynb | Agency fixed effects, descriptive statistics table, geographic map |

## Key Finding
The break-even ridership threshold — where predicted average cost per trip 
converges across modes — is estimated at **1,240 annual passenger trips**. 
The median rural DR agency serves approximately 18,857 trips annually, 
well above this threshold.
