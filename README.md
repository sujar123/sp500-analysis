# S&P 500 Financial Time-Series Analysis

## Overview

This project analyzes historical monthly S&P 500 index data using Python and statistical methods to study long-term market growth, returns, volatility, extreme declines, and the relationship between market returns and interest-rate changes.

The analysis focuses on describing historical market behavior and identifying patterns in the data. It does not attempt to predict future prices.

## Key Findings

- The S&P 500 showed substantial long-term nominal price growth across the historical period analyzed.
- Monthly returns were not normally distributed. The Shapiro-Wilk test rejected the normality assumption with a p-value below 0.001.
- Monthly returns had excess kurtosis of approximately 16.75, indicating that unusually large gains and losses occurred more often than a normal distribution would predict.
- Average annualized volatility was approximately 11.84%.
- The highest rolling annualized volatility was approximately 66.68%, occurring around October 1932.
- The S&P 500 produced positive returns in 101 of 154 complete years analyzed.
- The strongest annual return was 46.2% in 1933.
- The weakest annual return was -45.6% in 1931.
- There were 30 months with returns below -10%.
- The analysis found no statistically significant association between monthly S&P 500 returns and monthly changes in long-term interest rates.
- The relationship analysis produced a Pearson correlation of -0.0323 and a regression R² of 0.0010, indicating an extremely weak linear relationship in this dataset.

## Methods

The notebook uses the following analysis steps:

1. Cleaned and sorted the historical S&P 500 dataset by date.
2. Calculated monthly index changes and percentage returns.
3. Calculated 50-month and 200-month simple moving averages to examine medium- and long-term trends.
4. Calculated rolling 12-month volatility using the standard deviation of monthly returns.
5. Annualized volatility by multiplying the rolling standard deviation by the square root of 12.
6. Examined the distribution of monthly returns using a histogram and Q-Q plot.
7. Applied the Shapiro-Wilk test to test whether monthly returns followed a normal distribution.
8. Calculated annual returns using the final index value from each complete year.
9. Identified crash months as months with returns below -10%.
10. Compared monthly S&P 500 returns with monthly changes in long-term interest rates using Pearson correlation, Spearman correlation, and linear regression.

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- SciPy
- Google Colab
- GitHub

## Important Limitations

- The dataset contains monthly index-level data, so daily and intraday market movements are not analyzed.
- The S&P 500 values represent price changes and do not include reinvested dividends.
- Some early historical values may be reconstructed index data from before the modern S&P 500 existed.
- Correlation does not prove causation. Other economic factors may influence both interest rates and market returns.
- The crash-month threshold of -10% is a chosen definition; different thresholds could produce different results.
- The analysis describes historical behavior and should not be interpreted as financial advice or a guarantee of future performance.

## Repository Contents

- `SP500_Analysis.ipynb` — Complete analysis notebook containing the data preparation, statistical analysis, visualizations, and findings.
- `README.md` — Project overview, methodology, results, and limitations.

## Data Source

The analysis uses the public [S&P 500 dataset from the datasets GitHub organization](https://github.com/datasets/s-and-p-500).

The dataset contains monthly S&P 500 index values and related economic variables beginning in 1871. It is based primarily on historical data prepared by Robert Shiller and extends recent price data using the Federal Reserve Bank of St. Louis (FRED).

The analysis uses the `Date`, `SP500`, and `Long Interest Rate` columns.
