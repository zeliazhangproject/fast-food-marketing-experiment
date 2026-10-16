# Fast Food Marketing Experiment

## Overview

This project compares three promotion strategies used across fast-food store locations to understand whether the promotions lead to different sales performance.

I first checked whether the promotion groups looked reasonably balanced across store characteristics, then compared sales using ANOVA and Tukey HSD. Because each store appears across multiple weeks, I also used a mixed-effects model with store-level random effects to account for repeated observations.

## Business Question

Which promotion strategy performs best based on weekly sales?

## Dataset

The dataset contains weekly sales observations for stores assigned to one of three promotion strategies.

Key fields used in the analysis include:

- `Promotion`
- `SalesInThousands`
- `MarketID`
- `MarketSize`
- `LocationID`
- `AgeOfStore`
- `week`

Source: Kaggle — Fast Food Marketing Campaign A/B Test

## Analysis

The project includes:

- Data-quality checks
- Promotion-group distribution checks
- Market-size balance check
- Store-age balance check
- One-way ANOVA
- Tukey HSD pairwise comparisons
- Mixed-effects regression with store-level random intercepts
- Week fixed effects
- Business interpretation

## Main Findings

The overall ANOVA shows that sales are not the same across all three promotion groups.

Tukey HSD shows that Promotion 2 performs significantly worse than Promotions 1 and 3, while the difference between Promotions 1 and 3 is not statistically significant.

Because each store contributes multiple weekly observations, I also fit a mixed-effects model using `LocationID` as a random effect.

After accounting for store-level differences and week:

- Promotion 2 is estimated to generate about **$10.77K lower weekly sales than Promotion 1**.
- Promotion 3 is about **$2.74K lower than Promotion 1**, but the difference is not statistically significant.
- Week effects are not statistically significant.

## Business Recommendation

Based on sales performance, I would not recommend Promotion 2.

Promotions 1 and 3 perform similarly, so the final choice between them should depend on additional business factors such as campaign cost, profit margin, and operational complexity.

## Tools

- Python
- pandas
- NumPy
- scipy
- statsmodels
- matplotlib
- Jupyter Notebook

## Skills Demonstrated

- A/B and multi-group experiment analysis
- Randomization and balance checks
- ANOVA
- Tukey HSD
- Mixed-effects modeling
- Repeated-measures analysis
- Statistical interpretation
- Business decision-making

## Repository Structure

```text
fast-food-marketing-experiment/
├── marketing_campaign_analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

Install the required packages:

```bash
pip install -r requirements.txt
```

Then open `marketing_campaign_analysis.ipynb` in Jupyter Notebook, JupyterLab, or VS Code and run the notebook from top to bottom.

## Data

The raw dataset is not included in this repository.

You can access the dataset from Kaggle:

https://www.kaggle.com/datasets/chebotinaa/fast-food-marketing-campaign-ab-test
