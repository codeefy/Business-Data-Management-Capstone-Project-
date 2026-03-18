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
## 🗄️ Dataset Structure

The dataset spans **129 business days** (Nov 2024 – Apr 2025) with the following schema:

| Column | Type | Description |
|--------|------|-------------|
| `Date` | datetime | Business day |
| `Turmeric_sold(kg)` | float | Daily quantity sold (kg) |
| `RedChilli_sold(kg)` | float | Daily quantity sold (kg) |
| `Dhaniya_sold(kg)` | float | Daily quantity sold (kg) |
| `CarmonSeeds(Ajwain)_sold(kg)` | float | Daily quantity sold (kg) |
| `Cumin(Jeera)_sold` | float | Daily quantity sold (kg) |
| `Fennel(Sauf)_sold` | float | Daily quantity sold (kg) |
| `*_cost_per_kg` | float | Purchase cost per kg for each spice |
| `*_revenue` | float | Daily revenue per spice (qty × selling price) |
| `Total_Sales` | float | Sum of all spice revenues per day |
| `Total_Purchase` | float | Sum of all purchase costs per day |
| `Total_Profit` | float | Total_Sales − Total_Purchase |
| `Transport` | float | Daily logistics cost (₹) |

---
## 📈 Key Findings

### Revenue Distribution

```
Turmeric     ████████████████████░░░░░░░░░░░░░░  42.4%  (~₹9,00,000)
Red Chilli   ████████████████░░░░░░░░░░░░░░░░░░  33.3%  (~₹7,06,840)
Dhaniya      ███████░░░░░░░░░░░░░░░░░░░░░░░░░░░  15.5%  (~₹3,29,009)
Cumin        ███░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   6.0%  (~₹1,27,358)
Ajwain       █░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   2.1%  (~₹44,575)
Fennel       ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0.8%  (~₹16,981)
```

> ⚠️ **Turmeric + Red Chilli = 75.7% of total revenue** — a significant concentration risk.

---
## 🏷️ ABC Classification

```mermaid
graph LR
    subgraph A ["🔵 Category A — High Value (top 80% revenue)"]
        T["🌿 Turmeric\n₹9,00,000 · 42.4%"]
        R["🌶️ Red Chilli\n₹7,06,840 · 33.3%"]
    end

    subgraph B ["🟡 Category B — Moderate Value (next 15%)"]
        D["🌱 Dhaniya\n₹3,29,009 · 15.5%"]
    end

    subgraph C ["🔴 Category C — Low Value (bottom 5%)"]
        Cu["🫙 Cumin · 6%"]
        Aj["🫙 Ajwain · 2.1%"]
        Fe["🫙 Fennel · 0.8%"]
    end

    style A fill:#dbeafe,stroke:#1d4ed8
    style B fill:#fef9c3,stroke:#ca8a04
    style C fill:#fee2e2,stroke:#dc2626
```

**Action by category:**
- **Category A** → Prioritise stock, monitor supply chain closely, cold storage for Red Chilli
- **Category B** → Targeted seasonal promotions, increase visibility to push toward Category A
- **Category C** → Reduce stock levels, explore bundling with A/B items, reassess pricing

---
## 📅 Seasonal Trends

```mermaid
xychart-beta
    title "Monthly Sales Trend by Spice (Quantity Sold kg)"
    x-axis [Nov, Dec, Jan, Feb, Mar, Apr]
    y-axis "Quantity Sold (kg)" 0 --> 1500
    line [882, 1022, 1178, 1211, 1244, 1384]
    line [987, 1126, 1287, 1364, 523, 365]
    line [601, 539, 543, 541, 1021, 1139]
```

| Spice | Trend | Key Insight |
|-------|-------|-------------|
| 🌿 **Turmeric** | 📈 Steady upward growth | Cornerstone product — consistent demand throughout |
| 🌶️ **Red Chilli** | 📈 Peak Feb → 📉 Sharp crash Mar–Apr | Summer spoilage; needs cold storage & reduced summer stocking |
| 🌱 **Dhaniya** | 📉 Dips till Jan → 📈 Strong rise Mar–Apr | Seasonal/festive demand surge — opportunity for promotions |
| 🫙 **Cumin** | Flat with **spike in January** | Likely a bulk/festival order — investigate to replicate |
| 🫙 **Ajwain & Fennel** | Consistently lowest | Reassess inventory levels; candidate for bundling |

---
## 🚛 Transport Analysis

```mermaid
flowchart LR
    A[📦 High Turmeric Sales] -->|strongest driver\ncorr = 0.52| T[🚛 Transport Cost ₹]
    B[🌶️ Red Chilli Sales] -->|moderate driver\ncorr = 0.34| T
    C[🌱 Dhaniya Sales] -->|moderate driver\ncorr = 0.35| T
    D[🫙 Cumin · Ajwain · Fennel] -->|near zero / weak| T

    T --> S[📊 Key Statistics]
    S --> S1["Mean: ₹102.96/day"]
    S --> S2["Median: ₹105.50/day"]
    S --> S3["Range: ₹0 – ₹331"]
    S --> S4["Highest Month: March 🔺"]

    style T fill:#f59e0b,color:#fff
    style S fill:#1d3557,color:#fff
```

**Transport cost pattern by month:**

| Month | Observation |
|-------|------------|
| Nov | Elevated — high season activity |
| Dec–Jan | Moderate |
| Feb | Rising trend begins |
| **Mar** | **Highest transport cost** — operational inefficiency at peak |
| Apr | Slight decline |

---
## 💡 Recommendations

```mermaid
flowchart TD
    P1[📦 Problem 1\nOverdependence] --> R1A[🎁 Bundle slow spices\nwith Turmeric / Red Chilli]
    P1 --> R1B[📢 Targeted marketing\nfor Dhaniya in Mar–Apr]
    P1 --> R1C[📊 Track emerging demand\nwith monthly trend review]

    P2[🚛 Problem 2\nFluctuating Transport] --> R2A[📝 Long-term vendor\ncontracts with fixed rates]
    P2 --> R2B[🗺️ Route optimisation\nGoogle Maps · Routific]
    P2 --> R2C[📏 Define Transport KPIs\ncost/kg · cost/order]

    P3[☀️ Problem 3\nSummer Spoilage] --> R3A[❄️ Temperature-controlled\nstorage & insulated bags]
    P3 --> R3B[📉 Reduce Red Chilli orders\nin Mar–Apr using forecasting]
    P3 --> R3C[🏷️ Dynamic pricing for\nnear-expiry stock]

    style P1 fill:#1d3557,color:#fff
    style P2 fill:#1d3557,color:#fff
    style P3 fill:#1d3557,color:#fff
    style R1A fill:#2d6a4f,color:#fff
    style R1B fill:#2d6a4f,color:#fff
    style R1C fill:#2d6a4f,color:#fff
    style R2A fill:#2d6a4f,color:#fff
    style R2B fill:#2d6a4f,color:#fff
    style R2C fill:#2d6a4f,color:#fff
    style R3A fill:#2d6a4f,color:#fff
    style R3B fill:#2d6a4f,color:#fff
    style R3C fill:#2d6a4f,color:#fff
```

---


