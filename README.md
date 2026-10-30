# Customer Segmentation for an Online Retailer

Segments 4,338 customers by their purchasing behaviour so a retailer can target marketing to specific groups of customers instead of using a one-size-fits-all approach.

## Business Problem
The retailer currently treats all customers the same way during marketing. That means the retailer is overspending on customers who would gave stayed anyways and under-investing in the most valuable or at-risk ones. **Goal**: Group customers into segments for a markerting team to act on. 

## Approach
1. **Cleaning**: removed rows with no customer ID (24.9%), cancelled invoices, and non-positive quantities/prices, leaving 397,884 valid transactions (~73%). Capped extreme bulk orders (IQR) instead of deleting genuine purchases.
2. **Features**: Recency, Frequency, Monetrary value and Average order value per customer, standardised before clustering.
3. **Model**: K-Means and Hierarchical clustering (ward linkage), with k chosen using the elbow method, dendrogram, and silhouette score.

## Results
| Model | k | Score |
| --- | --- | --- |
| K-Means | 5 | 0.477 |
| Hierarchical (ward) | 5 | 0.384 |

K-Means was ultimately chosen for its higher score.


| Segment | Recommended action |
|---|---|
| Top-tier highest spenders | Dedicated account management, early access |
| Recent high spenders | Loyalty rewards, targeted upsell |
| Occasional high spenders | Reminders to shop more often |
| Active recurring customers | Promotions, cross-sell |
| At-risk customers | Automated win-back emails with discounts |

## Limitations and next steps
- The tier, "Top-tier highest spender", only has 9 customers, which is too few to confirm if its stable
- Only RFM features were used. Using product mix and return rate may reveal more about customers' spending behaviour
- Next: test segment stability across 2 halves of the year.
