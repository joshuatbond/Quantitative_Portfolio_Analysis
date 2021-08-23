# Quantitative Portfolio Analysis

## Background

The objective of this project was to help determine which portfolio is performing the best across multiple areas: volatility, returns, risk, and Sharpe ratios using quatitative analysis techniques with Python and Pandas.

I was tasked with creating a tool (an analysis notebook) that analyzes and visualizes the major metrics of the portfolios across all of these areas, and determine which portfolio outperformed the others. I was given the historical daily returns of several portfolios: some from a hypothetical firm's algorithmic portfolios, some that represent the portfolios of famous "whale" investors like Warren Buffett, and some from the big hedge and mutual funds. I was then to use this analysis to create a custom portfolio of stocks and compare its performance to that of the other portfolios, as well as the larger market ([S&P 500 Index](https://en.wikipedia.org/wiki/S%26P/TSX_60)).

## Prepare the Data

The first order of business was to read and clean several CSV files for analysis. The CSV files include whale portfolio returns, algorithmic trading portfolio returns, and S&P 500 historical prices.

1. Use Pandas to read the following CSV files as a DataFrame. Be sure to convert the dates to a `DateTimeIndex`.

   * `whale_returns.csv`: Contains returns of some famous "whale" investors' portfolios.
   * `algo_returns.csv`: Contains returns from the in-house trading algorithms from Harold's company.
   * `sp500_history.csv`: Contains historical closing prices of the S&P 500 Index.
2. Detect and remove null values.
3. If any columns have dollar signs or characters other than numeric values, remove those characters and convert the data types as needed.
4. The whale portfolios and algorithmic portfolio CSV files contain daily returns, but the S&P 500 CSV file contains closing prices. Convert the S&P 500 closing prices to daily returns.
5. Join `Whale Returns`, `Algorithmic Returns`, and the `S&P 500 Returns` into a single DataFrame with columns for each portfolio's returns.

## Conduct Quantitative Analysis

Analyze the data to see if any of the portfolios outperform the stock market (i.e., the S&P 500). Under each subsection are the questions I sought to answer.

### Performance Analysis

1. Calculate and plot daily returns of all portfolios.
2. Calculate and plot cumulative returns for all portfolios. Does any portfolio outperform the S&P 500?

### Risk Analysis

1. Create a box plot for each of the returns.
2. Calculate the standard deviation for each portfolio.
3. Determine which portfolios are riskier than the S&P 500.
4. Calculate the Annualized Standard Deviation.

### Rolling Statistics

1. Calculate and plot the rolling standard deviation for all portfolios using a `21-day` window.
2. Calculate and plot the correlation between each stock to determine which portfolios may mimick the S&P 500.
3. Choose one portfolio, then calculate and plot the `60-day` rolling beta between it and the S&P 500.
4. Calculate the exponentially weighted moving average (`ewm`) with a 21-day half-life.

### Sharpe Ratios

1. Using the daily returns, calculate and visualize the Sharpe ratios using a bar plot.
2. Determine whether the algorithmic strategies outperform both the market (S&P 500) and the whales portfolios.

## Create a Custom Portfolio

As a final objective of this project, I wanted to create a custom portfolio of 3 stocks and measure its performance against the whale portfolios and algorithmic strategies.

Using the [Google Sheets](https://docs.google.com/spreadsheets/) built-in Google Finance function, I downloaded data for the following 3 stocks to create this custom portfolio:

1. `TSM` - [Taiwan Semiconductor Manufacturing Company, Limited](https://en.wikipedia.org/wiki/TSMC)
2. `AMD` - [Advanced Micro Devices, Inc.](https://en.wikipedia.org/wiki/Advanced_Micro_Devices)
3. `DIS` - [Disney](https://en.wikipedia.org/wiki/The_Walt_Disney_Company)

I then performed the following analyses:

* Calculate the Annualized Standard Deviation.
* Calculate and plot rolling `std` with a `21-day` window.
* Calculate and plot the correlation.
* Calculate and plot beta for the custom portfolio compared to the S&P 500.
* Calculate the Sharpe ratios and generate a bar plot.

---

## Resources

* [Pandas API Docs](https://pandas.pydata.org/pandas-docs/stable/reference/index.html)
* [Exponential weighted function in Pandas](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.ewm.html)
* [`GOOGLEFINANCE` function help](https://support.google.com/docs/answer/3093281)
* [Supplemental Guide: Fetching Stock Data Using Google Sheets](../../../01-Lesson-Plans/04-Pandas/Supplemental/googlefinance_guide.md)
