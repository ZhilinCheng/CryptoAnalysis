Introduction to Project Design

1. Structure Design:
The structure design is the most critical aspect of programming. However, I must admit that the structure for this project could have been better. My approach was to create an abstract base class, override it in derived classes, and then use a main class to select the data range and run the analysis. The intended workflow was:

Fetch Data → Analyze Data → Main Class (Change symbols for different asset analysis).
This modular approach would ideally allow for easy maintenance—new features could simply be added to derived classes. However, due to time constraints, the structure lacks polish and could be optimized further.

2. Fetching Data:
Data fetching was implemented using Binance’s API (fetch_data_from_binance) to retrieve cryptocurrency data. This was followed by GARCH analysis, although the process is not entirely rigorous. For proper GARCH testing, an ADF test should first be conducted to check for stationarity. This step was not fully incorporated.

3. Regression Analysis:
A regression model was used to analyze the impact of risk factors on asset returns. The results indicate very low R-squared values, suggesting that other factors play a more significant role in explaining returns. I recommend reading this report by Two Sigma for additional insights into this topic.

4. Stress Testing:
Stress tests assessed the impact of a 50% drop in liquidity on asset returns. The results suggest that liquidity stress had minimal impact across all tested assets. This indicates that other risk factors, such as macroeconomic events or market sentiment, may be more critical.

5. Correlation Analysis:
The heatmap revealed that Bitcoin (BTC) and Ethereum (ETH) exhibit the highest correlation, indicating strong co-movement. In contrast, Chainlink (LINK) and Solana (SOL) show weaker correlations with BTC and ETH, suggesting more independent price behaviors. These findings highlight the varying degrees of interdependence within the crypto market.

6. Macro Analysis:
Initially, I planned to create two separate classes for fetching data: one for cryptocurrencies and another for S&P 500 data (I considered using treasury rates but ultimately opted for equity factors). However, due to challenges with data formatting and time constraints, I ended up creating one independent class for macro analysis. This approach is not ideal for structure design but was necessary given the circumstances.

From the macro analysis, it is clear that the cryptocurrency market has significantly higher volatility compared to the equity market. This may explain why certain volatility models, such as Heston, do not perform well in the crypto market. For further research, building a correlation model to analyze the relationship between equity factors and crypto assets could be valuable.

7. Trading Signal Generation:
A simple version of trading signal generation was implemented. It uses the z-score as a factor and plots the signals on a graph. While functional, this component could be expanded with more sophisticated algorithms in future iterations.

