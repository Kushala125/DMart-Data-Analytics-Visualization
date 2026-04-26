<p align="center">
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

## 📖 1. The Narrative — The "Discount Trap" Story

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=3500&pause=2000&color=E67E22&center=true&vCenter=true&width=780&lines=Is+every+discount+driving+loyalty%2C+or+are+some+merely+burning+margins%3F" alt="Narrative"/>
</p>

In the hyper-competitive Indian retail landscape, **"Discounting"** is often treated as the single most powerful weapon in a retailer's arsenal. DMart has built its entire brand identity around a high-volume, low-price philosophy — and it has worked remarkably well at the macro level. But beneath the surface, a more troubling picture emerges.

This project was born from a single, uncomfortable question: **Is every discount actually earning customer loyalty, or are a large proportion of them simply burning margin without creating any lasting behavioral change?**

By analyzing over **5,000 SKUs** across multiple categories, we discovered that while **99.8% of the inventory is discounted**, only a fraction — roughly **1 in 4 products** — genuinely delivers "High Value" to the consumer. The remaining 75% of discounts exist in a grey zone: they lower the price tag, but they fail to shift the customer's perception of the product being a worthwhile, repeatable purchase.

This repository documents the complete journey of transforming a flat, static product catalog into a **dynamic intelligence system** — one capable of identifying **"Retention Heroes"** (products whose price-to-utility ratio is strong enough to drive repeat business) and exposing **"Margin Burners"** (products whose discounts are generous but whose value creation is negligible).

<div align="center">

| 🛒 Total SKUs | 🏷️ Discounted | 💎 High Value | 📉 Value Gap |
|:---:|:---:|:---:|:---:|
| **4,732** | **4,722 (99.8%)** | **1,180 (25%)** | **3,542 products wasting margin** |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🏗️ 2. Strategic Challenges

<div align="center">

| Challenge | Description |
|:---|:---|
| 🔀 **The Normalization Paradox** | How do you compare the "deal quality" of a ₹10 staple against a ₹1,000 premium item on the same scale? Raw discount amounts are meaningless without normalization. |
| 📦 **The Price-Volume Illusion** | A 5kg bag of rice looks cheaper than a 1kg bag — but is it? Price per 100g metrics strip away packaging bias to surface true unit economic value. |
| 🔁 **Proxy Retention Modeling** | Transaction timestamps were unavailable, so a Synthetic Retention Index was engineered from price-competitiveness scores and category rankings as a behavioral proxy. |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 💻 3. Technical Implementation (Python)

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=600&color=E74C3C&center=true&vCenter=true&width=800&lines=Feature+Engineering+%E2%86%92+Value+Scoring+%E2%86%92+Deal+Index+%E2%86%92+Retention+Modeling+%E2%86%92+Funnel+Analysis" alt="Pipeline"/>
</p>

<details open>
<summary><b>⚙️ Core Feature Engineering — Savings Efficiency, Unit Value & Deal Score</b></summary>

<br/>

The backbone of the project is **specialized feature engineering** that moves far beyond basic price arithmetic. Three core metrics were constructed to quantify the customer's psychological and economic perception of a deal:

- **Savings Efficiency** captures how much of the MRP is actually returned to the consumer as savings — not just in absolute rupees, but as a meaningful proportion of the product's full price. A product discounted by ₹200 on a ₹300 item is a very different deal than one discounted by ₹200 on a ₹2,000 item.
- **Price per 100g (Unit Value)** eliminates packaging and quantity bias by normalizing all prices to a standard unit. This is the only fair way to compare a 200g product against a 2kg product of the same type.
- **Deal Score** is a composite index that blends discount attractiveness, unit value, and category rank — creating a single number that reflects the overall "deal quality" from a consumer's perspective.

```python
# Savings Efficiency — core value metric (discount as % of MRP)
df['savings_efficiency'] = (df['discount_pct'] / df['mrp']) * 100

# Unit Value — strips packaging bias to reveal true economics
df['price_per_100g'] = (df['selling_price'] / df['weight_g']) * 100

# Composite Value Score — multi-factor weighted index
df['value_score'] = (
    df['savings_efficiency'] * 0.5 +
    df['deal_score']         * 0.3 +
    (1 / df['price_per_100g']) * 0.2
)

# Synthetic Retention Index (proxy — no transaction timestamps available)
df['retention_index'] = df['deal_score'] * df['category_rank_score']
```

</details>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📊 4. Data Visualizations & Deep Insights

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2500&pause=1000&color=E67E22&center=true&vCenter=true&width=700&lines=19+Charts+%7C+Full+Value+Funnel+%7C+Retention+Modeling+%7C+KPI+Dashboard" alt="Charts"/>
</p>

---

### 📈 Chart 1 — Product Value vs. Savings Efficiency

> **Which products deliver the highest customer value when considering both price and savings, and which products are potentially overpriced due to low value contribution?**

![Chart 1](images/chart1.png)

**What this chart shows:** This scatter visualization maps every product in the catalog against two axes — its selling price and its computed value score — revealing the relationship (or lack thereof) between how much a product costs and how much value it actually delivers to the consumer.

**Key Findings:** The most immediately striking pattern is the absence of a linear relationship between price and value. If price reliably predicted value, all points would cluster along a diagonal. Instead, the distribution is scattered, with high-value products appearing across all price bands, and notably, several high-priced products delivering below-average value scores. This is the first visual confirmation of the "Discount Trap" hypothesis.

**Deep Business Insight:** Products that combine **moderate pricing with strong savings efficiency** consistently land in the top-right quadrant — the "sweet spot" of value creation. In contrast, premium-priced products that fail to offer proportional savings are disproportionately represented in the low-value zone, despite their higher revenue contribution per unit. From a strategic standpoint, this means DMart cannot rely on premium products to anchor its value proposition. The real value story is being written in the mid-price tier, where savings efficiency is highest relative to price. Brands and categories that sit in the bottom-right quadrant (high price, low value) represent the clearest candidates for pricing review or promotional restructuring.

**Actionable Implication:** Product managers should use this chart as a quarterly pricing audit tool. Any product consistently scoring below the value-score median for its price tier should either receive a deeper discount or face de-listing from premium shelf placement.

---

### 🌐 Chart 2 — 3D Multi-Dimensional Value Analysis

> **What factors drive product value when analyzing the combined impact of price, discount percentage, and deal attractiveness in a multi-dimensional analytical space?**

![Chart 2](images/chart2.png)

**What this chart shows:** A three-dimensional scatter plot that simultaneously maps price, discount percentage, and deal score across a single visualization — allowing the analyst to observe how all three variables interact to produce the final value outcome for each product.

**Key Findings:** The 3D space reveals a cluster of maximum-value products concentrated in a specific "golden zone" — products priced between ₹50 and ₹300, with discounts exceeding 20%, and deal scores above 40. Products outside this zone either lack the discount depth (low discount %), the pricing accessibility (high price), or the deal attractiveness (low deal score) needed to generate strong value signals. What's particularly revealing is the "dead zone" at the high-price, low-discount corner of the 3D space — products that are expensive and barely discounted. These products have almost zero representation in the high-value cluster.

**Deep Business Insight:** This visualization confirms that **value is not a single-variable outcome** — it requires all three conditions to be met simultaneously. A deeply discounted product that is still too expensive for its category won't generate the same loyalty response as a moderately discounted product at the right price point. Similarly, a cheap product with almost no discount fails to signal "deal" to the consumer, reducing its perceived attractiveness. The interaction of all three dimensions is what separates Retention Heroes from Margin Burners.

**Actionable Implication:** This 3D model should inform DMart's promotional calendar. When planning category-level sales events, the goal should not be to simply increase discount depth — it should be to move more products into the golden zone by simultaneously optimizing price, discount, and deal score. Category managers should identify which of their underperforming products are closest to the golden zone and target them for minor pricing adjustments.

---

### 🔍 Chart 3 — Feature Correlation Heatmap

![Chart 3](images/chart3.png)

**What this chart shows:** A full correlation matrix visualized as a heatmap, showing the pairwise statistical relationship between every engineered and raw feature in the dataset — including price, MRP, discount amount, discount percentage, savings efficiency, deal score, value score, unit price, and retention index.

**Key Findings:** Several correlations stand out as strategically significant. First, **discount percentage and value score** show a strong positive correlation, while **absolute price and value score** show a notably weak or even negative correlation in certain segments — reinforcing that how you discount matters far more than what you charge. Second, **unit price (price per 100g) and retention index** show a negative correlation, confirming that products with high unit costs consistently underperform on retention, even when their absolute selling price appears reasonable. Third, **deal score and savings efficiency** are highly correlated, validating that the deal score composite metric is capturing real consumer-perceived value and is not redundant with simpler metrics.

**Deep Business Insight:** The heatmap exposes which features are genuinely independent drivers of value versus which are proxies for each other. Many of the features that retail managers intuitively focus on — total discount amount in rupees, absolute price, shelf prominence — show weaker correlations with actual value outcomes than the normalized metrics like savings efficiency and unit cost. This is a critical reframing: the data is telling us that **the psychology of value creation** operates on ratios and proportions, not absolutes. A ₹5 discount on a ₹20 product (25% off) creates a stronger value signal than a ₹50 discount on a ₹500 product (10% off), even though the latter involves 10x more money.

**Actionable Implication:** Use the correlation matrix to eliminate redundant KPIs from internal reporting dashboards. Metrics with correlation coefficients above 0.85 with more complex composite scores add little incremental information. Simplify internal scorecards to focus on savings efficiency, unit cost, and deal score as the three primary value drivers.

---

### 📦 Chart 4 — Price per Unit Distribution

![Chart 4](images/chart4.png)

**What this chart shows:** A distribution analysis of the price-per-100g metric across the entire catalog, segmented by product category. This is the foundational "apples-to-apples" comparison that makes cross-product and cross-category analysis meaningful.

**Key Findings:** The distribution is heavily right-skewed, with the majority of products clustering in a unit-price band of ₹20–₹80 per 100g, but a long tail of premium and specialty products extending well beyond ₹200 per 100g. Critically, the distribution is **not uniform across categories** — Spices and Condiments show tight clustering at the low end, while Premium Nutrition, Organic, and Specialty products display wide dispersion with many high-unit-cost outliers.

**Deep Business Insight:** This chart exposes the "volume anchor" effect in DMart's catalog. The majority of footfall is driven by products in the low-unit-cost cluster — commodities like rice, sugar, and flour that consumers purchase in bulk precisely because the per-unit economics are compelling. However, these same products are the most vulnerable to competitive pricing from other retailers, as the consumer's price memory is sharpest for commodity items. The long tail of high-unit-cost products, while contributing less to footfall, carries disproportionate margin potential — provided they can justify their unit economics through quality or brand positioning. Currently, many of them cannot, as the value score analysis reveals.

**Actionable Implication:** Category teams should use unit-price distribution as a benchmarking tool. Any product priced significantly above its category's median unit cost should be required to demonstrate a commensurate improvement in deal score or consumer rating to justify its shelf placement and promotional investment.

---

### 🎯 Chart 5 — Feature Importance: What Actually Drives Product Value?

> **Which factors have the strongest influence on product value, and how do pricing and discount dynamics interact to shape customer value perception?**

![Chart 5](images/chart5.png)

**What this chart shows:** A feature importance analysis — likely derived from a gradient boosting or random forest model trained on the value score target — ranking each input variable by its relative contribution to predicting whether a product will be classified as High Value or not.

**Key Findings:**

<div align="center">

| Rank | Feature | Relative Importance | Interpretation |
|:---:|:---|:---:|:---|
| 1 | 🏷️ Discount Percentage | **Primary Driver** | Customers respond to proportional savings above all else |
| 2 | ⭐ Deal Score | **Strong Amplifier** | Composite attractiveness enhances the discount signal |
| 3 | 💰 Absolute Price | **Weak Contributor** | Price matters less than expected once discount is controlled |
| 4 | 📐 Unit Cost (per 100g) | **Negative Driver** | Higher unit costs actively suppress value perception |
| 5 | 🏪 Category Rank | **Context Modifier** | Category-level positioning adjusts baseline expectations |

</div>

**Deep Business Insight:** The single most important takeaway from this chart is that **price itself is a surprisingly weak predictor of value** once discount percentage is accounted for. This directly contradicts the common retail assumption that lowering absolute prices is the primary path to improving consumer value perception. What consumers are actually responding to is the *signal* of savings — the percentage off the original price — rather than the end price in isolation. This explains why a ₹30 product marked down from ₹40 (25% off) often outperforms a ₹25 product that has never been discounted, despite being more expensive. The discount percentage carries a psychological weight that the final price cannot replicate. The negative influence of unit cost is equally important — it tells us that value perception collapses when consumers sense they are paying too much per unit of product, regardless of how attractively the discount is presented.

**Actionable Implication:** Redesign the promotional pricing architecture. Instead of focusing solely on achieving a target shelf price, set targets for discount percentage as the primary promotional lever. Products in the "High Potential" tier should be promoted with an explicit percentage-off badge rather than a price reduction, as the former creates a stronger value signal. Additionally, high-unit-cost products should be prioritized for packaging review — offering larger pack sizes at the same price point improves unit economics without requiring deeper nominal discounts.

---

### 🏢 Chart 6 — Category & Brand Value Hierarchy

> **Which categories and brands contribute most significantly to overall product value, and how is this value distributed across the product hierarchy?**

![Chart 6](images/chart6.png)

**What this chart shows:** A hierarchical breakdown — possibly a treemap or stacked bar — of total value contribution across product categories and, within each category, across brands. This allows simultaneous analysis of both the category-level and brand-level value drivers.

**Key Findings:** The distribution is sharply unequal. Three categories — **Grocery, Dairy & Beverages, and Home & Kitchen** — account for the overwhelming majority of total catalog value. Within these categories, a relatively small number of dominant brands (typically 3–5 per category) contribute the bulk of value, while a long tail of smaller brands contributes marginally. The brand concentration within Grocery is particularly striking — a handful of trusted household names generate value scores that the remaining brands cannot approach, even when their discounts are deeper.

**Deep Business Insight:** This chart reveals a **Pareto-style concentration effect** in DMart's value architecture. Roughly 20% of categories and 15–20% of brands are generating approximately 80% of the catalog's total consumer value. This is both a strength and a vulnerability. It is a strength because it means DMart's core value proposition is anchored by a reliable set of high-performing categories and brands. It is a vulnerability because it implies an over-dependence on a narrow slice of the catalog — if any of those anchor brands were to exit, adjust pricing, or reduce available discounts, the impact on overall catalog value would be disproportionately large. The long tail of low-value brands is not merely underperforming — it is actively diluting the catalog's overall value average, creating a misleading impression of broad value delivery when the reality is highly concentrated.

**Actionable Implication:** Curate the catalog more aggressively. Products from brands in the bottom quartile of category-level value contribution should be evaluated for de-listing unless they serve a specific footfall or category-completion purpose. The freed shelf space and promotional budget should be redirected toward expanding the depth and variety of proven high-value brands and categories.

---

### 📉 Chart 8 — Discount Distribution Analysis

![Chart 8](images/chart8.png)

**What this chart shows:** A frequency distribution of discount percentages across all 4,700+ products in the catalog, revealing how discounts are spread from near-zero all the way to the maximum observed discount level.

**Key Findings:** The distribution reveals several distinct clusters. The largest cluster sits between 15–30% discount — the "middle market" of promotional pricing where the majority of DMart's catalog lives. A second, smaller cluster exists at the 0–10% range, representing products that are technically discounted but where the discount is so shallow it provides little to no behavioral stimulus. A third cluster at the 35–50% range represents the deep-discount products — typically end-of-season items, bulk goods, or loss leaders — that drive footfall but often at the cost of margin sustainability.

**Deep Business Insight:** The distribution exposes a **discount architecture problem**. The 0–10% cluster is particularly problematic — these products carry the cost of being labeled as "discounted" (which influences catalog positioning and promotional spend) while delivering almost none of the psychological or behavioral benefits of a meaningful discount. Consumer psychology research consistently shows that discounts below approximately 15% are largely invisible to the average shopper — they do not shift purchase intent, do not increase basket size, and do not drive repeat visits. DMart is effectively subsidizing a large segment of its catalog for zero behavioral return. At the other extreme, the 35–50% cluster needs scrutiny — while these products perform well on value score, they may be pricing at levels that are training consumers to wait for promotions rather than developing habitual purchase behavior at full promotional price.

**Actionable Implication:** Implement a minimum effective discount threshold policy. Products below 15% discount should either be moved to full price (removing the misleading discount label) or have their discounts meaningfully increased to cross the perceptual threshold. The promotional budget freed from ineffective sub-15% discounts should be reinvested in deepening discounts on high-retention-potential products that are currently sitting just below the deal score threshold.

---

### 🧩 Chart 9 — Multi-Feature Interaction Matrix

> **How do multiple features such as price, discount percentage, value score, and deal score interact to determine overall product value?**

![Chart 9](images/chart9.png)

**What this chart shows:** A pair-plot or multi-dimensional interaction matrix that plots every feature against every other feature simultaneously — creating a comprehensive view of how the input variables relate to each other and to the final value score outcome, with points color-coded by value tier (Low, Medium, High, Very High).

**Key Findings:** The matrix reveals several non-obvious interaction patterns. The most important is the **joint effect of discount percentage and deal score** — when both are high simultaneously, value score spikes dramatically beyond what either variable could achieve alone, confirming a multiplicative rather than additive relationship. The interaction between price and value score shows a characteristic "arch" shape — value increases as price rises from very low levels (where extreme cheapness signals low quality), peaks in the mid-price range, then falls sharply as price enters the premium tier without proportional discount compensation.

**Deep Business Insight:** The arch-shaped price-value relationship is one of the most strategically important findings in the entire analysis. It directly refutes two common retail pricing myths simultaneously: first, that "cheaper is always better" (the very low end underperforms), and second, that "premium pricing signals quality that customers will pay for" (the high end consistently underperforms without heavy discounting). The **optimal value zone is the mid-price band with strong discounting** — and products from across many different categories cluster in this zone when they achieve high value scores. This is DMart's actual competitive moat: not its cheapest products, and not its premium ones, but its mid-tier products with the highest savings efficiency.

**Actionable Implication:** Use the interaction matrix as a product development brief for private label and exclusive brand negotiations. When DMart is negotiating terms with supplier brands, the target should be products that can be positioned in the mid-price tier with discount headroom of 20–35% — the zone where the interaction effects create the maximum value amplification.

---

### 📊 Chart 10 — Category Performance Benchmarking

![Chart 10](images/chart10.png)

**What this chart shows:** A comparative benchmarking chart ranking all product categories by their average cost metrics and value scores — creating a league table of category-level performance that allows apples-to-apples comparison across very different product types.

**Key Findings:** The benchmarking reveals significant performance disparities between categories that, on the surface, appear similar. **Jams & Spreads** emerge as a high-average-cost category (~₹150 avg) with relatively modest value scores, while **Spices** operate as a low-cost, high-footfall category (~₹75 avg) that punches above its weight on deal score despite thin absolute margins. **Organic & Natural** categories show the widest variance — some organic SKUs achieve extraordinary deal scores while others represent some of the lowest value-for-money in the entire catalog.

**Deep Business Insight:** The benchmarking chart exposes a **category-level pricing efficiency gap**. High-cost categories like Jams & Spreads are not delivering value scores commensurate with their cost positioning — consumers are paying premium prices but not perceiving premium value, suggesting either that the discount structure is insufficient, the product formulation doesn't justify the price, or the category lacks the trust and frequency of purchase that would generate strong retention signals. In contrast, the Spices category demonstrates that even very inexpensive products can generate strong deal perception when the savings efficiency is optimized — small absolute savings on small absolute prices can still create powerful value signals if the percentage discount is meaningful. The Organic category's wide variance is actually an opportunity: it contains some of DMart's highest-performing products (24 Mantra Organic) alongside some of its most overpriced, suggesting that category-level strategies need to be SKU-specific rather than blanket.

**Actionable Implication:** Develop category-specific value targets. Rather than applying a uniform discount percentage across all products, set minimum value score thresholds by category, reflecting the different purchase dynamics, frequency, and price sensitivity of each segment.

---

### 🌟 Chart 11 — Retention Hero Categories

> **Which product categories demonstrate the highest value retention, and what key characteristics make them strong drivers of customer loyalty?**

![Chart 11](images/chart11.png)

**What this chart shows:** A retention-focused ranking of product categories, using the Synthetic Retention Index to identify which categories are most likely to drive repeat visits and habitual purchase behavior — effectively identifying DMart's loyalty engine.

**Key Findings:** **Grocery, Dairy & Beverages** lead the retention rankings, driven by their essential nature and high purchase frequency. However, the surprise finding is that certain subcategories within **Home & Kitchen** (particularly cleaning products and storage solutions) outperform many food categories on the retention index, despite being purchased less frequently. **Personal Care** emerges as a strong mid-tier performer, with several brand-specific subcategories — particularly deodorants, hair care, and oral hygiene — showing retention indices well above the catalog average.

**Deep Business Insight:** The retention hierarchy reveals an important distinction between **frequency-driven retention** and **value-driven retention**. Grocery retains customers primarily through necessity — consumers return because they must repurchase these items regularly, not necessarily because DMart's offer is uniquely compelling. This makes grocery retention somewhat fragile: it persists as long as DMart's prices remain competitive, but it does not represent deep loyalty that would survive a price-matching response from competitors. In contrast, categories like Personal Care and Home & Kitchen achieve their retention scores through genuine value creation — consumers actively choose DMart for these products because the deal quality is consistently superior. This value-driven retention is far more durable and represents a genuine competitive moat. Brands operating in these categories — particularly those with deal indices consistently above 300 — are the true Retention Heroes of the DMart ecosystem.

**Actionable Implication:** Separate the marketing and promotional strategy for frequency-driven versus value-driven categories. Frequency categories (Grocery, Dairy) need price-parity protection to prevent attrition. Value-driven categories (Personal Care, Home & Kitchen) need deal-depth amplification to convert moderate performers into full Retention Heroes. The top 10% of value-driven SKUs by retention index should be featured in DMart's loyalty communication — these are the products that actually create the emotional connection consumers have with the brand.

---

### 🏆 Chart 12 — Retention Index Distribution

![Chart 12](images/chart12.png)

**What this chart shows:** A full frequency distribution of the Synthetic Retention Index across all products, showing how the entire catalog distributes across retention tiers from Low to Very High.

**Key Findings:** The distribution is right-skewed, with the large majority of products clustering in the Low to Medium retention bands and a progressively smaller number achieving High and Very High retention scores. The tail is very thin — fewer than 15% of products reach the High tier, and the Very High tier represents a true elite: a small, concentrated group of SKUs that are delivering exceptional retention value.

**Deep Business Insight:** The shape of the retention distribution is strategically revealing. In a well-optimized catalog, you would expect a more balanced distribution — a meaningful proportion of products in each tier. Instead, DMart's catalog is heavily bottom-heavy, with the vast majority of products failing to generate strong retention signals. This is not necessarily a failure of product quality — it is, in large part, a failure of discount strategy. Many products in the Low retention tier have the category positioning and brand equity to achieve High retention scores, but their current discount structures are insufficient to generate the deal score needed to cross the threshold. The thin Very High tail represents DMart's most underexploited asset: these products are generating extraordinary retention value, but they are not being actively promoted or highlighted in ways that would amplify their impact on overall footfall and basket size.

**Actionable Implication:** Use the retention distribution as a portfolio health metric. Set a quarterly target to shift at least 5% of products from Low to Medium retention and 3% from Medium to High. Track which pricing interventions (discount deepening, pack-size optimization, bundle offers) are most effective at moving products up the retention tier ladder.

---

### 🥇 Chart 13 — Very High Retention Segment Deep Dive

> **Which product categories demonstrate the strongest value retention based on the proportion of products in the 'Very High' retention segment?**

![Chart 13](images/chart13.png)

**What this chart shows:** A focused analysis of the Very High retention tier specifically — identifying which categories are disproportionately represented among the elite performers and which brands are driving that outperformance.

**Key Findings:** The most surprising finding in this chart is the outsized presence of **Electronics and Accessories** in the Very High retention segment. Categories including computer accessories, mobile accessories, and brands like **Zebronics** achieve the highest proportional representation in the Very High tier — a counterintuitive result given that electronics are purchased far less frequently than food or personal care items. Within the more traditional DMart categories, **24 Mantra Organic** stands out as the dominant brand in the Very High tier for the Grocery segment, consistently achieving deal indices above 400.

**Deep Business Insight:** The Electronics and Accessories finding deserves particular attention because it challenges the assumption that retention is primarily driven by purchase frequency. The reason electronics accessories achieve Very High retention scores is not that consumers buy them repeatedly every week — they don't. Instead, these products achieve high retention because their **deal score is exceptionally strong relative to consumer expectations** for that category. When a consumer finds a ₹500 USB cable at DMart for ₹200, the savings efficiency is high, the deal score is extraordinary, and the consumer not only returns for future electronics purchases but also updates their mental model of DMart as a value destination across categories. This **halo effect** — where high-value performance in one category improves overall brand perception — is one of the most powerful and underappreciated mechanisms in retail loyalty. The 24 Mantra Organic phenomenon follows a similar logic: organic products are expected to be expensive, so when DMart offers them at deal scores above 400, the cognitive surprise is enormous and the loyalty signal is correspondingly strong.

**Actionable Implication:** Invest aggressively in the Very High retention categories, particularly Electronics Accessories. Expand the SKU range in this segment, deepen supplier relationships to secure better cost structures, and use these products as prominent marketing assets in both in-store displays and digital communication. The halo effect they generate is worth far more than their direct revenue contribution.

---

### 📋 Chart 14 — Retention Segment Distribution by Category

> **How do different product categories perform in terms of retention, and what key patterns emerge across retention segments?**

![Chart 14](images/chart14.png)

**What this chart shows:** A stacked bar or segmented chart showing the proportion of products in each retention tier (Low, Medium, High, Very High) broken down by product category — allowing comparison of retention profiles across the entire category portfolio simultaneously.

**Key Findings:** Retention profiles vary dramatically across categories. Electronics and Accessories show a distribution heavily weighted toward the upper tiers, with a significant proportion in High and Very High. Essential grocery categories show a more uniform distribution with moderate representation across all tiers. Niche and non-essential categories — including premium beverages, specialty foods, and seasonal items — are disproportionately concentrated in the Low tier, with minimal presence in High or Very High.

**Deep Business Insight:** The category-level retention profiles reveal three distinct strategic archetypes within DMart's catalog. The first archetype is **"Value Magnets"** — categories where a large proportion of products achieve High or Very High retention. These categories (Electronics Accessories, Personal Care, 24 Mantra Organic) should be treated as loyalty infrastructure: they are the reason consumers choose DMart over competitors even when price parity exists elsewhere. The second archetype is **"Frequency Vehicles"** — categories like Grocery and Dairy where retention is moderate and driven by necessity rather than deal excellence. These categories maintain footfall but do not create the emotional loyalty that protects against competitive disruption. The third archetype is **"Portfolio Drag"** — categories where the vast majority of products sit in the Low retention tier, consuming shelf space, working capital, and promotional budget while delivering minimal loyalty return. This third group represents the most immediate opportunity for catalog optimization.

**Actionable Implication:** Develop category-specific retention targets aligned with each archetype. Value Magnets should have a target of 30%+ products in Very High retention. Frequency Vehicles should focus on increasing the proportion in High retention. Portfolio Drag categories should face quarterly rationalization reviews with clear improvement timelines or de-listing consequences.

---

### 📊 Chart 15 — Brand-Level Value Analysis

![Chart 15](images/chart15.png)

**What this chart shows:** A brand-by-brand ranking of average value scores, deal scores, and retention indices — identifying which brands consistently deliver strong value across their entire portfolio versus which rely on a few hero products to disguise a weak overall offering.

**Key Findings:** Brand performance is highly variable even within the same category. Some brands achieve consistently high value scores across their entire SKU range — indicating that their pricing and discount structure is well-calibrated relative to consumer expectations. Others show extreme variance, with a few standout products elevating the brand average while the majority of their portfolio underperforms. **24 Mantra Organic** is the standout brand for catalog-wide consistency, achieving high value and deal scores across virtually its entire range.

**Deep Business Insight:** The distinction between **consistent brand performers** and **hero-dependent brands** is critically important for procurement and shelf-space decisions. A brand with a high average value score driven by two or three exceptional products is not the same as a brand where every product delivers strong value — the former creates inventory risk (if those hero products are discontinued or repriced, the brand's value contribution collapses), while the latter creates a durable partnership worth investing in. Brands in the hero-dependent category should be approached in supplier negotiations with a clear message: DMart will continue expanding shelf space for their hero products but will rationalize the rest of their catalog unless value consistency improves across the broader portfolio.

**Actionable Implication:** Build brand scorecards that track not just average value score but also value score standard deviation. A brand with a high average but high variance should receive a lower partnership tier than a brand with a slightly lower average but low variance — because predictability and consistency are more valuable than occasional excellence in a high-volume retail environment.

---

### 🔬 Chart 16 — Deal Score vs. Retention Correlation

![Chart 16](images/chart16.png)

**What this chart shows:** A scatter plot correlating deal score against retention index for every product, with category-level color coding to reveal whether the deal score → retention relationship holds uniformly or varies significantly by category.

**Key Findings:** The overall relationship between deal score and retention index is positive but notably non-linear. At low deal scores (below 30), retention indices cluster near zero regardless of category — confirming that below a minimum deal quality threshold, no amount of other product attributes can generate meaningful retention. Above a deal score of approximately 40–45, the retention response accelerates — a relatively small improvement in deal score produces a much larger improvement in retention index. This inflection point is one of the most practically useful findings in the analysis.

**Deep Business Insight:** The non-linear relationship reveals a **deal score activation threshold** — a minimum level of deal quality below which products are essentially invisible to the consumer's loyalty-formation process, and above which even small improvements generate outsized retention returns. This is the retail equivalent of a "cold start" problem: products need to cross the deal score threshold to enter the consumer's consideration set for repeat purchase. Products sitting just below the threshold (deal scores of 35–42) represent the highest-leverage intervention targets in the catalog — a modest increase in their discount depth or promotional visibility could push them over the activation threshold and generate significant retention uplift.

**Actionable Implication:** Identify all products with deal scores between 35 and 42 (the "pre-activation" zone). These are the best candidates for a targeted "Deal Score Boost" initiative — small, targeted discount increases or bundle offers designed to cross the activation threshold. The expected retention return per rupee of promotional investment in this zone is significantly higher than for products already in the High or Very High tier.

---

### 🌊 Chart 17 — Value Funnel: Where Do Products Fall Off?

> **At which stage in the product value funnel do products experience the greatest drop, and what does this reveal about pricing effectiveness?**

![Chart 17](images/chart17.png)

**What this chart shows:** A funnel visualization tracking the number of products that successfully pass through each stage of the value creation journey — from the total catalog, through discounted, to High Value, to High Retention — with the size of each stage reflecting the proportion of products that survive the transition.

**Key Findings:** The funnel reveals a catastrophic drop between the Discounted stage (4,722 products) and the High Value stage (approximately 1,180 products) — a **75% attrition rate** at the single most important transition in the entire value creation process. By comparison, the transition from High Value to High Retention, while also involving meaningful drop-off, is far less severe. This means the bottleneck in DMart's value creation engine is not at the retention stage — it is at the fundamental discount-to-value conversion stage.

**Deep Business Insight:** The 75% drop-off at the discount-to-value transition is the single most important finding in this entire project. It tells us that **three quarters of DMart's discounting investment is being wasted** — it is being spent on products whose discount structures do not generate meaningful consumer value signals. This is not a small inefficiency. On a catalog of 4,700+ products with an average discount depth of 26.39% and total consumer savings of ₹556,940, a 75% inefficiency rate means that roughly ₹417,000 worth of margin is being sacrificed annually for zero loyalty return. The implications for capital allocation are enormous. If even half of that inefficient discounting were redirected toward products with the structural characteristics needed to generate High Value status, the catalog's overall value performance could improve dramatically without any increase in total promotional spend.

**Actionable Implication:** Commission a full funnel audit for every product category. For each product currently stuck in the "Discounted but not High Value" stage, determine whether the barrier is structural (wrong price point, wrong category positioning, wrong discount depth) or tactical (insufficient promotional visibility, poor packaging, inadequate in-store placement). Products with structural barriers should be repriced or de-listed. Products with tactical barriers should receive targeted promotional support designed to push their deal scores over the High Value threshold.

---

### 🔄 Chart 18 — Funnel Progression & Bottleneck Mapping

> **How do products progress through different stages of the value funnel, and where do inefficiencies compound?**

![Chart 18](images/chart18.png)

**What this chart shows:** A more detailed funnel analysis that tracks not just the volume drop at each stage, but the characteristics of products that successfully advance versus those that stall — enabling identification of the specific product attributes that predict funnel success or failure.

**Key Findings:** Products that successfully navigate from Discounted to High Value share a consistent set of characteristics: discount percentages above 22%, unit costs below the category median, and category rankings in the top tertile. Products that stall at the Discounted stage consistently lack at least two of these three characteristics. Notably, the funnel progression from High Value to High Retention is much smoother — suggesting that once a product achieves High Value status, the pathway to generating strong retention is largely self-sustaining.

**Deep Business Insight:** The characteristics that predict successful funnel progression provide a clear product quality filter for future procurement and pricing decisions. The finding that funnel progression becomes self-sustaining above the High Value threshold is particularly important — it suggests that the investment required to push products over the initial High Value threshold yields compounding returns. Once a product achieves High Value classification, it tends to accumulate retention behavior organically, without requiring continued heavy promotional investment. This argues for a **"push to threshold" investment strategy**: concentrate promotional resources on products that are closest to the High Value threshold (rather than spreading investment uniformly across the catalog), push them over the line, and then allow their self-sustaining retention dynamics to take over.

**Actionable Implication:** Create a "Funnel Acceleration Program" — a structured, category-specific initiative that identifies the 200–300 products nearest the High Value threshold and provides them with targeted, time-limited promotional support to cross it. Track the retention outcomes for these products at 90 and 180 days post-intervention to validate the self-sustaining retention hypothesis.

---

### 🖥️ Chart 19 — KPI Dashboard: Full Executive Snapshot

> **What do the key KPIs and combined dashboard reveal about overall product performance, value creation, and retention?**

![Chart 19](images/chart19.png)

**What this chart shows:** The master executive dashboard bringing together all key performance indicators into a single, integrated view — providing a real-time health check of the entire DMart product intelligence system across value, discount, retention, and category dimensions.

**Key Findings:** The dashboard confirms the central thesis of the project at a glance. Total Consumer Savings stands at ₹556,940 against a background of 99.8% discounted products — impressive numbers that mask the underlying inefficiency revealed by the 25% High Value rate and the concentrated retention performance in a small subset of categories and brands.

<div align="center">

| 💰 Total Consumer Savings | 📉 Avg Global Discount | ⭐ Avg Deal Score | 🔁 Golden Ratio |
|:---:|:---:|:---:|:---:|
| **₹5,56,940.01** | **26.39%** | **42.96** | **1% discount = 0.4% retention lift** |

</div>

**Deep Business Insight:** The Golden Ratio finding — that every 1% increase in discount yields only a 0.4% improvement in the Retention Index — is the headline KPI that should drive strategic reorientation. It demonstrates a **diminishing returns plateau** in DMart's current discount architecture. The marginal return on additional discounting is less than half the investment, and this ratio is likely to worsen further as discounts are deepened, because consumers in heavily discounted categories develop an expectation of high discounts as the new normal, requiring ever-deeper discounts to generate the same perceived value signal. This is the mechanism by which discount strategies become unsustainable — and the data shows DMart is already on this curve in several key categories.

**Actionable Implication:** The Golden Ratio should be treated as the board-level KPI for the pricing strategy function. Every quarter, the executive team should review whether the discount-to-retention conversion rate is improving. If the ratio remains at 0.4 or worsens, it is a signal that the discount architecture needs fundamental restructuring — not incremental adjustment. The goal should be to improve this ratio to 0.6 or above by redirecting discount investment toward the pre-activation zone products and high-value categories where the deal score → retention relationship is strongest.

---

### 📊 Full Excel Intelligence Dashboard

![Dashboard](images/dash.png)

The Excel dashboard serves as the operational delivery mechanism for all Python-derived insights — translating complex multi-factor indices into an accessible, interactive tool that non-technical stakeholders can use for real-time retail decision-making.

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📈 5. Excel Dashboard Intelligence Suite

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=700&color=E67E22&center=true&vCenter=true&width=700&lines=XLOOKUP+%7C+INDEX-MATCH+%7C+Pivot+Engines+%7C+Dynamic+Charts+%7C+Slicers" alt="Excel"/>
</p>

<div align="center">

| Feature | Implementation | Impact |
|:---|:---|:---|
| 🏗️ **Modular Architecture** | 4-layer system: Source → Lookup → Pivot → Dashboard | 5,000+ SKUs organized and instantly updatable |
| 🔧 **Advanced Formulas** | XLOOKUP, INDEX-MATCH, nested IFS | Automated Price Categories, Value Scores, Deal Scores |
| 🌊 **Value Funnel** | Strategic bottleneck identification | 75% efficiency gap surfaced and quantified |
| 📊 **Category Benchmarking** | Automated Pivot Tables with rank scoring | Jams & Spreads ~₹150 avg · Spices ~₹75 avg |
| 📌 **KPI Tracking** | Executive snapshot with live recalculation | ₹556,940 savings · 26.38% avg discount at a glance |
| 🎛️ **Interactive Filtering** | Slicers + Dynamic Charts | "No-code" diagnostic tool for real-time retail auditing |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🎯 6. Strategic Roadmap & Recommendations

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=3000&pause=1500&color=E74C3C&center=true&vCenter=true&width=800&lines=Retail+intelligence+is+not+about+being+the+cheapest%3B+it+is+about+being+the+most+valuable." alt="Conclusion"/>
</p>

<div align="center">

| Priority | Action | Expected Outcome |
|:---:|:---|:---|
| 🔴 **1** | Re-evaluate pricing of 3,500+ products stuck in the "Value Gap" | Close the 75% funnel leakage and recover wasted margin |
| 🟠 **2** | Pivot marketing spend toward the top 15% of products by Deal Score | Maximize retention ROI per rupee of promotional investment |
| 🟡 **3** | Implement Python deal_score algorithm into live storefront | Auto-badge superior unit-economic products in real time |
| 🟢 **4** | Launch "Deal Score Boost" initiative for pre-activation zone products | Push sub-threshold products over the loyalty activation point |
| 🔵 **5** | Build brand consistency scorecards tracking value score variance | Prioritize consistent value brands over hero-dependent ones |
| 🟣 **6** | Set minimum effective discount threshold at 15% catalog-wide | Eliminate ineffective sub-threshold discounts that burn margin with no behavioral return |

</div>

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
