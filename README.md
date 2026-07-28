# customer-shopping-trends-analysis

# Customer Shopping Trends Analysis

A data-driven analysis of retail purchase behavior — from raw transaction data to a cleaned dataset, exploratory analysis in Python, and an interactive Power BI dashboard.

## Overview

This project analyzes 3,900 customer transactions to understand who customers are, when and what they buy, and how factors like discounts, subscriptions, and loyalty shape spending. The pipeline covers data cleaning, feature engineering, exploratory data analysis (EDA), and an interactive dashboard for non-technical stakeholders.

## Project Structure

```
.
├── shopping_trends.csv              # Raw source data (not included — see Data section)
├── shopping_trends_cleaned.csv      # Cleaned dataset with engineered features
├── analysis.ipynb                   # Jupyter notebook: cleaning, EDA, insights
├── Customer_Shopping_Dashboard.pbix # Power BI dashboard
└── README.md
```

## Dataset

| | |
|---|---|
| **Rows** | 3,900 customer transactions |
| **Columns** | 23 fields |
| **Format** | CSV |

**Key fields:** `customer_id`, `age`, `gender`, `item_purchased`, `category`, `purchase_amount_(usd)`, `location`, `size`, `color`, `season`, `review_rating`, `subscription_status`, `payment_method`, `shipping_type`, `discount_applied`, `promo_code_used`, `previous_purchases`, `frequency_of_purchases`

**Engineered fields** (added during feature engineering):

| Field | Description |
|---|---|
| `age_group` | Customer age bucketed into 6 life-stage bands (Under 18, 18-25, 26-35, 36-45, 46-60, 60+) |
| `spending_category` | Purchase amount tiered into Low / Medium / High |
| `loyalty_status` | Loyal / Regular / New, derived from `previous_purchases` |
| `discount_impact` | Whether a discount was applied to the sale |

## Methodology

1. **Load & Explore** — inspect shape, dtypes, and summary statistics of the raw data
2. **Data Cleaning**
   - Standardized column names (lowercase, underscores)
   - Checked for and removed duplicate records
   - Verified and coerced data types (purchase amount → numeric)
   - Audited missing values across all fields
   - Validated categorical labels (gender, season, category)
3. **Feature Engineering** — created `age_group`, `spending_category`, `loyalty_status`, and `discount_impact`
4. **Exploratory Data Analysis** — gender distribution, seasonal sales, category performance, top-selling items, spending by age group, and a correlation heatmap
5. **Dashboard** — connected the cleaned dataset to Power BI for interactive exploration

## Key Findings

- **Male-dominated base:** Men account for 68% of transactions (2,652 of 3,900), though average spend is nearly identical across genders ($59.54 vs. $60.25).
- **Clothing leads:** Clothing generates $104,264 in revenue — 45% of the total — more than accessories, footwear, and outerwear combined.
- **Demand is season-resilient:** Revenue varies only ~7% across seasons (Fall highest at $60,018, Summer lowest at $55,777).
- **Discounts drive volume, not value:** 43% of purchases involved a discount, but discounted and full-price buyers spend almost the same on average.
- **Subscriptions are underused:** Only 27% of customers subscribe, despite comparable spend levels — a clear growth opportunity.
- **Loyalty runs deep:** 80% of customers already qualify as "Loyal" (10+ prior purchases), indicating strong retention but a narrow new-customer pipeline.

## Business Recommendations

1. Prioritize clothing inventory and merchandising, the top revenue category
2. Grow subscription enrollment through targeted promotions
3. Re-evaluate blanket discounting in favor of acquisition-focused offers
4. Invest in top-of-funnel campaigns to widen new-customer acquisition
5. Keep marketing spend balanced across seasons rather than concentrated
6. Deepen engagement with the core male customer segment

## Tech Stack

- **Python** — Pandas, NumPy for data cleaning and feature engineering
- **Matplotlib, Seaborn** — statistical visualizations
- **Jupyter Notebook** — documented, reproducible analysis
- **Power BI** — interactive dashboard

## Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the analysis

```bash
jupyter notebook analysis.ipynb
```

### View the dashboard

Open `Customer_Shopping_Dashboard.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

## License

This project is available for personal and educational use.  MIT if distributing publicly.
