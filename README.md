# dbt Fundamentals — Jaffle Shop & Stripe Analytics Project

This repository contains my hands-on analytics engineering project built while completing the **dbt Fundamentals** certification using **dbt Cloud** and **Snowflake**.

## Architecture & Project Structure

The project transforms raw e-commerce (`jaffle_shop`) and payment (`stripe`) tables into modular, tested dimensional models following dbt best practices:

```text
models/
├── staging/                 # 1:1 cleaning and renaming from raw sources
│   ├── jaffle_shop/
│   │   ├── _src_jaffle_shop.yml
│   │   ├── _stg_jaffle_shop.yml
|   |   ├── jaffle_shop_docs.md
│   │   ├── stg_jaffle_shop__customers.sql
│   │   └── stg_jaffle_shop__orders.sql
│   └── stripe/
│       ├── _src_stripe.yml
│       ├── _stg_stripe.yml
│       └── stg_stripe__payment.sql
└── marts/                   # Business-ready fact and dimension models
    ├── finance/
    │   └── fct_orders.sql
    └── marketing/
        └── dim_customers.sql
