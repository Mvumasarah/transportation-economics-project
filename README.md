# Rural Transit Cost Efficiency: DRT vs Fixed-Route
**Transportation Economics Project | Spring 2026**
**Author: Sarah Mvuma**

## Overview
This repository contains the analysis code, cleaned dataset, and output figures 
for a study comparing the economic efficiency of demand-responsive transit (DRT) 
and fixed-route motor bus service in rural and low-density regions using National 
Transit Database (NTD) data (2018-2024).  

## Project Objective
This study investigates the economic efficiency of two predominant transit 
service types in rural and low-density markets: demand-responsive transit (DRT) 
and fixed-route motor bus (MB) service. While DRT is widely deployed in rural 
areas to improve geographic coverage and serve dispersed populations, national 
data consistently show that it operates at substantially higher cost per 
passenger trip than fixed-route service.

Using a seven-year panel of rural National Transit Database reporters (2018–2024), 
this study applies a cost-function econometric framework to:

1. Estimate and compare scale elasticities for each mode - measuring how 
   average cost responds to changes in ridership
2. Identify the ridership threshold at which fixed-route service becomes 
   more cost-efficient than demand-responsive service on a per-trip basis
3. Assess the robustness of these findings to agency-level heterogeneity 
   and COVID-19 pandemic disruptions

The central contribution is the derivation of a break-even productivity 
threshold - the annual ridership level at which predicted average cost per 
trip converges across modes - which provides actionable guidance for rural 
transit agencies and state departments of transportation allocating limited 
operating subsidies.

## Research Question
At what ridership level does fixed-route motor bus service become more 
cost-efficient than demand-responsive transit in rural markets?

## Key Finding
The break-even ridership threshold, where predicted average cost per trip 
converges across modes.

## Data Source
Federal Transit Administration - National Transit Database (NTD)  
Annual mode-level data, 2018-2024  
Download from: https://www.transit.dot.gov/ntd/ntd-data

**Files downloaded for each year (2018-2024):**
- Annual Database - Service Data
- Annual Database - Operating Expenses
- Annual Database - Fare Revenues

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
| `table1_descriptive_stats.csv` | Descriptive statistics |

## How to Run
1. Download the raw NTD files as described above
2. Place them in the same folder as the notebooks
3. Run notebook

## Methods Summary

