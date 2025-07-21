# Customer-SKU-Drop-off-Detection-Analysis

This module is part of the **Kevidko B2B Customer Behavior Analytics System**, focusing on identifying customers whose product diversity has significantly decreased and detecting specific products they stopped purchasing in the most recent month.

---

## 📌 Objective

To detect and list products **not purchased in the current month (July)** by customers who have **shown a decreasing trend in the number of purchased SKUs** over the past months (March–June), especially for products that were **previously purchased at least twice**.

This allows the sales and customer success teams to:
- Identify early warning signs of customer churn.
- Understand purchasing pattern shifts.
- Take proactive action to retain high-potential customers.

---

## 🧱 Project Structure

### 📂 Data Source
- Exported sales data from **QuickBooks**, including:
  - Customer Name
  - Product Code
  - Product Description
  - Order Date

### ⚙️ Process Flow

1. **Preprocessing**
   - Filter order dates to March–July 2025.
   - Clean and unify product and customer identifiers.

2. **Trend Detection**
   - Group data by customer and order month.
   - Count number of unique SKUs ordered per month.
   - Detect customers whose SKU counts **consistently declined for 3+ months**.

3. **Product Loss Analysis**
   - For flagged customers, compare SKUs purchased during March–June vs. July.
   - Identify missing SKUs that:
     - Were previously purchased ≥2 times.
     - Were not purchased at all in July.

4. **Export Results**
   - Output a structured Excel file with:
     - Customer Name
     - Missing Product Code
     - Missing Product Description

---

## 📊 Sample Output

| Customer                    | Product Code | Product Description             |
|----------------------------|--------------|---------------------------------|
| Civil Coffee – Studio City | SKU987       | 16oz Cold Cup – Clear Plastic   |
| Friends & Family Silverlake| SKU124       | Eco-Friendly Food Container     |
| RAHA Cafe                  | SKU205       | Brown Paper Bag – Medium        |

---

## 📈 Potential Enhancements
- Add Tableau dashboard showing SKU trendlines and alert signals.
- Create companion module for “extra purchases” (SKUs newly added).
- Integrate this pipeline with churn prediction model for holistic customer scoring.

---

## 🔧 Tech Stack

- Python (Pandas, Numpy, OpenPyXL)
- Excel
- QuickBooks (data export)
- Tableau (optional visualization)
