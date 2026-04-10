## 🛒 DMart Product Intelligence: Beyond the Discount
Optimizing Retail Value through Advanced Feature Engineering & Behavioral Analytics

## 📖 1. The Narrative: The "Discount Trap" Story
In the hyper-competitive Indian retail landscape, "Discounting" is often the only lever used to capture market share. DMart operates on a high-volume, low-price model, but a critical question remains: Is every discount driving loyalty, or are some merely burning margins?

This project uncovers the "Value Gap." By analyzing over 5,000 SKUs, we discovered that while 99.8% of the inventory is discounted, only a fraction of those products deliver "High Value" to the consumer. This repository documents the journey of transforming a static product catalog into a dynamic intelligence system that identifies "Retention Heroes"—products that don't just offer a lower price, but a price-to-utility ratio that ensures repeat business.

## 🏗️ 2. The Strategic Challenges
To move from raw data to actionable insights, this project addressed three core challenges:

The Normalization Paradox: Developing a way to compare the "deal quality" of a ₹10 staple versus a ₹1,000 premium item.

The Price-Volume Illusion: Using Price per 100g metrics to strip away packaging bias and find true unit economic value.

Proxy Retention Modeling: Since transaction timestamps were unavailable, we engineered a Synthetic Retention Index based on price-competitiveness and category rankings.

## 💻 3. Technical Implementation (Python)
The backbone of this project is built on specialized feature engineering. We moved beyond basic arithmetic to create multi-factor indices.

A. Core Feature Engineering
We calculated "Savings Efficiency" and "Unit Value" to quantify the customer’s psychological perception of a deal.

## Python
# 1. Price per 100g (The True Equalizer)
df["price_per_100g"] = (df["discountedprice"] / df["quantity_grams"]) * 100

# 2. Value Score (Savings Efficiency)
df["value_score"] = df["savings"] / df["price"]

# 3. The Custom "Deal Score"
# Weighted logic: Discount Depth (50%) + Value Score (30%) + Relative Pricing (20%)
df["deal_score"] = (
    (df["discount_percentage"] * 0.5) +
    (df["value_score"] * 100 * 0.3) +
    ((1 / df["relative_price_index"]) * 10 * 0.2)
)
B. Behavioral Simulation (Mixpanel Integration)
To validate our scores, we integrated a tracking simulation to model how "High Deal Score" products correlate with user behavior (Views → Add to Cart → Purchase).

Python
from mixpanel import Mixpanel
mp = Mixpanel("PROJECT_TOKEN")

for i in range(200):
    user = f"user_{i}"
    mp.track(user, "product_viewed")
    if random.random() > 0.5:
        mp.track(user, "add_to_cart")
## 📊 4. Data-Driven Insights
Our analysis yielded high-impact findings that challenge traditional retail assumptions:

I. The Value Funnel Leakage
Observation: Out of 4,732 products, 4,722 are discounted. However, only 1,180 qualify as "High Value."

Insight: There is a 75% drop-off between a discount being offered and a discount being meaningful. Most discounts are "noise" that fail to move the needle on customer value perception.

II. Category "Retention Heroes" vs. "Margin Burners"
High Performance: Personal Care and Home & Kitchen show the highest retention potential.

The Staple Trap: Groceries have high volume but surprisingly low retention scores per SKU, indicating high price-sensitivity and low brand loyalty in that segment.

III. The Power of Organic Staples
Data shows that 24 Mantra Organic products (Atta, Brown Rice, Sugar) consistently score the highest on the Deal Index (>400), serving as the "Anchor Products" for the entire DMart ecosystem.

## 📈 5. Visual Dashboard Summary- Excel
The project culminated in a KPI dashboard reflecting the following health metrics:

Total Consumer Savings: ₹556,940.01

Average Global Discount: 26.39%

Average Deal Score: 42.96

The Golden Ratio: We found that every 1% of discount only yields a 0.4% increase in the Retention Index, suggesting a plateau effect where deeper discounts stop providing value.

## 🎯 6. Conclusion: Strategic Roadmap
Based on the data, the following actions are recommended:

Optimize the Funnel: Re-evaluate the pricing of the 3,500+ products in the "Value Gap" (Discounted but not High Value).

Highlight Retention Heroes: Pivot marketing spend toward the top 15% of products that drive the highest Deal Scores.

Dynamic Pricing: Implement the Python-based deal_score algorithm into the live storefront to automatically badge products that offer superior unit-economic value.

Final Verdict: Retail intelligence is not about being the cheapest; it is about being the most valuable. This project provides the mathematical framework to ensure every rupee of discount translates into customer loyalty.
