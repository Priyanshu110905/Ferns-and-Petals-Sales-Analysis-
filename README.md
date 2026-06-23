# Ferns and Petals (FNP) Sales & Profitability Analysis

## 1. Background and Overview
**Ferns and Petals (FNP)** is a premier gifting brand specializing in delivering flowers, cakes, and personalized gifts across various major occasions (Diwali, Raksha Bandhan, Valentine’s Day, etc.). 

**The Business Problem:** Despite strong seasonal traffic, FNP needs to identify operational "weak spots"—specifically inefficiencies in delivery pipelines—and discover untapped revenue maximization opportunities to boost the bottom line. 

**Project Objective:**
To analyze **2023 sales and operational data** to identify delivery bottlenecks, uncover seasonal product trends, and propose data-driven strategies that optimize inventory allocation and improve overall profitability. 

* **Data Source:** [Data](https://drive.google.com/drive/folders/1EQNh7wdcfM5LagekiAQU4zyG-3m2Sfno?usp=drive_link)
* **Tech Stack Used:** **Microsoft Excel** (Power Query for Data Cleaning/ETL, Power Pivot & DAX for Data Modeling, Interactive Pivot Dashboards).
![image alt](https://github.com/Priyanshu110905/Ferns-and-Petals-Sales-Analysis-/blob/a8eeddb4f6e11b1ef34bee5eb92028ae2e840cda/Screenshot%202024-10-24%20160552.png)

---

## 2. Data Structure Overview

### 📖 Data Dictionary
Below is the core structure of the modeled data used for this analysis.

| Table | Column Name | Data Type | Description |
| :--- | :--- | :--- | :--- |
| **Orders** | `Order_ID` | `Text/Int` | Unique identifier for each transaction. |
| **Orders** | `Quantity` | `Number` | Number of items purchased per order. |
| **Orders** | `Order_Date` / `Delivery_Date` | `Date` | Timestamps for order placement and fulfillment. |
| **Orders** | `Revenue` | `Currency` | Total gross revenue generated per order (INR). |
| **Orders** | `diff_order_delivery`| `Number` | Calculated metric: Days taken to deliver the order. |
| **Products** | `Category` | `Text` | Product family (e.g., Cake, Soft Toys, Colors, Sweets). |
| **Customers**| `City` | `Text` | Delivery location/city of the customer. |

### 🗂️ Data Flow Diagram (Power Pivot Model)
![image alt](https://github.com/Priyanshu110905/Ferns-and-Petals-Sales-Analysis-/blob/0ed2335843c729a50b0f8d0f687a67153c087abc/Data%20Diagram.png)

### 🧹 Visual Data Cleaning Process (Power Query)
Raw data contained inconsistencies in date formatting, uncalculated logistics metrics, and missing price extensions. Below is the transformation process executed in Excel:

| Issue Identified | Before Cleaning (Raw) | After Cleaning (Transformed) | Business Impact |
| :--- | :--- | :--- | :--- |
| **Missing Revenue Field** | `Quantity: 4`, `Price: ₹1112` | `Revenue: ₹4448` | Enabled aggregated profitability metrics. |
| **Date String Formatting** | `24-02-2023` (Text) | `2023-02-24` (Date Format) | Allowed time-series and seasonality trend analysis. |
| **Missing SLA Metric** | No delivery timeframe | `diff_order_delivery = 5.53` | Allowed identification of logistical bottlenecks. |

---

## 3. Executive Summary
The analysis of **₹3.52M** in total revenue across 2023 revealed significant seasonal peaks offset by critical operational bottlenecks. 

**Key Quantified Outcomes:**
* **Total 2023 Revenue Generated:** **₹3,520,984**
* **Average Delivery Turnaround:** **5.53 Days** (A critical operational weak spot).
* **High-Value Seasonality:** Just two months—**August (₹737K) and February (₹704K)**—account for **40.9%** of the entire year's revenue, heavily driven by Raksha Bandhan and Valentine's Day.
* **Top Performing Category:** "Colors" generated **₹1.0M (28.5% of total revenue)**, vastly outperforming traditional categories like Cake (₹329K).

**The Bottom Line:** While FNP excels in capturing seasonal demand, the **5.53-day average delivery time** poses a severe risk to customer retention for time-sensitive occasions (e.g., Birthdays and Anniversaries).

---

## 4. Insights Deep Dive & Exploratory Data Analysis (EDA)

### Insight 1: Extreme Seasonality Drives the Bottom Line
Our EDA via Excel Pivot Charts reveals a massive spike in revenue during August (Raksha Bandhan) and February (Valentine's Day). Conversely, off-peak months like January (₹95K) and September (₹136K) drag down quarterly profitability.
* **Metric:** August Revenue: **₹737,389** | February Revenue: **₹704,509**

### Insight 2: Logistical Bottlenecks in Delivery (The Weak Spot)
The average time taken from order placement to delivery is 5.53 days. For an occasion-based gifting business, this lag directly threatens customer satisfaction and repeat business.
* **Metric:** Average diff_order_delivery across all **1000** orders is **5.53** days.

### Insight 3: Category Performance Anomalies
Contrary to assumption, baked goods ("Cake") are not the primary revenue driver. The "Colors" category generated ₹1,005,645, followed by "Soft Toys" (₹740,831).
* **Metric:** "Magnam Set" alone drove **₹121,905** in revenue.
* **Metric:** Anniversaries (₹674K) and Raksha Bandhan (₹631K) are the most lucrative occasions overall.

### 5. Recommendations for ROI & Profitability

Based on the data dashboard, I recommend the following actionable strategies to management:

* **1.Implement Express Fulfillment SLAs for High-Value Occasions:**
-Why it matters: The current 5.53-day delivery average is too slow for occasions like Birthdays and Anniversaries.
-Action: Invest in local dark-store fulfillment in top ordering cities to reduce delivery times to <48 hours, allowing for premium "Express Delivery" upcharges (estimated to boost revenue by 10-15%).

* **2.Capitalize on the "Colors" and "Soft Toys" Categories:**
-Why it matters: Colors account for nearly 30% of total revenue.
-Action: Create high-margin bundle packages (e.g., "Colors + Sweets") prior to Holi and Diwali. Since Sweets already bring in ₹733K, bundling the two top non-perishable items will increase the Average Order Value (AOV).

* **3.Smooth Out Off-Peak Months (Jan, Sep, Oct):**
-Why it matters: Revenue drops by over 85% from August to September.
-Action: Launch targeted email marketing campaigns focusing on "All Occasions" (currently bringing in ₹586K) or "Just Because" gifting discounts during Q3 and early Q1 to stabilize cash flow.

* **4.Optimize Inventory for the "Magnam Set":**
-Why it matters: As the #1 selling product (₹121K revenue), any stockout is a direct hit to profitability.
-Action: Increase warehouse safety stock for this item by 20% preceding the February and August rush.
