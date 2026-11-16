# E-Commerce Delivery Performance & Customer Satisfaction

A portfolio project using the Olist Brazilian E-Commerce Public Dataset to investigate delivery performance and customer satisfaction through Python-based exploratory data analysis and statistical inference.

## Business questions
1. How long do orders take to reach customers, and how variable are delivery durations?
2. How often do delivered orders arrive before, on, or after the estimated delivery date?
3. Do customer review scores differ across delivery-performance groups?
4. Are observed differences statistically and practically meaningful?

## Repository structure

```text
ecommerce-delivery-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/                 # Put downloaded Olist CSV files here
│   └── processed/           # Generated analysis-ready data
├── notebooks/
│   ├── 01_data_quality_and_understanding.ipynb
│   ├── 02_delivery_performance_eda.ipynb
│   ├── 03_customer_satisfaction_analysis.ipynb
│   └── 04_statistical_hypothesis_testing.ipynb
├── outputs/
│   └── figures/
└── reports/
    └── executive_summary_template.md
```

## Dataset setup

Download the Olist Brazilian E-Commerce Public Dataset from Kaggle:

https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Place the required CSV files in `data/raw/`. At minimum:
- `olist_orders_dataset.csv`
- `olist_order_reviews_dataset.csv`

The dataset is not bundled in this ZIP. Review Kaggle's dataset terms before redistributing data.

## Environment setup

```bash
python -m venv .venv
source .venv/bin/activate        # macOS/Linux
# .venv\\Scripts\\activate   # Windows

pip install -r requirements.txt
```

Open the notebooks in Jupyter or upload the repository to Google Colab. Run notebooks from the repository root so relative paths resolve.

## Notebook roadmap

| Notebook | Purpose | Status |
|---|---|---|
| 01 — Data quality and understanding | Structure, uniqueness, missingness, status-based missingness | Prepared |
| 02 — Delivery performance EDA | Duration, descriptive statistics, histogram, boxplot, IQR, punctuality | Prepared; rerun and validate against CSV |
| 03 — Customer satisfaction analysis | Review data quality, joins, review-score segmentation | Starter template |
| 04 — Statistical hypothesis testing | Hypotheses, test selection, p-values, confidence intervals, effect sizes | Starter template |

## Important metric definitions

**Delivery duration** is the elapsed time from purchase to customer delivery. It is not the same as lateness.

**Calendar-date delay** is calculated as:

`actual_delivery_calendar_date - estimated_delivery_calendar_date`

The current analysis assumes the estimated delivery field represents a promise to deliver by the end of that calendar date. Confirm and document this business definition before reporting punctuality KPIs.

Do not impute missing actual delivery timestamps using estimated delivery dates. An estimate is not evidence of the actual delivery time.

## Reproducibility and reporting

- Run each notebook from top to bottom.
- Do not treat saved historical outputs as current verified results.
- Keep the raw data unchanged.
- State the denominator for every percentage.
- Document exclusions and missing-data handling.
- Report effect sizes and uncertainty alongside p-values.
- Do not infer causation from observational associations.

## Portfolio status

This repository is a structured working project. Notebooks 01 and 02 contain the initial analysis workflow and must be rerun against the downloaded CSV files before publishing. Notebooks 03 and 04 are guided starter templates, not completed analyses.
