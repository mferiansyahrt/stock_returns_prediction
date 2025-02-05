# stock_returns_prediction

The dataset used comes from [starbuck_stocks]('https://raw.githubusercontent.com/lazyprogrammer/machine_learning_examples/master/tf2.0/sbux.csv')

<div align="center">
    <a href="./">
        <img src="./figure/dataset_preview.png" width="60%"/>
    </a>
</div>

"Open" is the first stock price of a particular day, while "close" is the last stock price of that day. "High" refers to the highest stock price on a specific day, and "low" refers to the lowest stock price on that day. "Volume" represents the number of shares traded on that day. Notes: Stock prices are timestamped, meaning we can observe the price of a stock at any given second on a specific day. The most important aspect of the data is whether all features fall within the same range. In this dataset, stock prices range in the tens, while the volume ranges in the millions.

## Results on stock prediction

The model used on stock prediction is LSTM with 5 hidden units, but it does not predict the subsequent values effectively using the existing training data. This is because the time series data in this case is highly correlated, meaning previous data is closely related to the following data. The analogy is similar to image pixels, where if one pixel is red, the adjacent pixel is likely to be red as well. Therefore, the time series prediction below results in the model merely copying the previous value (on multistep).

One-step prediction predicts a single future value, while multi-step prediction generates a sequence of future values, often requiring the model to handle more complex dependencies between data points.

<div align="center">
    <a href="./">
        <img src="./figure/onestep_1.png" width="60%"/>
    </a>
</div>

<div align="center">
    <a href="./">
        <img src="./figure/multistep_1.png" width="60%"/>
    </a>
</div>
     
