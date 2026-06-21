# Customer Data Analysis — Power BI 

An end-to-end Power BI project analyzing customer shopping behavior across 10 shopping malls in Istanbul (2021–2023). The project covers data cleaning, DAX-based feature engineering, interactive dashboard design, and business recommendations derived from the insights.

---
## 📊 Project Overview

Retail businesses generate huge volumes of transactional data, but raw numbers alone don't drive decisions — patterns do. This project analyzes ~99.5K customer transactions to uncover how **gender, age group, product category, and payment method** influence purchasing behavior, and translates those patterns into actionable business recommendations.

**Key metrics from the dataset:**

| Metric | Value |
|---|---|
| Total Sales | 251.51M |
| Total Transactions | 99.457K |
| Total Products Sold | 299K |
| Time Period | 2021 – 2023 |
| Locations | 10 shopping malls, Istanbul |

---

## 🎯 Objectives

- Analyze customer shopping behavior based on gender and age group
- Identify which customer segment contributes the most to sales
- Understand product category performance
- Analyze payment method preferences
- Generate insights and provide business recommendations

---

## 🗂️ Dataset

The dataset contains transactional records with the following attributes:

| Column | Description |
|---|---|
| `invoice_no` | Unique transaction identifier |
| `customer_id` | Unique customer identifier |
| `gender` | Customer gender |
| `age` | Customer age |
| `category` | Product category purchased |
| `quantity` | Units purchased per transaction |
| `price` | Price per unit (Turkish Lira) |
| `payment_method` | Cash / Credit Card / Debit Card |
| `invoice_date` | Date of transaction |
| `shopping_mall` | Mall where the transaction occurred |

*Note: The raw dataset itself isn't included in this repo — it was provided via the internship platform's database connection. The `.pbix` file connects directly to that source.*

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — dashboard design & visualization
- **Power Query** — data cleaning and transformation
- **DAX** — calculated columns and measures

---

## 🧹 Data Preparation

- Removed duplicate transactions using `invoice_no` as the unique key
- Created a `Total Revenue` measure: `Total Revenue = Quantity × Price`
- Engineered an `Age Group` column via DAX `SWITCH` logic, binning customers into:
  - 18–25 (Young customers)
  - 26–35 (Early adults)
  - 36–45 (Mid-age group)
  - 46–55 (Mature customers)
  - 56+ (Senior customers)

```dax
age_group =
SWITCH(
    TRUE(),
    'customer'[Age] >= 18 && 'customer'[Age] <= 25, "18-25",
    'customer'[Age] >= 26 && 'customer'[Age] <= 35, "26-35",
    'customer'[Age] >= 36 && 'customer'[Age] <= 45, "36-45",
    'customer'[Age] >= 46 && 'customer'[Age] <= 55, "46-55",
    'customer'[Age] >= 56, "56+"
)
```

---

## 📈 Dashboard Pages

The Power BI dashboard is built across 5 interactive pages:

1. **Gender Based Analysis** — shopping distribution, products sold, and revenue by gender
2. **Age Group Based Analysis** — distribution, products sold, and revenue by age group
3. **Category Based Analysis** — category performance across age, gender, payment method, and mall
4. **Payment Based Analysis** — payment method trends across all customer segments
5. **Overall Insights & Recommendations** — summary insights and strategic recommendations

**Dashboard features:** KPI cards (sales, transactions, products sold), slicers for gender/age/category/mall/year, bar/pie/donut/treemap visuals, and navigation buttons (Home, Reset Filters, Next Page).

### Preview

**Gender-Based Analysis**
<img width="1455" height="794" alt="Gender Based Analysis" src="https://github.com/user-attachments/assets/cea96d18-3b34-4bb5-a989-a3339336cbc8" />

**Age Group-Based Analysis**
<img width="1458" height="796" alt="Age Group Based Analysis" src="https://github.com/user-attachments/assets/80d82ef1-235e-404a-894c-435f1e0803b2" />

**Category-Based Analysis**
<img width="1458" height="802" alt="Category Based Analysis" src="https://github.com/user-attachments/assets/81e0c83e-3cd2-4fd0-b105-e021c92d5e98" />

**Payment-Based Analysis**
<img width="1457" height="792" alt="Payment Based Analysis" src="https://github.com/user-attachments/assets/af7d997e-fca2-4a91-af8f-56779b2e4077" />

**Overall Insights & Recommendations**
<img width="1504" height="796" alt="Overall Insights" src="https://github.com/user-attachments/assets/f814450d-8f83-4f95-b06b-96f755ed8c5b" />


---

## 🔍 Key Insights

- **Female customers** drive the business: ~60% of transactions, ~150M TL in revenue, and ~179K products purchased — versus ~120K for male customers.
- **Customers aged 56+** are the most valuable segment by spend, contributing the highest revenue (67M TL) and transaction share (~26.7%), while 18–25 contributes the least.
- **Clothing** is the top revenue-generating category overall, followed by Shoes and Technology.
- **Cash** is the dominant payment method (44.69% of transactions), followed by Credit Card and Debit Card; older customers lean toward cash while younger customers use credit cards more.
- **Mall of Istanbul and Kanyon** generate the highest revenue among all 10 mall locations.

---

## 💡 Business Recommendations

- Focus marketing on female customers while running targeted campaigns to grow male engagement
- Promote high-performing categories (Clothing, Shoes, Technology) and use discounts/bundles to lift underperforming ones
- Offer premium products for the 56+ segment and trendy, affordable options for 18–25 customers
- Encourage card payments through cashback and rewards to reduce cash dependency
- Run localized promotions and events to boost low-performing malls
- Use personalized, segment-based offers to improve customer retention and repeat sales

---

## 📁 Repository Structure

```
├── Customer_data_analysis.pbix          # Power BI dashboard (open in Power BI Desktop)
├── Customer_Data_Analysis_Report.docx   # Full written project report
├── DASHBOARD_SCREENSHOTS_CDA.pdf        # Dashboard screenshots (all pages)
└── README.md
```

## ⚠️ Limitations

- Dataset limited to selected malls in Istanbul; findings may not generalize to other markets
- No customer income or stated-preference data available
- Seasonality and promotional effects aren't isolated in the analysis

---

## 📚 Key Learnings

This was my first capstone project, and it walked me through the full analytics workflow — from cleaning raw transactional data to delivering a stakeholder-ready dashboard:

- Data cleaning and validation in Power Query
- Writing DAX for calculated columns and measures (e.g., Age Group segmentation, Total Revenue)
- Designing an interactive, multi-page dashboard with KPIs, slicers, and navigation
- Translating visual patterns into business-relevant recommendations

---

## 👤 Author

**Jenihelan M**

