# Seasonal Agriculture Performance Analysis

**VOIS AICTE Batch 1 (2026–2027) — Major Project**
Author: Nachiket Ghalsasi | Electronics & Telecommunication Engineering, SFIT Mumbai

## Overview

Agricultural performance in India varies across the **Kharif, Rabi, and Zaid** seasons due to
differences in environmental conditions, resource use, and market conditions. This project analyzes
a seasonal agriculture performance dataset (4,000 farm records across 8 states and 8 crops) to
identify meaningful seasonal patterns, test whether observed differences are statistically
significant, and develop evidence-based insights for seasonal agricultural planning.

## Repository Contents

| File | Description |
|---|---|
| `analysis.ipynb` | Full analysis notebook — cleaning, EDA, statistical testing, visualizations, insights |
| `seasonal_agriculture_performance_dataset.csv` | Source dataset |
| `requirements.txt` | Python dependencies |

## Methodology

1. **Data cleaning** — season-wise median imputation for missing values, duplicate removal, IQR-based outlier capping on implausible yield/production values
2. **Feature engineering** — profit margin %, cost per tonne, profitability flag
3. **Exploratory analysis** — environmental conditions, resource usage, and economic performance compared across seasons, crops, and states
4. **Correlation analysis** — identifying the strongest drivers of yield and profit
5. **Statistical testing** — Kruskal-Wallis / ANOVA for seasonal differences in yield and profit, chi-square test for irrigation-method association, Pearson correlation for rainfall-yield relationship
6. **Segment analysis** — comparing profitable vs. loss-making farms to isolate what actually separates them

## Key Findings

- Yield and profit both vary significantly by season (Kruskal-Wallis, p < 0.001) — seasonal differences in this dataset are real, not random noise.
- **~49% of farms in the dataset operate at a loss**, regardless of season — profitability is not simply a seasonal problem.
- Loss-making and profitable farms differ most in **water efficiency** (~2.7 vs. ~8.0 tonnes per 1000 m³), a far larger gap than in rainfall, soil conditions, or fertilizer use — suggesting irrigation practice matters more than weather.
- Loss rates vary sharply by crop (Wheat ~74% vs. Sugarcane ~12%) and by irrigation method (Rainfed ~53% vs. Drip ~40%).

*(See the notebook's "Key Insights" section for the complete, numbers-grounded list.)*

## Setup & Running Locally

```bash
git clone https://github.com/ghalsasinachiket-creator/seasonal-agro-analysis.git
cd seasonal-agro-analysis

python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

pip install -r requirements.txt

code .   # open in VS Code, select the venv kernel, then Run All in analysis.ipynb
```

## Tech Stack

Python · pandas · numpy · matplotlib · seaborn · scipy (statistical testing)

## Acknowledgments

Dataset and problem statement provided as part of the VOIS AICTE Batch 1 (2026–2027) Data Analytics program.
