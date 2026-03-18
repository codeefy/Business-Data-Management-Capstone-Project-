# 📊 BDM Capstone Project  
### *Studying and Enhancing Operational Efficiency at Mahak Spices Company*  

## 📌 Project Overview  
Mahak Spices, a **B2B wholesale spice trading company**  supplies high-quality spices to local retailers and businesses. Despite its strong local presence, the business faces operational challenges that limit profitability and scalability.  

This project applies **data analytics** to study these inefficiencies and proposes **data-driven strategies** to enhance operational efficiency and ensure sustainable growth. 


## 🎯 Objectives (Problem Statements)  
1. **Overdependence on Few Spices**  
   - Heavy reliance on Turmeric and Red Chilli (~76% of revenue).  
   - Poor performance of other spices leading to overstocking and wastage.  

2. **Fluctuating Transportation Costs**  
   - Inconsistent logistics expenses due to third-party vendors and poor route planning.  
   - High unpredictability in profit margins.  

3. **Spice Spoilage in Summer Months**  
   - Red Chilli highly perishable; sales drop sharply during March–April due to heat-related spoilage.  

---
## 🔬 Methodology  

### 1. Data Collection  
- Daily transactional data (Nov 2024 – Apr 2025):  
  - Sales & purchases  
  - Quantity sold per spice  
  - Cost per kg  
  - Daily transport costs  

### 2. Data Cleaning & Structuring  
- Missing values replaced with zero  
- Standardized column headers & formats  
- Duplicate/incorrect entries removed  
- Feature engineering: Revenue, Profit, Total Daily Profit  

### 3. Analysis Techniques  
- **Descriptive Statistics:** Mean, Std. Deviation, Skewness  
- **Correlation Analysis:** Heatmaps & Pearson coefficients  
- **ABC Classification:** Categorizing spices into A (high), B (moderate), C (low) revenue groups  
- **Trend & Seasonality Analysis:** Monthly sales line charts  
- **Profitability & Transport Analysis:** Scatter plots, monthly breakdown  

### 4. Tools Used  
- **Excel:** Data cleaning, structuring, initial calculations  
- **Python (Pandas, Matplotlib, Seaborn):** Statistical analysis, advanced visualizations  

---
## 📈 Key Findings  

1. **Product Performance**  
   - Turmeric (42.4%) & Red Chilli (33.3%) dominate revenue.  
   - Dhaniya (15.5%) shows potential for growth.  
   - Cumin, Ajwain & Fennel contribute minimally.  

2. **Seasonal Trends**  
   - Turmeric: Steady growth, consistent demand.  
   - Red Chilli: Strong until February, sharp decline in March–April due to spoilage.  
   - Dhaniya: Seasonal surge in March–April.  
   - Cumin: One-time spike in January (bulk order).  

3. **Transport Cost Analysis**  
   - Positive correlation between sales & transport cost (esp. Turmeric).  
   - March saw **highest transport cost**, indicating inefficiencies.  
   - Costs fluctuate widely (₹0 – ₹331).  

4. **Profitability Trends**  
   - November → Highest profit (₹1,00,000+).  
   - December → Lowest due to seasonal dip.  
   - Recovery in Jan–Feb; decline again in Mar–Apr due to spoilage  
