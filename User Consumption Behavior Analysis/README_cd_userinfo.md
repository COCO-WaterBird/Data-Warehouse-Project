# 🧠 CDNOW Customer Behavior Analysis
*Data-driven insights on customer purchasing patterns and lifecycle management*

## 📘 Overview
This project analyzes **CDNOW transactional data (Jan 1997 – Jun 1998)** containing ~70K purchase records from 23K unique users.  
The goal is to extract **customer behavior insights** and **business intelligence patterns** through data cleaning, aggregation, and visualization — supporting **strategic decision-making** for marketing, retention, and product planning.

**Target Roles:**  
- 🎯 Business Analyst (BA): Market segmentation, customer lifecycle analysis  
- ⚙️ Data Engineer (DE): Data preprocessing, ETL, and transformation pipeline  
- 📊 Product Manager (PM): Data-driven user retention and revenue strategies  

## 🧩 Dataset Description
| Column | Description |
|:--------|:-------------|
| `user_id` | Unique customer identifier |
| `order_dt` | Order date (YYYYMMDD) |
| `order_products` | Number of products purchased |
| `order_amount` | Total order value (USD) |

**Data Summary:**
- 69,659 total transactions  
- 23,570 unique customers  
- Mean order value ≈ $36  
- Mean quantity ≈ 2.4 products/order  

## 🧹 Data Processing & Transformation
- Converted `order_dt` to datetime format → new column `order_date`
- Extracted monthly period → `month`
- Aggregated user-level metrics:
  - Total purchases, total spending, last purchase date
- Built monthly cohorts using **pivot tables**
- Standardized variables for **RFM modeling**

## 📈 Trend & Behavioral Insights
### 1. **Monthly Trends**
![Monthly Purchase Amount](images/monthly_amount.png)
- Sales volume and revenue **peaked in Q1 1997**, followed by stabilization.
- Customer count dropped from ~10,000 to <2,000 — suggesting **promotion-driven spikes** early in the year.

### 2. **Customer Spending Patterns**
![Customer Spending Distribution](images/order_amount_dist.png)
![Pareto Curve](images/pareto_curve.png)
- Average spend per user ≈ $106; median $43.
- Top 15% of customers contribute ~60% of total revenue (Pareto pattern).

### 3. **Customer Lifecycle**
| Metric | Insight |
|:--------|:--------|
| Average Lifetime | 134 days |
| One-time Buyers | 51% |
| Repeat Buyers | 49% |
| Mean Purchase Cycle | 68 days |

## 🧮 Customer Segmentation (RFM Model)
![RFM Segmentation Clusters](images/rfm_scatter.png)
| Label | Description | Business Implication |
|:-------|:-------------|:--------------------|
| High-Value Customers | High Recency, Frequency, Monetary | Core loyalty segment |
| Key Growth Customers | High Frequency, Moderate Monetary | Potential up-sell target |
| Key Recovery Customers | Low Recency, Medium Monetary | Ideal for win-back marketing |

## 🔄 User Cohort Analysis
![User Status Area Chart](images/user_status_area.png)
- Early phase (first 3 months): strong acquisition and activation  
- Mid–late phase: drop in new users, rise in return users  
- Indicates market maturity and **shift from acquisition → retention**

## 📊 Key Metrics Summary
| Metric | Value | Interpretation |
|:---------|:------|:---------------|
| Average purchase cycle | 68 days | Normalized buying frequency |
| Active user rate | ~2.5% post-May | Platform maturity |
| Return user rate | ~5% | Established retention base |
| Repeat purchase rate | 20–22% | Moderate loyalty |
| Repurchase rate | ~30% | Healthy retention potential |

## 💡 Business Recommendations
1. **Retention Strategy:** Coupons ~3 days before expected repurchase (cycle ≈ 68 days).  
2. **Acquisition Optimization:** Re-engage dormant users via segmentation.  
3. **Engineering Extension:** Automate RFM via Python + Airflow.  
4. **Product Insight:** Focus on repeat-purchase features (saved carts, reminders).

## 🛠️ Tech Stack
- **Python:** pandas, numpy, matplotlib  
- **Visualization:** ggplot-style plots  
- **Modeling:** Pivot tables, RFM segmentation  
- **Extensions:** SQL + Airflow-ready pipeline  

## 🧭 Summary
This project demonstrates a full **data-to-insight pipeline** — from raw data cleaning to **business recommendations**.  
It highlights skills across:
- **Analytical reasoning (BA)**  
- **Data transformation (DE)**  
- **Strategic insight (PM)**

---
**Author:** hueEugene  
**Report:** `cd_userinfo.pdf`  
**Notebook:** `cd_userinfo.ipynb`
