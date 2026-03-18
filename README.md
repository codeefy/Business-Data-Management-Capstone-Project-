<div align="center">

# 🌶️ Mahak Spices — Operational Efficiency Study

### BDM Capstone Project · Indian Institue of Information Technology Lucknow

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Excel](https://img.shields.io/badge/Microsoft-Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)](https://www.microsoft.com/excel)

> *A data-driven investigation into inventory, logistics, and spoilage challenges at a B2B spice trading company in Shahjahanpur, Uttar Pradesh.*

---

**Submitted by:** Rohit Raj &nbsp;|&nbsp; **Roll No:** MSE25004 &nbsp;|&nbsp; **Period:** Sept 2025 – Dec 2025

</div>

---
## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statements](#-problem-statements)
- [Methodology & Workflow](#-methodology--workflow)
- [Dataset Structure](#-dataset-structure)
- [Key Findings](#-key-findings)
- [ABC Classification](#-abc-classification)
- [Seasonal Trends](#-seasonal-trends)
- [Transport Analysis](#-transport-analysis)
- [Recommendations](#-recommendations)
- [Repository Structure](#-repository-structure)
- [Tools Used](#-tools-used)

---
## 🏢 Project Overview

**Mahak Spices** is a B2B wholesale spice trading business,supplying a wide variety of spices to local retailers and small businesses.

Despite its strong local presence, three key operational challenges limit the company's profitability and long-term scalability:

```
┌─────────────────────────────────────────────────────────────┐
│               THREE CORE OPERATIONAL CHALLENGES             │
├─────────────────┬──────────────────┬────────────────────────┤
│📦 Overdependence │ 🚛 Transport Costs │ ☀️ Summer Spoilage│
│  on few spices   │   fluctuating    │   of Red Chilli       │
└─────────────────┴──────────────────┴────────────────────────┘
```

---
## 🎯 Problem Statements

| # | Problem | Impact |
|---|---------|--------|
| 1 | **Overdependence on Turmeric & Red Chilli** (~76% of revenue) | Revenue risk, idle inventory for slow-movers |
| 2 | **Fluctuating Transportation Costs** (₹0 – ₹331/day, mean ₹103) | Unpredictable margins, no logistics baseline |
| 3 | **Spice Spoilage in Summer (Mar–Apr)** | Sharp Red Chilli sales drop, direct profit loss |

---
## 🔬 Methodology & Workflow

```mermaid
flowchart TD
    A([🏬 Mahak Spices\nDaily Operations]) --> B[📥 Data Collection\nNov 2024 – Apr 2025]
    B --> B1[Daily Sales & Purchases]
    B --> B2[Quantity Sold per Spice]
    B --> B3[Cost per kg per Day]
    B --> B4[Daily Transport Costs]

    B1 & B2 & B3 & B4 --> C[🧹 Data Cleaning\nin Microsoft Excel]
    C --> C1[Replace missing values with 0]
    C --> C2[Standardise column headers]
    C --> C3[Remove duplicates & anomalies]
    C --> C4[Fix data types: date, currency, number]

    C1 & C2 & C3 & C4 --> D[⚙️ Feature Engineering]
    D --> D1["Revenue = Qty × Selling Price"]
    D --> D2["Profit = Revenue − Cost"]
    D --> D3["Total Daily Profit = Σ Profits"]

    D1 & D2 & D3 --> E[📊 Analysis in Python]

    E --> F1[📐 Descriptive Statistics\nMean · Median · Std Dev · Skewness]
    E --> F2[🔗 Correlation Analysis\nPearson Coefficient · Heatmaps]
    E --> F3[🏷️ ABC Classification\nPareto / Revenue Ranking]
    E --> F4[📅 Trend & Seasonal Analysis\nMonthly Line Charts]
    E --> F5[🚛 Transport Cost Analysis\nScatter Plots · Monthly Breakdown]

    F1 & F2 & F3 & F4 & F5 --> G[💡 Insights & Recommendations]

    style A fill:#8B0000,color:#fff
    style G fill:#2d6a4f,color:#fff
    style E fill:#1d3557,color:#fff
```

---
