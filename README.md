a<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a0005,40:7B0D1E,80:C0392B,100:E74C3C&height=230&section=header&text=DMart%20Product%20Intelligence&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Beyond%20the%20Discount%20%E2%80%94%20Advanced%20Retail%20Analytics&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=20&duration=2500&pause=800&color=E74C3C&center=true&vCenter=true&multiline=true&width=800&height=80&lines=Transforming+5%2C000%2B+SKUs+into+Retail+Intelligence;Identifying+Retention+Heroes+%26+Closing+the+Value+Gap" alt="Typing SVG"/>
</p>

<br/>

<p align="center">
  <img src="https://img.shields.io/badge/SKUs%20Analyzed-5%2C000%2B-E74C3C?style=for-the-badge&logo=databricks&logoColor=white&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Discounted%20Products-99.8%25-C0392B?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/badge/High%20Value%20Products-25%25-922B21?style=for-the-badge&logo=target&logoColor=white&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Consumer%20Savings-%E2%82%B9556%2C940-E67E22?style=for-the-badge&logo=cashapp&logoColor=white&labelColor=1a0005"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Seaborn-4C8CBF?style=for-the-badge&logo=python&logoColor=white"/>
</p>

<br/>

---

## 📖 The Narrative — The "Discount Trap" Story

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=3500&pause=2000&color=E67E22&center=true&vCenter=true&width=780&lines=Is+every+discount+driving+loyalty%2C+or+are+some+merely+burning+margins%3F" alt="Narrative"/>
</p>

In the hyper-competitive Indian retail landscape, **"Discounting"** is often the only lever used to capture market share. DMart operates on a high-volume, low-price model — but a critical question remains unanswered.

This project uncovers the **"Value Gap."** By analyzing over 5,000 SKUs, we discovered that while **99.8% of the inventory is discounted**, only a fraction of those products deliver **"High Value"** to the consumer. This repository documents the journey of transforming a static product catalog into a dynamic intelligence system — identifying **"Retention Heroes"** that don't just offer a lower price, but a *price-to-utility ratio* that ensures repeat business.

<div align="center">

| 🛒 Total SKUs | 🏷️ Discounted | 💎 High Value | 📉 Value Gap |
|:---:|:---:|:---:|:---:|
| **4,732** | **4,722 (99.8%)** | **1,180 (25%)** | **3,542 lost products** |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🏗️ Strategic Challenges

<div align="center">

| Challenge | Description |
|:---|:---|
| 🔀 **The Normalization Paradox** | Developing a way to compare "deal quality" of a ₹10 staple vs a ₹1,000 premium item |
| 📦 **The Price-Volume Illusion** | Using Price per 100g metrics to strip away packaging bias and find true unit economic value |
| 🔁 **Proxy Retention Modeling** | Engineering a Synthetic Retention Index based on price-competitiveness and category rankings |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 💻 Technical Implementation

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=600&color=E74C3C&center=true&vCenter=true&width=800&lines=Feature+Engineering+%E2%86%92+Value+Scoring+%E2%86%92+Deal+Index+%E2%86%92+Retention+Modeling+%E2%86%92+Funnel+Analysis" alt="Pipeline"/>
</p>

<details open>
<summary><b>⚙️ A. Core Feature Engineering — Savings Efficiency & Unit Value</b></summary>

<br/>

We moved beyond basic arithmetic to create **multi-factor indices** that quantify the customer's psychological perception of a deal:

- **Savings Efficiency** — How effectively does the discount translate into real consumer value?
- **Unit Value (Price per 100g)** — Strips away packaging bias to reveal true unit economics
- **Deal Score** — A composite metric combining price-competitiveness and discount attractiveness

```python
# Savings Efficiency — the core value metric
df['savings_efficiency'] = (df['discount_pct'] / df['mrp']) * 100

# Unit Value — strips packaging bias
df['price_per_100g'] = (df['selling_price'] / df['weight_g']) * 100

# Value Score — multi-factor composite
df['value_score'] = (
    df['savings_efficiency'] * 0.5 +
    df['deal_score']         * 0.3 +
    (1 / df['price_per_100g']) * 0.2
)

# Synthetic Retention Index (proxy — no timestamps available)
df['retention_index'] = df['deal_score'] * df['category_rank_score']
```

</details>

---

<details open>
<summary><b>📊 B. The Value Funnel — Leakage Analysis</b></summary>

<br/>

The most critical finding: **only 25% of discounted products convert into High Value** offerings:

| Funnel Stage | Products | Drop-off |
|:---|:---:|:---:|
| 🏪 All Products | 4,732 | — |
| 🏷️ Discounted | 4,722 | -0.2% |
| 💛 High Value | ~1,180 | **-75%** ← Major bottleneck |
| 🌟 High Retention | Subset | Further drop |

> **Key Insight:** The largest value drop occurs between the **Discounted** and **High Value** stages — discounts alone are insufficient without alignment to pricing and perceived savings.

</details>

---

<details open>
<summary><b>🔑 C. The Golden Ratio Discovery</b></summary>

<br/>

```
Every 1% of discount → only 0.4% increase in Retention Index
```

This **plateau effect** reveals that deeper discounts stop providing meaningful value — confirming the need to shift from price-cutting to value-creation strategies.

</details>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📊 Data Visualizations

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2500&pause=1000&color=E67E22&center=true&vCenter=true&width=700&lines=19+Charts+%7C+Full+Value+Funnel+%7C+Retention+Modeling+%7C+KPI+Dashboard" alt="Charts"/>
</p>

---

### 📈 Chart 1 — Product Value vs. Savings Efficiency

> **Which products deliver the highest customer value when considering both price and savings?**

![Chart 1](images/chart1.png)

Product value is not driven by price alone — but by how effectively pricing translates into **meaningful customer savings**. Products combining affordability with strong discounts consistently deliver higher value, while high-priced products without proportional savings underperform.

---

### 🌐 Chart 2 — 3D Multi-Dimensional Value Analysis

> **What factors drive product value across price, discount, and deal attractiveness in 3D space?**

![Chart 2](images/chart2.png)

The highest-value products emerge within an **optimal zone** where moderate pricing is complemented by strong discounting — value is maximized when affordability aligns with meaningful savings.

---

### 🔍 Chart 3 — Feature Correlation Heatmap

![Chart 3](images/chart3.png)

Deep correlation analysis revealing which pairs of features move together — and which are independent drivers of consumer value perception.

---

### 📦 Chart 4 — Price per Unit Distribution

![Chart 4](images/chart4.png)

Unit-level pricing analysis that strips away packaging bias to surface the true economic value across product categories.

---

### 🎯 Chart 5 — Feature Importance: What Drives Product Value?

> **Which factors have the strongest influence on product value?**

![Chart 5](images/chart5.png)

<div align="center">

| Driver | Influence | Insight |
|:---|:---:|:---|
| 🏷️ Discount Percentage | **Primary** | Customers prioritize savings efficiency above all |
| ⭐ Deal Score | **Secondary** | Amplifies perceived value beyond raw price |
| 💰 Price | **Minimal** | Absolute price plays surprisingly little direct role |
| 📐 Unit Cost | **Negative** | Higher unit costs directly reduce perceived value |

</div>

---

### 🏢 Chart 6 — Category & Brand Value Hierarchy

> **Which categories and brands contribute most to overall product value?**

![Chart 6](images/chart6.png)

Value creation is **highly concentrated** within essential categories — Grocery, Dairy & Beverages, and Home & Kitchen. A small group of dominant brands contributes the majority of value, proving that value is driven by high-impact segments, not spread evenly.

---

### 📉 Chart 8 — Discount Distribution Analysis

![Chart 8](images/chart8.png)

A deep dive into how discounts are spread across the catalog — revealing clusters of over-discounting where margins are burned without proportional value gain.

---

### 🧩 Chart 9 — Multi-Feature Interaction Matrix

> **How do price, discount %, value score, and deal score interact to determine product value?**

![Chart 9](images/chart9.png)

Product value is driven by **combined interaction** of multiple factors. High-value products emerge when moderate pricing pairs with strong discounts and attractive deal scores — while low discounts produce poor value perception regardless of price.

---

### 📊 Chart 10 — Category Performance Benchmarking

![Chart 10](images/chart10.png)

Automated ranking of categories by cost and value, identifying high-margin items (Jams & Spreads ~₹150 avg) vs. low-cost traffic drivers (Spices ~₹75 avg).

---

### 🌟 Chart 11 — Retention Hero Categories

> **Which product categories demonstrate the highest value retention?**

![Chart 11](images/chart11.png)

**Grocery, Dairy & Beverages**, and select Electronics segments exhibit the highest value retention — driven by consistent pricing, reliable value delivery, and high purchase frequency. These categories naturally foster repeat buying behavior.

---

### 🗺️ Chart 12 — Retention Index Distribution

![Chart 12](images/chart12.png)

A full distribution map of the Synthetic Retention Index across the catalog, showing where the majority of products cluster and where the "Retention Heroes" live.

---

### 🏆 Chart 13 — Very High Retention Segment Analysis

> **Which product categories dominate the 'Very High' retention segment?**

![Chart 13](images/chart13.png)

**Electronics and Accessories** — including brands like Zebronics and computer accessories — achieve the highest value retention. These categories consistently deliver superior value through optimized pricing and discount strategies.

---

### 📋 Chart 14 — Retention Segment Distribution by Category

> **How does retention vary across all product categories?**

![Chart 14](images/chart14.png)

<div align="center">

| Performance | Category Type | Retention Pattern |
|:---:|:---|:---|
| 🟢 High | Electronics, Accessories | Consistent value + strong deals |
| 🟡 Moderate | Grocery, Dairy | High frequency but stable value |
| 🔴 Low | Niche, Non-essential | Inconsistent value + low frequency |

</div>

---

### 📊 Chart 15 — Brand-Level Value Analysis

![Chart 15](images/chart15.png)

Brand-by-brand breakdown of value delivery — surfacing which brands punch above their weight and which are coasting on category tailwinds.

---

### 🔬 Chart 16 — Deal Score vs. Retention Correlation

![Chart 16](images/chart16.png)

Mapping the relationship between deal attractiveness and repeat-purchase propensity — validating that the Deal Score is a meaningful proxy for long-term customer loyalty.

---

### 🌊 Chart 17 — Value Funnel: Where Do Products Drop Off?

> **At which stage does the greatest value drop occur?**

![Chart 17](images/chart17.png)

The funnel reveals that **75% of products fail to convert discounts into meaningful value**. The biggest bottleneck sits between the Discounted and High Value stages — discounts alone are not enough without alignment to pricing effectiveness.

---

### 🔄 Chart 18 — Funnel Progression & Bottleneck Map

> **How do products progress through the value funnel, and where do inefficiencies occur?**

![Chart 18](images/chart18.png)

Products that reach the high-value stage progress efficiently through deal attractiveness and retention — but a **major bottleneck exists early**, where the vast majority of discounted products fail to convert.

---

### 🖥️ Chart 19 — KPI Dashboard: Full Executive Snapshot

> **What do the key KPIs reveal about overall product performance, value creation, and retention?**

![Chart 19](images/chart19.png)

The combined dashboard reveals: a vast majority of products are discounted, only a limited proportion convert into high customer value, and an even smaller subset achieves strong retention. The **primary bottleneck is discount-to-value conversion**.

---

### 📊 Full Excel Intelligence Dashboard

![Dashboard](images/dash.png)

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📈 Excel Dashboard Intelligence Suite

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=700&color=E67E22&center=true&vCenter=true&width=700&lines=XLOOKUP+%7C+INDEX-MATCH+%7C+Pivot+Engines+%7C+Dynamic+Charts+%7C+Slicers" alt="Excel"/>
</p>

<div align="center">

| Feature | Implementation | Impact |
|:---|:---|:---|
| 🏗️ **Modular Architecture** | 4-layer system (Source → Lookup → Pivot → Dashboard) | 5,000+ SKUs organized and instantly updatable |
| 🔧 **Advanced Formulas** | XLOOKUP, INDEX-MATCH, nested IFS | Automated Price Categories, Value Scores, Deal Scores |
| 🌊 **Value Funnel** | Strategic bottleneck identification | 75% efficiency gap revealed |
| 📊 **Category Benchmarking** | Automated Pivot Tables | Jams & Spreads ~₹150 avg · Spices ~₹75 avg |
| 📌 **KPI Tracking** | Executive snapshot cards | ₹556,940 savings · 26.38% avg discount |
| 🎛️ **Interactive Filtering** | Slicers + Dynamic Charts | "No-code" diagnostic tool for real-time retail auditing |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 💡 Data-Driven Insights

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=3000&pause=1500&color=E74C3C&center=true&vCenter=true&width=800&lines=Retail+intelligence+is+not+about+being+the+cheapest%3B+it+is+about+being+the+most+valuable." alt="Insight"/>
</p>

---

### I. The Value Funnel Leakage

<div align="center">

```
4,732 Total Products
      ↓
4,722 Discounted  (99.8%)
      ↓  ← 75% DROP HERE
1,180 High Value  (25%)
      ↓
  Retention Heroes (top 15%)
```

</div>

> Most discounts are **"noise"** that fail to move the needle on customer value perception. There is a **75% drop-off** between a discount being offered and a discount being meaningful.

---

### II. Retention Heroes vs. Margin Burners

<div align="center">

| 🏆 High Performance | ⚠️ The Staple Trap |
|:---|:---|
| Personal Care & Home & Kitchen | Groceries — high volume, low per-SKU retention |
| Highest retention potential | High price-sensitivity + low brand loyalty |
| Strong deal scores across the board | Frequent purchase, but SKU-level retention is weak |

</div>

---

### III. The Power of Organic Anchor Products

**24 Mantra Organic** products (Atta, Brown Rice, Sugar) consistently score the **highest on the Deal Index (>400)**, serving as the Anchor Products for the entire DMart ecosystem — the products that bring customers back.

---

### IV. KPI Snapshot

<div align="center">

| 💰 Total Consumer Savings | 📉 Avg Global Discount | ⭐ Avg Deal Score | 🔁 Golden Ratio |
|:---:|:---:|:---:|:---:|
| **₹5,56,940.01** | **26.39%** | **42.96** | **1% discount = 0.4% retention** |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🎯 Strategic Roadmap & Recommendations

<div align="center">

| Priority | Action | Expected Outcome |
|:---:|:---|:---|
| 🔴 **1** | Re-evaluate pricing of 3,500+ products in the "Value Gap" | Close the 75% funnel leakage |
| 🟠 **2** | Pivot marketing spend toward the top 15% high Deal Score products | Maximize retention ROI |
| 🟡 **3** | Implement Python deal_score algorithm into live storefront | Auto-badge superior unit-economic products |
| 🟢 **4** | Build category-specific discount strategies | Improve retention for niche segments |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📁 File Structure

```
DMart-Data-Analytics-Visualization/
│
├── 📁 data/
│   └── DMart_.xlsx              # Raw product dataset (5,000+ SKUs)
│
├── 🖼️ images/                   # chart.png, chart1–19.png, dash.png
│
├── 📓 notebook/                 # Jupyter notebooks — Python EDA & feature engineering
│
└── 📋 README.md
```

---

## 📈 Conclusion

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=16&duration=3000&pause=99999&color=E74C3C&center=true&vCenter=true&width=800&lines=Every+rupee+of+discount+must+translate+into+customer+loyalty." alt="Conclusion"/>
</p>

This project provides the **mathematical framework** to ensure every rupee of discount translates into customer loyalty — not just a lower price tag. The deal_score algorithm and retention modeling can be directly operationalized into DMart's live pricing infrastructure.

<div align="center">

| 🔍 Value Intelligence | 📊 Funnel Optimization | 🛡️ Retention Engineering |
|:---:|:---:|:---:|
| Multi-factor value scoring across 5,000+ SKUs | Identifies the 75% discount-to-value gap | Synthetic Retention Index for every product |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:E74C3C,50:922B21,100:1a0005&height=140&section=footer&animation=fadeIn" width="100%"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Built%20with-Python%20%7C%20Excel%20%7C%20Pandas%20%7C%20Jupyter-E74C3C?style=flat-square&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/github/repo-size/Kushala125/DMart-Data-Analytics-Visualization?color=C0392B&style=flat-square&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/github/last-commit/Kushala125/DMart-Data-Analytics-Visualization?color=E74C3C&style=flat-square&labelColor=1a0005"/>
  &nbsp;
  <img src="https://img.shields.io/github/stars/Kushala125/DMart-Data-Analytics-Visualization?color=E67E22&style=flat-square&labelColor=1a0005"/>
</p>
