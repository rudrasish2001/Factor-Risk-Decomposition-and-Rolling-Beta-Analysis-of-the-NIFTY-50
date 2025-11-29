Factor Risk Decomposition and Rolling Beta Analysis of the NIFTY 50:

INTRODUCTION:
The goal of this project is to build a full multi-factor and time-series forecasting framework for the NIFTY 50. It brings together Fama–French factors, key macro indicators, and machine-learning models to understand what drives the index and how it might move ahead. The work looks at how NIFTY returns have behaved over time, how factor sensitivities shift across market cycles, and how much each factor actually explains when tested through rolling regressions. It then builds forward-looking forecasts using ARIMA and LSTM models to compare accuracy and stability. In short, the project aims to show how global conditions, domestic trends, and style-based factors shape Indian equities, and which forecasting methods capture that behaviour most reliably.

<img width="1189" height="390" alt="image" src="https://github.com/user-attachments/assets/13fcede1-1925-4cb6-9cad-673354c1bd1a" />


SUMMARY:
This project builds a full asset-pricing and forecasting framework for the NIFTY 50. It brings together market data, Fama–French factors, macro-yield variables, and a mix of time-series models to understand what drives the index and how it might behave ahead.

Five years of NIFTY data were merged with daily factor datasets, including market excess return (Rm−Rf), SMB, HML, RMW, CMA, momentum, and the U.S. 10-year Treasury yield (DGS10). After cleaning and aligning the dates, daily NIFTY returns were converted into excess returns using the risk-free rate.

The multi-factor OLS results show one thing clearly: the market factor is still the main force behind NIFTY excess returns. SMB and HML add useful but shifting insight depending on the period. The strong negative correlation with the U.S. 10-year yield (about −0.67) confirms how sensitive Indian equities are to global rate cycles. High overlap between HML and CMA also shows how value and investment styles often move together.

Rolling 252-day regressions reveal how these relationships change through time. Market beta climbs in expansionary periods like 2021 and 2024, then cools off when monetary policy tightens, as in 2022–23. SMB turns positive in late 2024–25, which lines up with the surge in mid and small caps. HML drifts between positive and neutral, showing steady but moderate preference for value.

Rolling R² drops hard during macro volatility, which means the factor model explains less when local shocks or idiosyncratic behaviour take over. Residual volatility spikes during 2022–23, then settles again once conditions improve in 2024.

Cumulative factor-contribution charts show that market movement accounts for most of the excess performance. SMB and HML add smaller but meaningful layers, while yield variables bring in independent information that helps explain cross-border rate sensitivity.

For forecasting, the project tested ARIMA, SARIMAX, and LSTM models. The LSTM produced smoother and more flexible projections. ARIMA and SARIMAX stayed closer to flat paths, which matches the reality of near-zero average daily returns. A combined six-month forecast plot blends these outputs with the final months of actual data for a practical view of what may lie ahead.

Altogether, the work shows that NIFTY’s risk profile shifts with both global shocks and domestic sector rotations. Using multi-factor modeling, rolling analytics, and machine-learning forecasts gives a more solid picture of how the market behaves and what future trends might look like.


1. Cumulative Factor Contributions

This chart tracks how each factor—Market Excess Return (Rm−Rf), SMB, and HML—contributes cumulatively to NIFTY’s excess returns over time.

Interpretation:

1. The market factor dominates long-term contribution, indicating NIFTY’s performance is primarily driven by broad market risk.
2. HML (Value) remains consistently positive, showing value-oriented stocks contributed steadily.
3. SMB (Size) stays slightly negative or flat, meaning small-cap exposure added little to performance.
4. Market downturns show sharp drops in the market factor contribution, confirming high sensitivity to macro shocks.

<img width="1588" height="690" alt="image" src="https://github.com/user-attachments/assets/7daeb3f1-b464-456e-9521-c3ed34f186a1" />


2. Rolling Residual Volatility:

Rolling standard deviation of regression residuals—how much NIFTY returns are left unexplained by the factor model.

Interpretation:

1. Residual volatility spiked in 2022–23, indicating several risk events (global tightening, inflation, foreign outflows).
2. Volatility falls in 2024, showing markets stabilized and factors explained returns better.
3. A small rise in 2025 reflects renewed domestic volatility in small/mid-caps.

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/67672dc8-94d0-4107-92f4-7085c60e9155" />


3. Rolling R²:

This measures how much of NIFTY’s excess return is explained by the factors over time.

Interpretation:

1. High R² in 2021–22, meaning factors explained NIFTY well during stable growth phases.
2. Sharp drop in 2022–23, showing factor models struggled during monetary tightening and global turmoil.
3. R² improves again in 2024 but not consistently—meaning structural changes in the Indian market reduced factor predictability.

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/ae9dfcd9-0876-4e69-a902-998add7fff49" />


4. Rolling Factor Betas (252 trading days)

This plots the time-varying sensitivity of NIFTY to Market (Rm−Rf), Size (SMB), and Value (HML) factors.

Interpretation:

1. Market Beta is procyclical: high in 2021, low in 2022–23, rising again in 2024.
2. SMB Beta turns positive in 2024-25, aligning with India’s mid/small-cap rally.
3. HML Beta remains moderately positive, reflecting value-sector contribution in banks, metals, PSU stocks.

<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/74d097f4-e496-43ef-b677-9be4ae1d7e35" />


5. Correlation Heatmap

Correlation between NIFTY excess returns and all risk factors.

Interpretation:

1. Strong negative correlation with DGS10 (−0.67) → Rising U.S. yields hurt Indian markets.
2. Low correlation with SMB/HML → NIFTY is not strongly style-tilted on average.
3. HML and CMA highly correlated → Value and conservative-investment strategies overlap.
4. Market factor has only mild correlation, due to differences between the US and Indian market structures.

<img width="799" height="686" alt="image" src="https://github.com/user-attachments/assets/2ea10de5-d437-41d1-83c4-c7d72a75d70e" />


6. Actual vs ARIMA vs LSTM – 6-Month Forecast

A combined plot comparing actual NIFTY prices with 6-month forecasts from ARIMA and LSTM.

Interpretation:

1. ARIMA prediction is flat, reflecting nearly zero long-term drift in daily returns.
2. LSTM shows a smooth declining trend, capturing structural slowing in momentum.
3. Actual prices show higher volatility than model predictions, consistent with machine learning smoothing.

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/19ac6f83-6c54-498e-ba01-20230d5420fb" />


7. Previous-3-Month Predictions vs Next-3-Month Forecasts

A split visualization showing how well ARIMA and LSTM predicted the last 3 months, and their forecasts for the next 3 months.

Interpretation:

1. LSTM matches previous trend more closely than ARIMA.
2. ARIMA underreacts, producing flat values both historically and forward.
3. Future LSTM predictions show a mild downward slope, consistent with observed weakening momentum.

<img width="1188" height="490" alt="image" src="https://github.com/user-attachments/assets/8d790ab9-57c6-4dc7-908d-e22676060d73" />
