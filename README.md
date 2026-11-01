# Safety Stock and Reorder Point Under Uncertain Demand

Final project for the SoftUni course *Math Concepts for Developers*
(Data Engineering and Analytics track), November 2026.

## The problem

An online retailer of bathroom and kitchen products keeps part of its
assortment in its own warehouse. For every item the supplier needs a known
number of days to deliver, while the daily demand is random. Every automatic
ordering system has to answer one question:

> **At which stock level should the next order be placed, so that the product
> (almost) never runs out before the supplier delivers, without tying up more
> money in stock than necessary?**

That stock level is called the **reorder point**, and the part of it that only
exists to protect against uncertainty is the **safety stock**. The analysis
is built step by step in `safety_stock_reorder_point.ipynb`.

## Data

The retailer's real sales export could not be published, so the notebook works
on **synthetic daily sales** for three products, A, B and C, from 2026-04-01 to
2026-10-31. `data/generate_daily_sales.py` produces them with a fixed random
seed from two simple random experiments per day, a Bernoulli trial for "does
the product sell today?" and a probability table for the units sold on such a
day, with parameters set to match the statistical profile of three real
products. `data/daily_sales.csv` is its output, with columns `sale_date`,
`product` and `units`; days without sales are not listed and are treated as
zero. Running the script again reproduces the file exactly.

## How to run

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code or Jupyter with a Python 3.11 or newer kernel
that has the packages above. Tested with Python 3.14 on Windows 11.

## Status

Work in progress.

## Author

Martin Marchev