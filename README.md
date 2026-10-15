# Coupon Acceptance Analysis

## Table of Contents
- [Overview](#overview)
- [Data Preparation](#data-preparation)
- [Key Findings](#key-findings)
- [Bar Coupon Analysis](#bar-coupon-analysis)
- [Coffee House Analysis](#coffee-house-analysis)
- [Hypothesis](#hypothesis)
- [Recommendation](#recommendation)
- [Practical Application 1 Jupyter Notebook](./Practical%20Application%201%20Jupyter%20Notebook.ipynb)

## Overview

This project explores driving coupon survey data to understand what factors are associated with coupon acceptance. Exploratory data analysis was performed using Python, pandas, Matplotlib, and Seaborn. After reviewing data quality, the analysis examined overall coupon acceptance and then focused on Bar and Coffee House coupons. Customer behavior, demographics, and driving context were compared using acceptance rates and visualizations. The strongest patterns suggest that customers are more likely to accept coupons when the offer matches their existing venue preferences and is delivered in a relevant context, particularly at an appropriate time of day.

## Data Preparation

The dataset contains **12,684 observations and 26 variables**.

Key preparation steps included:

- Investigating missing values and duplicate records
- Reviewing categorical variables and unusual values
- Identifying `car` as approximately 99% missing
- Identifying `toCoupon_GEQ5min` as a constant variable
- Using `Y` as the target:
  - `1` = Accepted
  - `0` = Rejected

Overall coupon acceptance was **56.8%**.

## Key Findings

| Coupon Type | Acceptance Rate |
|---|---:|
| Carry out & Take away | **73.5%** |
| Restaurant(<20) | **70.7%** |
| Coffee House | **49.9%** |
| Restaurant(20-50) | **44.1%** |
| Bar | **41.0%** |

Acceptance varied substantially by coupon type, suggesting that both customer preferences and the nature of the offer matter.

## Bar Coupon Analysis

Bar coupons had an overall acceptance rate of **41.0%**.

Frequent bar visitors were significantly more receptive:

| Group | Acceptance |
|---|---:|
| Bar visits ≤3/month | 37.1% |
| Bar visits >3/month | **76.9%** |
| Bar >1/month and age >25 | **69.5%** |
| Bar >1/month, no kid passenger, selected occupation criteria | **71.3%** |

**Finding:** Previous bar-going behavior was one of the strongest indicators of Bar coupon acceptance.

## Coffee House Analysis

Coffee House coupons had an overall acceptance rate of **49.9%**.

### Driving Context

| Factor | Highest Acceptance |
|---|---:|
| Weather: Rainy | 52.2% |
| Temperature: 80°F | 53.0% |
| Time: 10AM | **64.1%** |
| Time: 2PM | **54.8%** |

Time of day showed a particularly clear relationship with acceptance.

### Visit Frequency + Timing

The strongest Coffee House pattern emerged when existing customer behavior was combined with coupon timing:

| Customer / Context | Acceptance |
|---|---:|
| Regular visitor + 10AM/2PM | **77.4%** |
| Regular visitor + other time | 57.7% |
| Not regular + 10AM/2PM | 43.4% |
| Not regular + other time | **28.8%** |

Regular Coffee House visitors receiving coupons at typical coffee-consumption times had the highest observed acceptance.

## Hypothesis

> **Customers are more likely to accept coupons when the offer aligns with both their existing venue preferences and the context in which the coupon is presented.**

For Bar coupons, visit frequency was strongly associated with acceptance. For Coffee House coupons, combining regular Coffee House behavior with relevant timing produced the strongest result.

## Recommendation

Coupon targeting should prioritize behavioral relevance and contextual timing rather than distributing offers uniformly.

For example, Coffee House coupons could be targeted toward regular visitors around **10AM or 2PM**, where this dataset showed an acceptance rate of **77.4%**.

These findings demonstrate association, not causation. Statistical testing or predictive modeling would be useful next steps to determine which factors remain significant when considered together.
