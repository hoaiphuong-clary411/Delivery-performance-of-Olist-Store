# 📦 Delivery Performance Analytics — Olist Store
*A tactical analytics solution delivering root‑cause insights into delivery failures across time, geography, and product segments using Power BI and a Galaxy Schema data model.*

---

## 🔍 Executive Summary
This project provides a comprehensive delivery performance assessment for Olist Store (Brazil), leveraging a 100K‑order dataset (2016–2018).  
The analysis identifies operational bottlenecks, quantifies the revenue impact of late deliveries, and provides data‑driven recommendations for optimizing logistics capacity.

The dashboard is designed as a tactical decision‑support tool for operations managers and analysts, focusing on:
- Performance anomalies  
- Operational inefficiencies  
- Risk concentration  
- Actionable interventions backed by data  

---

## 🧩 Business Context
Olist is a marketplace platform connecting SMBs across Brazil with customers nationwide.  
Between 2016 and 2018, rapid customer acquisition created delivery‑pressure spikes that resulted in:
- Increased late‑delivery rate  
- Reduced customer satisfaction  
- Higher logistics costs  
- Regional performance inconsistencies  

This project answers three central questions:
1. **What happened?**  
2. **Why did it happen?**  
3. **What should Olist do next?**

---


## 📅 Dataset Overview
- **Source:** [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Timeframe:** 2016–2018  
- **Size:** ~100,000 orders  
- **Tables:** Customers, Sellers, Orders Status, Order Items, Products, Geolocation


---

## 🛠️ Technical Stack
- **Power BI** — Data modeling, DAX, dashboarding  
- **Power Query** — ETL, transformation  
- **Excel** — Exploratory analysis  
- **DAX** — KPI measures & delivery logic  

---

## 🧱 Data Modeling Architecture (Galaxy Schema)

### Entity‑Relationship Diagram
*(Replace the image path with your actual folder name — for example: images/er_diagram.png)*

flowchart LR
  %% Olist Data Model (2016–2018)
  subgraph Core
    ORD[(olist_orders_dataset)]
    OI[(olist_order_items_dataset)]
    REV[(olist_order_reviews_dataset)]
    PAY[(olist_order_payments_dataset)]
  end

  PROD[(olist_products_dataset)]
  SELL[(olist_sellers_dataset)]
  CUST[(olist_customers_dataset)]
  GEO[(olist_geolocation_dataset)]

  %% Relationships
  ORD <-- order_id --> REV
  ORD <-- order_id --> PAY
  ORD <-- customer_id --> CUST

  ORD -- order_id --> OI
  OI -- product_id --> PROD
  OI -- seller_id --> SELL

  CUST -- zip_code_prefix --> GEO
  SELL -- zip_code_prefix --> GEO

  %% Styling (optional)
  classDef table fill:#fff,stroke:#bbb,stroke-width:1px,color:#333;
  class ORD,OI,REV,PAY,PROD,SELL,CUST,GEO table;


---

## 📊 Analytical Framework

### 1. Time Analysis
- Late‑delivery trends  
- Seasonality insights (rainfall season, holidays, Black Friday)  
- Weekend and weekday differences  
- Correlation between revenue surges & operational strain  

### 2. Geography Analysis
- State‑level delivery performance  
- Distance segmentation 
- Coastal vs inland operational risks  
- Weather‑driven & infrastructure‑driven patterns  

### 3. Product Analysis
- Volumetric weight vs delivery performance  
- Category‑level performance segmentation  
- Revenue concentration mapping  

---

## 💡 Key Insights

### Time
- Late deliveries peaked during weekends & rainfall season (Nov–May).  
- April 2018 recorded the highest late‑delivery rate despite high demand.  
- Operational delays strongly correlate with revenue spikes.

### Geography
- 0–1k km routes generate **80.46% of revenue** but show the highest late‑day ratios of 40.14%.  
- Coastal cities demonstrate higher weather‑related disruption risk.  
- Three states (São Paulo, Rio de Janeiro, Minas Gerais) contribute **62.74% of total revenue** with **a late-delivery rate of around 7.69%**.

### Product
- Higher volumetric weight → higher probability of late delivery.  
- Two priority clusters identified for logistics optimization.

---

## 🚀 Recommendations

### Customer Experience
- Provide flexible delivery window options  
- Enable proactive notifications during peak weather months  

### Internal Operations
- Enhance ETA forecasting with weather data  
- Reallocate labor during seasonal spikes  
- Optimize warehouse flow for short‑distance deliveries  

### Logistics Partners
- Prioritize top‑3 revenue states with capacity allocation  
- Implement performance scorecards for partners  
- Assign dedicated trucks for bulky / high‑volumetric shipments  

---

## 🖼️ Report Preview

*(Upload your own images into `/images/` and replace file names)*


---

## 📥 Download PBIX File
The full Power BI report (.pbix) is available under **GitHub Releases**:

👉 https://github.com/hoai­­phuong-clary411/Delivery-performance-of-Olist-Store/releases  

---

## 👩‍💻 About Me
**Nguyễn Hoài Phương** — Data Analyst 
- Power BI · DAX · Data Modeling  
- Excel & VBA Automation  
- Supply Chain & Logistics Analytics  

📫 Contact  
- Email: hoaiphuong411hp@gmail.com 
