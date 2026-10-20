# Fuzzy-factory-sql-analysis

# E-commerce Channel, Conversion & Profitability Analysis (MySQL)

## Objective
Analyze 3 years of data from an online toy retailer (Maven Fuzzy Factory) to understand
growth, marketing channel performance, device conversion, product profitability and refunds.

## Dataset
Maven Analytics Toy Store E-Commerce Database (public domain): 472,871 website sessions,
32,313 orders, 40,025 order items, 1,731 refunds, 4 products (Mar 2012 - Mar 2015).
The pageviews table was not used.

## Tools
MySQL 8: joins, CTEs, window functions (LAG), subqueries, views, indexing

## Data validation
- No orphan records: every order links to a session, every item to an order, every refund
  to an item
- Order totals reconcile exactly with the sum of their line items (0 mismatches)
- Trend queries exclude the partial final month (Mar 2015); 2012 (Mar-Dec) and
  2015 (Jan-Feb) are partial years

## Key findings
1. Business: $1.94M revenue, 6.8% conversion, 62.7% gross margin; refunds were 4.4% of revenue.
2. Growth: conversion rose from 4.14% (2012) to 7.22% (2014); revenue per session from
   $2.07 to $4.61. Revenue grew ~2.7x from 2013 to 2014.
3. Channels: paid nonbrand search drives ~72% of sessions and ~70% of revenue but converts
   below brand, organic and direct (6.65% vs 7.15-7.78%). Paid social converts at 3.21%.
4. Device gap: desktop converts 2.5x-3.5x better than mobile in four channels (nonbrand:
   8.01% vs 3.17%) and ~6x better in paid social.
5. Products: Mr. Fuzzy earns 62.5% of revenue; newer products have higher margins
   (68% vs 61%).
6. Refunds: Mr. Fuzzy's refund rate spiked to 10.6% in 2014-Q3 (vs ~3.5% baseline),
   about 200 excess refunds (~$10K).

## Recommendations
1. Shift paid nonbrand bids toward desktop; audit the mobile experience.
2. Review paid social spend, which converts at about half the rate of other channels.
3. Promote higher-margin products through cross-sell.
4. Investigate the 2014-Q3 refund spike and add a refund-rate alert.

## Limitations
No ad-spend data, so ROI/CAC could not be calculated. Findings show associations,
not proven causes.

## How to run
1. Download the dataset from Maven Analytics
2. Run setup.sql (update the CSV file paths)
3. Run analysis.sql
