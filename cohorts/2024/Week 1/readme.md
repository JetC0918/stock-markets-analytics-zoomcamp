## Module 1: Introduction and Data Sources

Week 1 explore the way to get data from sources.

#### For Macro, we can get from FRED
To read data from FRED, we can use pandas datareader

```
import pandas_datareader as pdr
pdr.DataReader("GDPC1", "fred", start=start)
```


#### For Index, we can get from Yahoo Finances
In yfinance, we use ticker to represent the index
For example, for S&P 500

```
import yfinance as yf
snp500 = yf.download(tickers = "^GSPC",
                     period = "max",
                     interval = "1d")
```

The data obtained might be missing date column, we need to reset the index and get the "Date" column

```
snp500.reset_index(inplace=True)
```
 
#### Explanation of Terms Used

- **Adj Close**: Adjusted closing price of a stock or financial asset. The adjusted closing price is the price of the stock after adjustments have been made for dividends, stock splits, and other corporate actions that may affect the stock price.

- **Inverted Yield Curve**: Happens when the yields on short-term bonds are higher than long-term bonds. Normally seen as a warning sign of an economic downturn.

- **CAGR**: Compound Annual Growth Rate. It is a measure used to describe the mean annual growth rate of an investment over a specified period of time longer than one year. It can be calculated using the following formula: `CAGR = ((Final Value / Initial Value) ^ (1 / Number of Years)) - 1`.

- **52-Week Range Ratio**: Provides insights into the volatility and price variation of each stock relative to its maximum value. Calculated by using the formula `(Maximum Adj Close - Minimum Adj Close) / Maximum Adj Close`. Normally, the higher the ratio, the more volatile the stock.

- **Dividend Yield**: Financial ratio that indicates the percentage of a company's stock price that is paid out annually in dividends. Calculated using the formula `Total dividend in a year / Adj close in the last trading day`.

