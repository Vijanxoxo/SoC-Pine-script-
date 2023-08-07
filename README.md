# SoC-Pine-script-


Building trading strategy with pine script
-

Aim: The project aimed to provide hands-on experience in developing custom trading strategies using Pine Script language on TradingView. Pine Script is a programming language that allows traders to create custom indicators and strategies on the TradingView platform. 

Motivation: The project entailed getting an understanding of how the trading view platform works, how to read charts, using indicators, available functionalities and the final boss i.e.learning pine script to develop a comprehensive trading strategy and backtest it to see how it performs. My motivation for the project was to study if the indicators work the way we intend them to, add a little bit of coding to my arsenal and have a productive summers.

Description: I started with exploring the platform and pine script, read a bunch of articles, got my hands on some frisky shortcuts, some websites that i referred to can be found here: 
// [Quantifiedstrategies](https://www.quantifiedstrategies.com/trading-strategies/)
// [Algotrading101](https://algotrading101.com/learn/pine-script-tradingview-guide/#:~:text=Pine%20script%20was%20designed%20to,up%20quickly%20and%20notice%20similarities.)
// [Tradingcode](https://www.tradingcode.net/tradingview-pine-script-course/)
// And a bunch of youtube tutorials are also helpful 

Also fun fact, you can use indicators on other indicators to produce results in trading view
Then I read about a bunch of indicators, it was a smooth ride as i had already done a little paper trading and portfolio building before. 
And explored strategies that supposedly produced good profit ex 50 day SMA, donchian channel breakouts etc links to which i have attached below:
// [investopedia](https://www.investopedia.com/top-7-technical-analysis-tools-4773275)
// [cointelgraph](https://cointelegraph.com/news/3-technical-analysis-strategies-that-help-confirm-winning-trades)
// Babypips

Finally read how to implement these strategies using pine script, backtest them to generate orders etc etc, links to those articles are also attached below 
// [tradingcode](https://www.tradingcode.net/tradingview/example-strategies/)
// trading view itself also has a good repository of pine scripts for indicators and strategies 

After a comprehensive study i build a VWAP and SWMA strategy, it was a trend confirming long term strategy; [vwap](https://navi.com/blog/volume-weighted-average-price/#:~:text=The%20VWAP%20indicator%20shows%20the,enter%20or%20exit%20the%20market.) stands for volume weighted average price, its a volume indicator whereas [swma](https://in.tradingview.com/scripts/swma/) is smooth weighted moving average, both are lagging indicators buy/sell signals are generated when price crosses swma and the order confirmation is generated when vwap also generates the same signal. You can refer to [vwap swma strategy](https://github.com/Vijanxoxo/SoC-Pine-script-/blob/main/vwap%20swma%20strategy) for the code and paste it in the editor to backtest and/or use it. 
Given the complications, this was still a very primitive strategy and doesnt explore pine script to its full potential, for all it was a very beginners way to a simple strategy creation.

A lot of factors come into play when we talk about making your own strategy and ofcourse no strategy is perfect, but luckily pine script accomodates for most of these and you can set variales such as slippage, stop losses, limits, visuals, plots, shapes etc



Breakout strategy
- 

To implement it i worked on another strategy which is conventionally common but a pretty useful one for breakout trading A breakout refers to when the price of an asset moves above a resistance area, or moves below a support area. Breakout traders commonly use bands and channels as limits and prices crossing those barriers generates trading signals. [Bollinger bands](https://www.babypips.com/learn/forex/bollinger-bands) is one of such bands which can tell us about the trend in the market and place orders. The same has been implemented my script [Bollinger Bands Breakout Strategy](bollinger_bands_breakout_strategy.txt). Some features i implemented in this strategy are: 
1)You can now give source(open/high/low/close) as an input. Default has been set to close 
2)You can also define sma deviation, deviation etc  
3)Script plots bands and adds color between the lines
4)signals are displayed on the graph 
5)incorporated pyramiding(placing more than one active trade)



Moving on, the final strategy was a build up on previous strategies and adding some additional nuances. 

Swing trading strategy using MACD, RSI, ADX, ATR, Parabolic SAR
-

It was a swing trend trading strategy which captured the market trends using a combination of momentum oscillator indicator - MACD(moving average convergence divergence), momentum indicator - RSI(relative strength index), directional trend strength indicator - ADX(Average Directional Index), trailing and stop indicator - parabolic SAR(stop and reversal). The choice of these indicators were based on the following factors:-
1)Used a combination of both lagging and leading indicators and smoothed them to remove any fakeouts (RSI is a leading indicator)
2)RSI doesnt work in choppy markets so we use parabolic SAR to confirm signals when trend is weak
3)Trend strength is confirmed by ADX, a value of ADX higher than 30 indicates a trending market
4)RSI and MACD are complimenting indicators 
5)We use smoothed RSI to avoid false unwanted signals

The code can be found here: [Swing trading strategy](initial_swing_trading_strategy.txt)

Strategy: Strength of trend is plotted in green and red using ADX. MACD line and signal line is plotted, crossover momentum is also plotted, rsi and parabolic sar are also plotted as line and dots respectively. Signal line crossing macd line produces a buy/sell signal, a confirmation is generated using rsi or sar values. RSI higher than 70 means overbought condition and generates a buy signal and vice versa for rsi less than 30. A flip and 3 continuous dots of parabolic sar indicates buy signal if the dots are below the prices and sell signal if they are above it. 

Stop loss is decided using atr(average true value) entire process is linked: https://www.investopedia.com/articles/trading/06/stopplacement.asp
Position size is also decided based on a certain fraction of total capital can be risked at a time. 
Take profits are decided based on a risk reward ratio which is given as an input since stop has already been calculated.
Slippage has been accounted for.

The problem that i came accross was lot of articles on internet uses pine script version 4 but the current one is version 5 so you might have to modify it at times


This concludes my project progress, in future i wish to incorporate the following in the project:
1)Risk Management: Integrate risk management techniques into your trading strategies to control and minimize potential losses.
2)Backtesting and Optimization: Backtest the strategy on major macroeconomic and microeconomic events ex CoViD and see how it performs 
3)Adding alerts and notifications
4)Risk-adjusted Performance Metrics: Include risk-adjusted metrics like Sharpe ratio, Sortino ratio, or Calmar ratio.
5)Incorporate Fundamental Data: Explore ways to incorporate fundamental data (e.g., earnings reports, economic indicators)


Thank you!

