# Nestlé (NSRGY) Stock Performance Analysis

## Table of Contents


- [Tools Used](#tools-used)
- [Project Background](#project-background)
- [Data Structure & Initial Checks](#data-structure--initial-checks)
- [Executive Summary](#executive-summary)
- [Insights Deep Dive](#insights-deep-dive)
  - [Category 1: Short-Term Trading Signals](#category-1-short-term-trading-signals-from-price-and-moving-averages)
  - [Category 2: Daily Return Behavior](#category-2-daily-return-behavior-and-risk-profile)
  - [Category 3: Volatility Dynamics](#category-3-volatility-dynamics-and-risk-management)
- [Recommendations](#recommendations)
- [Assumptions and Caveats](#assumptions-and-caveats)

## Tools Used

-Python

-Excel (for a clearer view of the dataset and minor edits)

-Tableau

For Python code used in cleaning and analyzing the data, [click here](https://github.com/Etingena/Etinosa_portfolio/blob/main/Nestlestock.ipynb)

To view the interactive Tableau dashboard for this analysis, [click here](https://public.tableau.com/views/Nestle_17486275953630/Dashboard1?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link)

## Project Background
Nestlé S.A. (Ticker: NSRGY) is a leading global food and beverage company with over 150 years in operation. Headquartered in Switzerland, the company operates in more than 180 countries and offers a diverse product portfolio, including dairy, beverages, pet care, and health science solutions. The business model is centered around strong brand equity, global distribution, and sustainable innovation. Key financial metrics of interest include share price performance, daily return behavior, and volatility—important to both internal finance teams and external investors.

As a data analyst on the finance strategy team, I was tasked with evaluating short-term trading signals, return behaviors, and risk trends using NSRGY’s stock performance data between January 2024 and April 2025.

Insights and recommendations are provided on the following key areas:

- **Category 1:** Short-Term Trading Signals from Price and Moving Averages  
- **Category 2:** Daily Return Behavior and Risk Profile  
- **Category 3:** Volatility Dynamics and Risk Management

---

## Data Structure & Initial Checks  
The dataset contained daily stock price data from January 2024 to April 2025. Key fields included:

- Date  
- Closing Price  
- 7-Day and 14-Day Simple Moving Averages (SMA)  
- Daily Returns  
- Rolling Volatility (based on a 7-day time window)

Initial checks involved handling minor missing values in SMA and rolling volatility calculations due to insufficient lookback periods (specifically, the first 6 days for 7-day rolling metrics) and ensuring consistent datetime formatting. Outlier detection showed no extreme distortions, and the dataset was deemed reliable for trend analysis.

---

## Executive Summary  

### Overview of Findings  
NSRGY’s stock experienced a prolonged decline throughout most of 2024, seeing an approximate **-27.10%** decrease from its peak in February 2024 to its low in January 2025. This was followed by a sharp and sustained recovery in early 2025, rebounding by approximately **+32.05%** by April 2025. During the downtrend, moving averages acted as resistance, while in the recovery phase they served as dynamic support. Although daily returns were mostly stable, volatility (measured as daily standard deviation) spiked during market transitions—especially in September 2024 and March 2025.

These insights provide clarity for investment strategy, particularly for teams involved in technical trading, portfolio risk management, and capital planning. While this analysis focuses on technical indicators, it's crucial to acknowledge that external factors such as global economic conditions, changes in consumer spending habits, commodity price fluctuations, and company-specific news (e.g., earnings reports, product innovations, M&A activities) likely underpinned these price movements. Future analyses could integrate fundamental drivers to provide a more holistic understanding.

[image alt](https://github.com/Etingena/Etinosa_portfolio/blob/main/Dashboard%201%20(5).png)

---

## Insights Deep Dive  

### Category 1: Short-Term Trading Signals from Price and Moving Averages  

**Main Insight 1: Bearish Trend Dominated Most of 2024.**

From **February 27, 2024**, the 7-day SMA crossed below the 14-day SMA—a classic bearish indicator. The stock price declined from ~$107 to a low near $78 by January 2025, consistently staying below both SMAs. This sustained pattern reflected negative sentiment and momentum, suggesting a prolonged period of selling pressure possibly influenced by broader market corrections or specific company performance challenges.

**Main Insight 2: Bullish Reversal Took Hold in Early 2025.**

In **January 16, 2025**, a "golden cross" occurred as the 7-day SMA moved above the 14-day SMA. A "golden cross" is a technical chart pattern indicating the potential for a major rally, where a short-term moving average crosses above a longer-term moving average. The stock price rallied from $78 to over $103 by April 2025, marking a clear trend reversal. The closing price consistently held above both SMAs, signaling buyer strength, potentially driven by improved market sentiment or positive company developments.

**Main Insight 3: Moving Averages Served as Key Support/Resistance.**

During the downtrend, the SMAs consistently capped price rebounds, acting as resistance levels. In contrast, during the rally, they served as dynamic support zones, with prices often bouncing off these lines. These dynamics suggest opportunities for trend-following and mean-reversion strategies. Historical reliability of these crossovers for NSRGY could be further validated by backtesting their performance over longer periods.

![image alt](https://github.com/Etingena/Etinosa_portfolio/blob/main/Sheet%201%20(2).png)

---

### Category 2: Daily Return Behavior and Risk Profile  

**Main Insight 1: Returns Clustered Near Zero with Mild Negative Bias.**

Most daily returns hovered around a mean of **-0.08%**, indicating generally low volatility with a slight downward tilt. This suggests relative stability with occasional drawdowns, a typical characteristic of a large, mature consumer staples company.

**Main Insight 2: Moderate Risk Window Captured by Return Tails.**

While daily changes were predominantly small, returns occasionally ranged from -5.5% to +5.5%. Approximately **98.5%** of all daily returns fell within this range. Returns outside this range (e.g., extreme positive or negative movements exceeding ±5.5%) occurred very infrequently, accounting for roughly 1.5% of observations. This information is critical for setting realistic stop-loss thresholds and preparing for infrequent, but significant, outlier events.

**Main Insight 3: Slight Negative Skewness in Return Distribution.**

The histogram showed a mild leftward skew (skewness coefficient of approximately -0.25), implying that sharper negative returns were slightly more common and larger in magnitude than large positive ones. This characteristic is important for stress testing and portfolio simulations, suggesting that while daily returns are often stable, the risk of larger single-day losses is marginally higher than equivalent single-day gains.

![image alt](https://github.com/Etingena/Etinosa_portfolio/blob/main/Sheet%202.png0)

---

### Category 3: Volatility Dynamics and Risk Management  

**Main Insight 1: Volatility Was Not Constant—It Clustered.**

Volatility, measured as the 7-day rolling daily standard deviation, oscillated between approximately **0.005 (0.5%) and 0.030 (3.0%)** over the 16-month period, confirming classic clustering behavior seen in financial time series. This implies that periods of high volatility tend to be followed by more high volatility, and vice versa. Annualized, a 0.030 daily standard deviation would translate to approximately 0.476 (47.6%) annual volatility ($0.030 \times \sqrt{252}$).

**Main Insight 2: Sharp Volatility Spike Aligned with September 2024 Selloff.**

The highest volatility occurred around **September 1, 2024**, coinciding with the most intense phase of the price decline. This correlation suggests that the selloff was accompanied by increased uncertainty and larger daily price swings, elevating overall risk levels for investors.

**Main Insight 3: Renewed Volatility During Q1 2025 Rally.**

While the recovery brought significant gains, it also came with higher volatility. March 2025 saw volatility resurge past 0.025, reflecting increased trading activity and potentially a mix of profit-taking, new capital inflows, and shifting market expectations amid the bullish sentiment. This indicates that while the trend was upward, the path was not smooth, and market participants experienced notable price fluctuations.

![image alt](https://github.com/Etingena/Etinosa_portfolio/blob/main/Sheet%203%20(1).png)

---

## Recommendations

Based on the findings above, the following actions are recommended:

- The trading team should monitor moving average crossovers closely, specifically implementing alerts for the 7-day SMA crossing the 14-day SMA. A sustained crossover (e.g., remaining crossed for 3 consecutive days) can be used to refine entry/exit strategies for short-term trades, as they clearly preceded trend shifts in 2024 and 2025.
- The risk management team should revise stop-loss placements using the observed daily return range of ±5.5%. For instance, consider setting stop-loss orders at approximately 4-5% below the entry price, adjusting based on the specific trade strategy and risk tolerance. This ensures they are neither too tight (leading to premature exits) nor too lenient (leading to excessive losses), improving risk-adjusted returns.
- The finance team should treat periods of exceptionally low volatility (e.g., November 2024–January 2025, where the 7-day rolling standard deviation was below 0.01) as potential precursors to breakout moves. These windows may provide strategic points for capital deployment (e.g., accumulating positions before a confirmed uptrend) or hedging (e.g., reducing exposure before a potential downtrend, especially if fundamental indicators are weak).
- Portfolio managers should account for the slight negative skew in daily returns when modeling future performance scenarios. This implies that Value-at-Risk (VaR) or Conditional Value-at-Risk (CVaR) models should explicitly incorporate this asymmetry, potentially by using historical simulation or skewed distributions, to provide more robust downside risk planning and capital allocation decisions.

---

## Assumptions and Caveats

- Missing SMA values for the first 13 days, and missing 7-day rolling volatility for the first 6 days of the dataset, were excluded due to insufficient data points for accurate computation. This did not significantly impact the overall trend analysis which covers a 16-month period.
- Data for January 1 and public holidays were naturally absent, as trading did not occur. These were not imputed.
- Volatility was calculated using a rolling window of **7 days**. Different window sizes (e.g., 14-day, 21-day) may yield different short-term sensitivity and highlight different aspects of volatility dynamics. A sensitivity analysis could be performed in future work to assess the impact of different window choices.
- Interpretations of moving averages and volatility assume a technical analysis perspective and may not fully reflect fundamental shifts. A comprehensive investment strategy should integrate both technical and fundamental analysis to capture underlying drivers and broader market context.

---
