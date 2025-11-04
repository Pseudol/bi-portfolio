# 📊 Consumer Financial Complaints Analytics Dashboard

**Tool:** Power BI  
**Data Source:** DataDNA Dataset Challenge ( Consumer Financial Protection Bureau (CFPB) )
**Purpose:** Analyze  and identify patterns in complaints, evaluate company responses, and highlight areas of concern for regulators and consumers.

---

## 🔍 Overview
This dashboard provides a comprehensive view of complaints, company responses and areas of concern in the financial sector. It helps regulators and consumers to ensure fairness and accountability in the financial sector.

The CFPB collects complaints from consumers across the United States regarding financial products and services. Each complaint is tracked from submission through company response. The dataset consists of consumer complaints spanning multiple financial categories, locations, and companies. 

---

## 🧩 Key Metrics
- Total Complaints
- Average Response Time (Days)
- Timely Response Rate
- Complaints Per 1% Market Share

---

## 🧠 Data Model
- **Fact Table:** `Complaints`
- **Dimensions:** `DimDate`, `Company`, `Product`, `Location`
- Relationships: `Complaints[Company_ID_1081]` → `Company[Company_ID_1081]`, 
                 `Complaints[Date submitted]` → `DimDate[Date]`, 
                 `Complaints[Product_SubProduct_Key]` → `Product[Product_SubProduct_Key]`

---

## ⚙️ DAX Highlights
```DAX

Complaints = DISTINCTCOUNT('Complaints'[Complaint ID])

Complaints per 1% Market Share = 
DIVIDE(SUM(Company[Complaint_Count]), SUM(Company[Market_Share_Percent]))

Avg Response Time (Days) = AVERAGE(Complaints[Response_Time_Days])

Timely Response Rate = AVERAGE(Company[Timely_Response_Rate])

```
---

## 🚀 Insights

- The most complaints are reported for bank accounts (savings/checking account)
- Total complaints peaked in 2022 (~ 13k) and had less reports in 2017 (~5k)
- The South census region have the highest recorded complaints (~36%) followed by the West (~31%)
- Most complaints are reported for services rendered by small companies with ~94% of the total complaints
- Most complaints are reported via the Web and the average response time for resolving these complaints is 15 days.
