# 300k take home interview question

In crypto currency market, there are many tokens and many trading pairs.

The goal is to compare price information of any two trading pairs.

Step 1.
Write api connection to fetch data from binance API https://binance-docs.github.io/apidocs/spot/en/#old-trade-lookup
You can find the api to get historical trades information.
The raw data should looks like this. we only care about time and price, the pair name we need to fetch are BTCUSDT and LINKUSDT
```
price: "38910.15", time: 1499865549590, ...
...
```

Write code to fetch from binance api and save them into any format for later use. you can save to csv, or insert into database, up to you to choose.
You should fetch at least one day's data (24 hours). No need to exceed 3 days data.


Step 2.
Once we have the raw trades data, we need to sample them to convert to one price data point every 10 seconds.
Let's look at the expected results after sampling

```
                         BTC/USDT                LINK/USDT              BTC/LINK (result)
2020-12-01 00:00:00       38910.15                 16.763                2321.19
2020-12-01 00:00:10       38925.1                  16.542                2353.11
2020-12-01 00:00:20       38966.00                 16.652                2340.02
...

```

To calculate BTC/LINK price for the above table, we need to sample the BTC/USDT, and LINK/USDT price every 10 seconds.

Meaning every 10 seconds, you take the last trade price as the market price, insert into the table,

Then you can compare BTC/LINK price once you have both pricing data at same timestamp.
Once you have the data above, write them into a CSV file and upload to github.

Step 3.
Optional, you can draw a chart of BTC/LINK price using any tool you like, and attach the chart with your results.

Final result:
Please upload you code，csv result file, chart (if available) to github, and share the github link via email.
