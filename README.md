import yfinance as yf
import numpy as np
import pandas as pd
import datetime
from statsmodels.tsa.stattools import adfuller
from statsmodels.tsa.seasonal import seasonal_decompose
import matplotlib.pyplot as plt

ticker = '^GSPC'
start = datetime.datetime(2015,1,1)
end = datetime.datetime(2021, 1 , 1)

SP500 = yf.download(ticker,start=start,end=end,interval='1mo')

seasonal_decompose(SP500['Close'], period=12).plot()
plt.show()
