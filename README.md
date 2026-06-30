# E-commerce Sales Analysis: SQL + Python + Tableau

End-to-end analysis of e-commerce transactional data: from raw SQL extraction in Google BigQuery to exploratory analysis, statistical hypothesis testing, and an interactive Tableau dashboard.

## Project Goal

Identify key revenue drivers, seasonality patterns, and statistically significant differences in customer behavior across traffic channels, devices, and regions — to support data-driven marketing and product decisions.

## Dataset

- **Source:** Google BigQuery
- **Volume:** 349,545 session-level events, ~33,500 of which resulted in an order
- **Period:** full calendar year, includes holiday season
- **Fields:** date, session ID, geography (continent/country), device, browser, traffic source/channel, account status, product category, price

## Tech Stack

- **SQL** — data extraction from BigQuery
- **Python** (Google Colab) — pandas, numpy, matplotlib, seaborn, scipy, statsmodels
- **Tableau** — interactive dashboard

## Analysis Workflow

1. **Data Extraction** — SQL query joining sessions, accounts, and product data in BigQuery
2. **Exploratory Data Analysis** — data structure, descriptive statistics, missing values
3. **Geographic & Device Analysis** — sales by continent, country, device type, mobile models
4. **Traffic Analysis** — sales and sessions by traffic source/channel
5. **Registered Users Analysis** — verified vs unverified, subscribed vs unsubscribed behavior
6. **Sales Dynamics & Seasonality** — daily/weekly trends, holiday peak detection
7. **Pivot Tables & Heatmaps** — channel × device, category × country, device × channel
8. **Correlation Analysis** — Spearman correlation between sessions/sales, continents, channels, categories
9. **Hypothesis Testing** — Mann-Whitney U, Kruskal-Wallis (with Bonferroni correction), two-proportion Z-test, Chi-Square test of independence
10. **Tableau Dashboard** — interactive visualization of key metrics

## Key Insights

- **Organic Search dominates**, generating 34.2% of total sales, followed by Direct traffic (23.4%) — indicating strong SEO performance and brand recognition.
- **Clear holiday seasonality**: a sharp revenue spike in mid-December across all top continents, followed by a steep decline in late January.
- **Desktop + Organic Search** is the single most profitable device-channel combination; mobile revenue relies mainly on Direct and Organic traffic.
- **Device type and traffic channel are statistically dependent** (Chi-Square, p < 0.05): users from specific channels strongly prefer specific devices.
- **More sessions reliably drive more revenue** — a strong, statistically significant positive correlation (Spearman, p < 0.05) between daily sessions and daily sales.
- **Guest vs. registered users differ significantly** in sales behavior (Mann-Whitney, p < 0.05), with guest checkouts generating higher daily sales volume.
- **No significant AOV difference** between desktop and mobile buyers, and no significant difference in organic traffic share between Europe and the Americas — showing consistent behavior across these segments.
- 71.7% of registered users have verified emails, supporting reliable CRM/retargeting data quality.

## Tableau Dashboard

🔗 [E-commerce Sales Overview — Tableau Public](https://public.tableau.com/app/profile/anna.savchuk6598/viz/E-commerceSalesOverview_17821451873840/E-commerceSalesOverview?publish=yes)
