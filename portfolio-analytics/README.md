## Project Overview
This project builds a multi-asset portfolio analytics and optimization framework using over eight years of historical market data across equities, fixed income, real assets, and commodities. The analysis compares three portfolio construction approaches—equal-weight, mean–variance optimization, and risk-parity—evaluating their performance through risk-adjusted returns, volatility, drawdowns, and behavior across market regimes.
Beyond static performance metrics, the project incorporates rolling volatility and Sharpe ratio analysis to capture time-varying risk, as well as regime analysis distinguishing calm and crisis periods using drawdown-based thresholds. All strategies are benchmarked against a traditional 60/40 equity–bond portfolio to assess real-world relevance. The results highlight trade-offs between upside capture, risk concentration, and downside protection, with risk parity emerging as the most robust strategy in terms of risk-adjusted performance and drawdown control.

## Methods & Data
### Data
The analysis uses daily historical price data spanning over eight years (from 2016 onward) for a diversified set of exchange-traded funds (ETFs) representing major asset classes: U.S. equities, international equities, U.S. bonds, real estate, commodities, and gold. Price data were sourced from Yahoo Finance and downloaded using the yfinance Python library. Auto-adjusted prices were used to account for dividends and corporate actions, ensuring that return calculations reflect true investor performance. Daily returns were computed from adjusted prices and validated to contain no missing observations across assets.
### Portfolio Construction
Three portfolio construction methodologies were implemented and compared:
Equal-Weight Portfolio: Capital is allocated evenly across all asset classes, serving as a transparent baseline that does not adjust for differences in risk or correlation.
Mean–Variance Portfolio: A long-only, fully invested minimum-variance portfolio is constructed using historical return and covariance estimates. Portfolio weights are chosen to minimize total portfolio volatility subject to realistic investment constraints.
Risk-Parity Portfolio: Portfolio weights are determined such that each asset contributes equally to total portfolio risk, using the covariance matrix to balance risk contributions rather than capital allocations.
All portfolios are evaluated using annualized return, annualized volatility, Sharpe ratio (assuming a zero risk-free rate), and maximum drawdown.
### Benchmarking and Regime Analysis
Portfolio performance is benchmarked against a traditional 60/40 equity–bond portfolio to provide real-world context. To assess robustness across market environments, a regime analysis is conducted by separating calm and crisis periods using a drawdown-based threshold on U.S. equities. Rolling 12-month volatility and Sharpe ratios are also computed to capture time-varying risk and performance dynamics.
