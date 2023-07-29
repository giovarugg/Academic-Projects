# **Statistical Tool for Optimal Trading Parameters**

This Python script is a tool that computes **stop loss** and **soft target** values for trading positions using the **Average True Range (ATR)** indicator. 
The script utilizes the pandas, yfinance, numpy, and tabulate libraries to fetch financial data, calculate ATR, and display the results in a tabular format.


## **Requirements**

Before using this script, make sure you have the following libraries installed:
* pandas
* yfinance
* numpy
* tabulate


## **How to Use**
1. Import the required libraries and the script.
2. Define the function **parameters(ticker, interv, order)** to calculate stop loss and soft targets for a given trading position.
* **ticker**: The stock or financial instrument's ticker symbol you want to analyze.
* **interv**: The interval of data you want to consider. For example, '1d' for daily data, '1wk' for weekly data, or '1mo' for monthly data.
* **order**: The type of order you want to calculate for. Use 'market' for market order or 'limit' for limit order.

3. Call the function with your desired parameters. For example, **parameters('EURUSD=X', '1d', 'limit')**


## **How it Works**

The script fetches historical data for the specified ticker from Yahoo Finance, starting from '2018-01-01' and at the given interval.

It calculates the **True Range (TR)** for each period, which is the maximum of three values:
* High - Low
* Absolute value of High - Previous Close
* Absolute value of Low - Previous Close

The **Average True Range (ATR)** is calculated using the rolling mean of the True Range over a period of 14 days.

If the order is '**market**', the script fetches minute data for the ticker to get the current market price.
If the order is '**limit**', the user is prompted to input their desired limit price.

Stop loss and soft target values are computed for both long and short positions based on the ATR:
* **sl_long**: Stop Loss for a long position at 1 ATR below the entry price.
* **st_long**: Soft Target for a long position at 3 ATR above the entry price.
* **sl_short**: Stop Loss for a short position at 1 ATR above the entry price.
* **st_short**: Soft Target for a short position at 3 ATR below the entry price.

The results are displayed in a tabular format, showing the calculated values for the given ticker.


## **Important Note**

This tool is meant for informational and educational purposes only and should not be considered as financial advice. 
Always conduct thorough research and consider your risk tolerance before making any trading decisions. Use this script responsibly and at your own risk. Happy trading!
