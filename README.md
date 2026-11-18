
#  Mall Customer Segmentation with K-Means

> Turning 200 anonymous shoppers into **five actionable customer segments**, using unsupervised learning on income and spending behavior.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tonia-3/Customer-Segmentation-Analysis/blob/main/customer_segmentation_analysis.ipynb)
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-KMeans-orange)
![Plotly](https://img.shields.io/badge/Plotly-interactive-3f4f75)

---

## Overview

Marketing works best when it speaks to specific groups, not "the average customer." This project applies **K-Means clustering** to the Mall Customers dataset to discover natural groupings based on how much customers earn and how much they spend, then translates each group into a business-ready profile.

**What you get:**

- Exploratory analysis of demographics, income, and spending behavior
- A univariate baseline: segmenting by annual income alone
- A bivariate model: segmenting by income and spending score together
- Elbow Method analysis to choose the number of clusters
- An interactive Plotly visualization with cluster centers
- Five named segments with suggested marketing actions

---

## Dataset

**Mall Customers**: 200 customers, 5 columns.

| Column | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Gender` | Male / Female (56% / 44%) |
| `Age` | Customer age in years |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Score assigned by the mall based on spending behavior |

---

## Approach

```
Load data → EDA → Univariate clustering (Income, k=6)
                → Elbow Method
                → Bivariate clustering (Income + Spending, k=5)
                → Visualize clusters + centers → Profile segments
```

1. **Exploratory data analysis**: distribution plots, boxplots by gender, a pairplot colored by gender, group means, and a correlation heatmap.
2. **Univariate clustering**: K-Means with 6 clusters on annual income, evaluated with inertia.
3. **Elbow Method**: inertia plotted for k = 1 to 10 for both models to pick the cluster count.
4. **Bivariate clustering**: K-Means with 5 clusters on annual income and spending score, with cluster centers marked on an interactive scatter plot.

---

## Key Findings

**Exploration**

- The customer base is 56% female and 44% male.
- Average spending score is similar across genders: about 51.5 for women and 48.5 for men.
- **Age and spending score are negatively correlated (r ≈ -0.33)**: younger customers tend to spend more.
- **Income and spending score are essentially uncorrelated (r ≈ 0.01)**. High earners are not automatically high spenders, which is the reason a two-dimensional segmentation is worthwhile.

**Income-only clustering (k=6)** splits customers into income bands from roughly 24k to 128k, but every band has a nearly identical average spending score (about 49-53). Income alone says nothing about spending behavior.

---

## The Five Segments

Clustering on income and spending score reveals five distinct groups:

| Segment | Profile | Suggested strategy |
|---|---|---|
|  **High Income, High Spending** | Affluent, engaged shoppers | VIP programs, premium and luxury offers |
|  **High Income, Low Spending** | Value-conscious or under-engaged | Win-back campaigns, quality and exclusivity messaging |
|  **Moderate Income, Moderate Spending** | The typical mall customer | Broad promotions, loyalty programs |
|  **Low Income, High Spending** | Aspirational or impulsive buyers | Installment offers, trend-driven and limited-time deals |
|  **Low Income, Low Spending** | Cost-conscious shoppers | Discounts and clearance events |

---

## Getting Started

### Run in the cloud

Click the **Open In Colab** badge at the top. No setup needed.

### Run locally

```bash
git clone https://github.com/tonia-3/customer_segmentation_analysis.git
cd customer_segmentation_analysis
pip install pandas seaborn matplotlib scikit-learn plotly
jupyter notebook
```

Place `Mall_Customers.csv` in the project root, then open the notebook and run all cells.

---

## Project Structure

```
├── Mall_Customers.csv      # Dataset
├── customer_segmentation_analysis.ipynb   # Full analysis and modeling
└── README.md
```

---

## Tech Stack

`Python` · `pandas` · `seaborn` · `matplotlib` · `scikit-learn` · `Plotly`

---

## Limitations and Next Steps

- Results come from a small (200-row) dataset, so segments should be treated as exploratory.
- Age is explored but not yet used in the final clustering.
- K-Means assumes roughly spherical clusters; other algorithms may fit better.

---

## License

Released under the MIT License. See `LICENSE` for details.

---

## Author

**Tonia Chebet** · [GitHub](https://github.com/tonia-3) 

⭐ If you found this useful, consider starring the repo.
