# Data Setup

This project uses the **Brazilian E-Commerce Public Dataset by Olist**, available publicly on Kaggle:

https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

The raw dataset is not included in this repository. To reproduce the analysis, download the dataset from Kaggle and place the required CSV files in a `raw_data/` directory at the repository root.

## Required Raw Files

The ETL pipeline uses the following files:

```text
raw_data/
├── olist_orders_dataset.csv
├── olist_order_reviews_dataset.csv
├── olist_order_items_dataset.csv
├── olist_order_payments_dataset.csv
├── olist_customers_dataset.csv
├── olist_products_dataset.csv
├── olist_sellers_dataset.csv
└── product_category_name_translation.csv
```

The Olist geolocation dataset is not required for this analysis.

## Processed Data

Running [`ETL.ipynb`](../ETL.ipynb) creates the final analytical dataset:

```text
data/
└── clean_sales_data.csv
```

`clean_sales_data.csv` contains the **31,004-order analytical cohort** used by the statistical analysis notebook.

The processed CSV is generated locally and is not committed to the repository.

## Expected Project Layout

Before running the ETL notebook, the relevant directories should look like:

```text
olist-discount-ratings-analysis/
├── ETL.ipynb
├── olist_discount_ratings_analysis.ipynb
├── raw_data/
│   ├── olist_orders_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_customers_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_sellers_dataset.csv
│   └── product_category_name_translation.csv
```

After placing the raw files in `raw_data/`, run `ETL.ipynb` to generate `data/clean_sales_data.csv`, then run `olist_discount_ratings_analysis.ipynb`.
