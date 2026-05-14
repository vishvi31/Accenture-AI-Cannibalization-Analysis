# 🤖 Accenture AI Cannibalization Analysis

> *"We must build the technology that destroys our way of making money — or someone else will do it for us."*

## The Paradox

Accenture's core business model is selling human expertise by the hour. But what happens when the world's leading technology consultancy starts automating the very services it bills clients for?

Revenue goes down. Salaries are saved. But did you actually win?

This project quantifies that tension — the **AI Cannibalization Paradox** — by analysing which service lines are most at risk when automation potential increases, and whether the cost savings justify the revenue lost.

---

## Project Overview

| | |
|---|---|
| **Domain** | IT Consulting / Professional Services |
| **Company** | Accenture (Synthetic Public Financial Data) |
| **Techniques** | Revenue Impact Modelling · K-Means Clustering · Random Forest Regression · Scenario Analysis |
| **Tools** | Python · Pandas · Scikit-learn · Matplotlib · Seaborn |
| **Author** | Vishvi |

---

## Dataset

Synthetic dataset inspired by Accenture's public annual reports and service portfolio disclosures. 

**800 records · 6 features**

| Column | Description |
|---|---|
| `Service_Line` | Type of consulting service (e.g., Cloud Migration, Legacy ERP Maintenance) |
| `Year` | Fiscal year (2024–2026) |
| `Hourly_Rate_USD` | Billing rate per hour (USD) |
| `Automation_Potential` | 0–1 score representing AI replaceability of the service |
| `Hours_Billed` | Adjusted hours billed (decreases as automation increases) |
| `Revenue` | `Hours_Billed × Hourly_Rate_USD` |

**Key design logic:** `Hours_Billed` is reduced proportionally as `Automation_Potential` rises, simulating real cannibalization behaviour.

---

## Analysis Pipeline

### 1. Revenue Impact Modelling
A **Random Forest Regressor** was trained to predict revenue from service features. A scenario was then run: *What if automation potential increased by 20% across all service lines?*

The model outputs the projected revenue delta — the financial cost of automating your own workforce.

### 2. K-Means Clustering (3 Clusters)
Services were segmented by `Automation_Potential` and `Hourly_Rate_USD` to identify distinct risk portfolios:

| Cluster | Profile | Strategic Implication |
|---|---|---|
| **At-Risk** | Low-margin + high automation potential | Highest cannibalization exposure |
| **Efficiency Gains** | Mid-range services partially automated | Optimisation opportunity |
| **High-Value** | Premium rates sustained despite AI integration | Reskilling roadmap — protect and grow |

### 3. Scenario Analysis
Projected revenue impact of a 20% increase in automation potential across the test set, quantifying the exact revenue Accenture would "eat" by accelerating AI adoption.

---

## Key Findings

- As `Automation_Potential` increases, `Hours_Billed` decreases — revenue compression is real and measurable.
- **Cluster 1** (At-Risk) represents the highest cannibalization zone: services with high automation potential but low hourly rates offer minimal financial cushion.
- **Cluster 2** (High-Value) reveals where Accenture successfully commands premium pricing even after AI integration — the blueprint for value-based pricing and upstream ROI.
- The 20% automation scenario quantifies the exact breakeven point: when does salary savings outweigh lost billing revenue?

---

## Visualisations

### Chart 1 — The Cannibalization Effect
![The Cannibalization Effect](<img width="2591" height="1644" alt="Accenture_Risk_Chart" src="https://github.com/user-attachments/assets/09385166-d4ec-4695-b326-b2dfc91dce27" />
)
*As automation potential increases, revenue compresses. The red trend line makes the trade-off impossible to ignore.*

---

## Business Concepts Applied

- **Managed Services** — recurring, outcome-based service delivery replacing traditional time-and-materials billing
- **Value-Based Pricing** — charging for outcomes, not hours; insulates revenue from automation erosion
- **Upstream ROI** — investing in high-complexity, strategic services that AI cannot easily replicate

---

## Repository Structure

```
├── Accenture-AI-Cannibalization-Analysis.ipynb      # Full analysis notebook
├── chart1_cannibalization_effect.png                # Revenue vs Automation scatter + trend
├── chart2_service_portfolio_clusters.png            # K-Means cluster portfolio map
├── chart3_revenue_by_service_line.png               # Revenue by service line (coloured by cluster)
└── README.md
```

---

## Notebook link:
[Accenture-AI-Cannibalization-Analysis.ipynb](https://github.com/user-attachments/files/27742957/Accenture-AI-Cannibalization-Analysis.ipynb)

## How to Run

```bash
# Clone the repository
git clone https://github.com/vishvi31/accenture-ai-cannibalization-analysis.git
cd accenture-ai-cannibalization-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Open the notebook
jupyter notebook Accenture-AI-Cannibalization-Analysis.ipynb
```

---

*Built with Python · Jupyter Notebook · Scikit-learn*
