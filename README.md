# 🛒 E-Commerce Company's Path to Sustainable Growth
### Data-Driven Analysis for Operational Optimization

![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4c72b0)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📋 Table of Contents

- [Situation](#-situation)
- [Task](#-task)
- [Action](#-action)
- [Result](#-result)
- [Dataset Overview](#-dataset-overview)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)
- [Key Recommendations](#-key-recommendations)
- [How to Run](#-how-to-run)

---

## 🔴 Situation

An Indian e-commerce company selling fashion products (Kurtas, Sets, Western Dress, etc.) on **Amazon.in** was facing multiple operational and strategic challenges that threatened sustainable growth:

- **High order cancellation rates** — averaging ~14% monthly, leading to revenue leakage and fulfilment inefficiency
- **Logistics bottlenecks** — a significant share of orders remaining in a perpetual "Shipped" limbo without reaching final delivery
- **Unbalanced product performance** — revenue heavily concentrated in just a few product categories (Sets, Kurtas), creating business risk
- **Underdeveloped B2B segment** — despite B2B customers demonstrating higher average order values and stable behaviour, this segment remained largely untapped
- **Fragmented fulfillment** — orders split between Amazon-managed and Merchant-managed fulfilment with no visibility into performance differences
- **Geographic blind spots** — no systematic understanding of which cities/states drive demand, making inventory planning reactive rather than proactive

The company needed a comprehensive, data-driven diagnostic to understand *why* these problems were occurring and *what* to do about them.

---

## 🎯 Task

The goal was to conduct an end-to-end exploratory data analysis of the company's order transaction data to:

1. **Financial Performance** — Quantify revenue trends, identify best-selling products, and understand average spending behaviour
2. **Customer Insights** — Map top-performing geographies, analyse cancellation patterns, and differentiate B2B vs. B2C behaviour
3. **Logistics & Fulfillment** — Compare Amazon vs. Merchant fulfilment performance and assess shipping efficiency
4. **Product Management** — Pinpoint high-demand categories and assess quantity patterns for smarter inventory planning
5. **Customer Satisfaction & Returns** — Investigate return/cancellation patterns and identify problematic product areas
6. **Deliver Actionable Recommendations** — Translate every insight into a concrete business action

---

## ⚙️ Action

The analysis was conducted in a structured 4-step methodology:

### Step 1 — Data Exploration & Understanding
- Loaded and inspected the dataset (23 columns including Order ID, Date, Status, Fulfilment, Category, SKU, Amount, ship-city/state, B2B flag, etc.)
- Assessed data shape, column types, unique value distributions, and null counts
- Profiled key dimensions: order statuses, fulfilment types, product categories, and geographic spread

### Step 2 — Data Cleansing
- Handled missing values across multiple columns (Courier Status, fulfilled-by, promotion-ids, etc.)
- Replaced null values in the `Amount` column with the **median** to preserve statistical integrity without distorting the revenue distribution
- Dropped a fully blank trailing column (`Unnamed: 22`)
- Standardised date formats for time-series aggregation

### Step 3 — In-Depth Analysis (5 Analytical Pillars)

| Pillar | Key Analyses Performed |
|---|---|
| 💰 Financial Performance | Monthly revenue trends, MoM order growth, average order value by month, top revenue-generating categories |
| 👥 Customer Insights | Top cities & states by order volume, cancellation trend analysis, B2B vs. B2C order share and AOV comparison |
| 🚚 Logistics & Fulfillment | Amazon vs. Merchant fulfilment order breakdown, shipping service level (Standard vs. Expedited) distribution |
| 📦 Product Management | Category-wise demand ranking, size-level quantity analysis, SKU-level performance |
| 🔄 Returns & Cancellations | Month-over-month cancel rate tracking, return rate trends, status-wise order distribution |

### Step 4 — Visualisation & Insight Communication
- Built charts using **Matplotlib** and **Seaborn** — bar plots, line charts, pie charts, and heatmaps
- Constructed a monthly summary DataFrame capturing: total orders, cancellations, deliveries, returns, revenue, cancel rate %, delivery rate %, return rate %, and MoM change metrics

---

## 📊 Result

The analysis produced the following key findings:

### Revenue & Orders
- **April 2022** was the peak month — **49,043 orders** generating **₹2.63 Cr** in revenue
- Revenue declined steadily from April → June 2022, signalling a potential post-launch or post-season demand drop
- Average Order Value remained stable at approximately **₹535–₹571** across all months

### Product Performance
- **Sets** and **Kurtas** are the dominant revenue contributors — together they account for the majority of total sales
- Customer demand is strongly concentrated in the **₹500–₹1,000 price band**, indicating a value-conscious buyer base

### Customer Behaviour
- The business is overwhelmingly **B2C** in volume, but **B2B customers** show higher average order values and more predictable purchasing patterns — a clear growth opportunity
- Top demand cities include **Bengaluru, Mumbai, Hyderabad, and Chennai** — metro-first purchasing pattern

### Operational Challenges
- The **cancellation rate hovered around 14%** across April–June 2022, representing significant revenue and logistics waste
- The **return rate remained low (~1.3–1.8%)**, indicating customers are satisfied with received products — the problem is upstream (cancellations), not downstream (returns)
- A large proportion of orders remained in "Shipped" status without progressing to "Delivered to Buyer", pointing to last-mile delivery gaps

### Fulfillment
- Orders are split between **Amazon** and **Merchant** fulfilment, with **Easy Ship** as the dominant last-mile method

---

## 📁 Dataset Overview

| Column | Description |
|---|---|
| `Order ID` | Unique identifier for each order |
| `Date` | Order placement date |
| `Status` | Order status (Shipped, Cancelled, Delivered to Buyer, etc.) |
| `Fulfilment` | Fulfilled by Amazon or Merchant |
| `Sales Channel` | Platform (Amazon.in) |
| `ship-service-level` | Standard or Expedited shipping |
| `Style / SKU` | Product style code and stock-keeping unit |
| `Category` | Product category (Kurta, Set, Western Dress, etc.) |
| `Size` | Product size |
| `Qty` | Units ordered |
| `currency / Amount` | Transaction currency (INR) and value |
| `ship-city / ship-state / ship-country` | Shipping destination |
| `promotion-ids` | Applied promotion codes |
| `B2B` | Boolean — whether the order is Business-to-Business |
| `fulfilled-by` | Shipping fulfilment method (e.g., Easy Ship) |

---

## 📁 Project Structure

```
ecommerce-sustainable-growth/
│
├── Ecommerce_sustainable_development_analysis.ipynb   # Main analysis notebook
├── Problem_Statement.pdf                              # Project brief & objectives
└── README.md                                          # This file
```

---

## 🛠 Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Core programming language |
| Pandas | Data loading, cleaning, and manipulation |
| NumPy | Numerical computations |
| Matplotlib | Data visualisation |
| Seaborn | Statistical plotting |
| Jupyter Notebook | Interactive development environment |

---

## 💡 Key Recommendations

1. **Reduce Cancellation Rate** — Improve inventory accuracy, set realistic delivery timelines, and send proactive order confirmations
2. **Strengthen Core Categories** — Expand Sets and Kurtas product variety and invest in focused marketing for these lines
3. **Optimise Pricing** — Grow product offerings in the ₹500–₹1,000 sweet spot; develop value bundles for this segment
4. **Promote Top SKUs** — Use homepage placements, online ads, and seasonal campaigns to spotlight best-sellers
5. **Grow the B2B Segment** — Introduce bulk purchase discounts, dedicated B2B portals, and retailer partnership programs
6. **Improve Last-Mile Delivery** — Address the "Shipped but not Delivered" backlog through tighter courier SLA management
7. **Data-Driven Inventory** — Deploy demand forecasting using historical monthly trends to prevent stockouts and overstocking

---

## ▶️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/ecommerce-sustainable-growth.git
cd ecommerce-sustainable-growth
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

**3. Launch the notebook**
```bash
jupyter notebook Ecommerce_sustainable_development_analysis.ipynb
```

**4. Ensure the dataset CSV is in the same directory** and update the file path in the first data-loading cell if needed.

---

## 🙌 Acknowledgements

Project guided by **[Kashish Agrawal](https://www.linkedin.com/in/analyst-kashishagrawal/)** as part of a data analytics mentorship program.

---

*Built with 🐍 Python | Analysis performed on Amazon India e-commerce order data (Mar–Jun 2022)*
