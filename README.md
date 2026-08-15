# 📊 Portfolio Performance and Risk Analysis

A Python-based analysis of an individual stock and a weighted equity portfolio, comparing historical performance and risk against the S&P 500.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Finance](https://img.shields.io/badge/Focus-Portfolio%20Analytics-green)
![Status](https://img.shields.io/badge/Status-Learning%20Project-yellow)

---

## 📌 Project Overview

This project uses historical financial data to investigate two main questions:

1. How has Goldman Sachs (`GS`) performed relative to the wider US stock market?
2. How would a portfolio containing NVIDIA (`NVDA`), Goldman Sachs (`GS`) and Microsoft (`MSFT`) have performed relative to the S&P 500?

The project uses Python to:

- Download historical market data
- Calculate daily stock and portfolio returns
- Construct a weighted portfolio
- Compare performance against SPY
- Generate performance and risk statistics
- Analyse drawdowns and risk-adjusted returns
- Interpret the results from an investment-risk perspective

> **Important:** This is an educational project, not financial advice or a recommendation to invest in these companies.

---

## 🎯 Why I Built This Project

I built this project to develop a practical understanding of how Python is used in portfolio analysis and quantitative finance.

Before completing this project, I had encountered concepts such as volatility, alpha, beta, drawdown and the Sharpe ratio in theory. However, I wanted to understand how these measures are calculated using real market data and, more importantly, how they should be interpreted.

I initially followed a portfolio-analysis tutorial created by **NeuralNine**, alongside finance books and official library documentation. The tutorial gave me a practical foundation for retrieving market data and generating PyFolio tear sheets.

I then developed my understanding by:

- Selecting my own companies and portfolio weights
- Comparing the portfolio against a market benchmark
- Examining the meaning of each performance measure
- Interpreting the portfolio’s returns and risks
- Identifying weaknesses in the backtest
- Considering how the analysis could be improved

This project forms part of my wider effort to strengthen my skills in Python, data analysis and quantitative finance.

---

## 🧺 Portfolio Composition

The portfolio uses the following allocation:

| Company | Ticker | Weight |
|---|---:|---:|
| NVIDIA | `NVDA` | 40% |
| Goldman Sachs | `GS` | 40% |
| Microsoft | `MSFT` | 20% |
| **Total** |  | **100%** |

The daily portfolio return is calculated as:

```text
Portfolio Return = (NVDA Return × 40%)
                 + (GS Return × 40%)
                 + (MSFT Return × 20%)
```

The portfolio is compared against `SPY`, an exchange-traded fund designed to track the S&P 500.

---

## 🔍 Analysis Performed

### 1. Goldman Sachs Analysis

The first part of the notebook:

- Downloads the complete available price history for Goldman Sachs
- Calculates daily percentage returns
- Downloads SPY benchmark data
- Aligns GS and SPY returns by trading date
- Generates a PyFolio returns tear sheet
- Evaluates performance, volatility and market sensitivity

### 2. Weighted Portfolio Analysis

The second part:

- Downloads historical prices for NVDA, GS and MSFT
- Combines the price series using their common trading dates
- Calculates daily returns for each asset
- Applies the selected portfolio weights
- Creates a combined portfolio-return series
- Compares the portfolio against SPY
- Produces a second PyFolio tear sheet

---

## 📈 Key Findings

The saved notebook results cover the period from **5 May 1999 to 28 July 2026** for the three-stock portfolio.

| Metric | Goldman Sachs | Three-Stock Portfolio |
|---|---:|---:|
| Annualised return | 11.96% | **26.43%** |
| Annualised volatility | 36.05% | **35.74%** |
| Sharpe ratio | 0.49 | **0.83** |
| Sortino ratio | 0.74 | **1.26** |
| Maximum drawdown | -78.84% | **-75.04%** |
| Calmar ratio | 0.15 | **0.35** |
| Alpha against SPY | 0.05 | **0.17** |
| Beta against SPY | 1.33 | **1.41** |
| Daily value at risk | -4.47% | **-4.38%** |

The period beginning in 2023 was particularly strong:

| Metric | Goldman Sachs | Three-Stock Portfolio |
|---|---:|---:|
| Annualised return | 40.04% | **62.59%** |
| Annualised volatility | 28.65% | **28.56%** |
| Sharpe ratio | 1.32 | **1.85** |

These are historical results and should not be interpreted as expected or sustainable future returns.

---

## 💡 My Interpretation

### Return and volatility

The three-stock portfolio generated a substantially higher annualised historical return than Goldman Sachs alone.

Interestingly, its annualised volatility was slightly lower than that of GS. This suggests that, during the period studied, combining the three assets improved the relationship between return and total volatility.

However, this does not mean the portfolio was low risk.

### Sharpe ratio

The portfolio produced a Sharpe ratio of `0.83`, compared with `0.49` for GS.

The Sharpe ratio measures return relative to total volatility. Therefore, the higher value indicates that the portfolio generated more return for each unit of total risk during the historical period.

### Sortino ratio

The portfolio’s Sortino ratio was `1.26`, compared with `0.74` for GS.

Unlike the Sharpe ratio, the Sortino ratio focuses specifically on harmful downside volatility. The higher portfolio value suggests that it produced a better return relative to its negative price movements.

### Maximum drawdown

Despite its strong returns, the portfolio experienced a maximum drawdown of approximately `75%`.

This means that, at its worst point, its value fell by around three-quarters from a previous peak. The worst drawdown:

- Began in October 2007
- Reached its lowest point in November 2008
- Did not fully recover until August 2014

This demonstrates that strong long-term returns do not prevent investors from experiencing extremely large temporary losses.

### Alpha

The portfolio produced an estimated alpha of `0.17`, compared with `0.05` for GS.

This suggests that the portfolio achieved stronger returns than would be expected solely from its historical exposure to SPY under the model used.

However, alpha is a historical, model-dependent estimate. It does not prove that investment skill caused the additional return.

### Beta

The portfolio had a beta of `1.41`.

A beta above `1` means that the portfolio historically tended to move more strongly than the market. For example, a 1% movement in SPY could be associated with an approximately 1.41% movement in the portfolio on average, although the relationship is not exact.

This increased market sensitivity contributed to both stronger gains and potentially larger losses.

### Skewness and kurtosis

The portfolio displayed positive skewness, suggesting that unusually large positive daily returns occurred more frequently than similarly large negative returns.

Its kurtosis of `7.55` indicates fat-tailed returns. In simple terms, extreme daily movements occurred more frequently than would be expected under a normal distribution.

This shows why volatility alone cannot provide a complete picture of portfolio risk.

---

## ⚖️ Overall Conclusion

The portfolio historically delivered:

- Higher annualised returns
- Better Sharpe and Sortino ratios
- Higher estimated alpha
- Similar overall volatility to GS

However, it also had:

- Greater sensitivity to market movements
- A maximum drawdown of approximately 75%
- Significant concentration risk
- Heavy exposure to large US technology companies
- Strong dependence on historically successful stocks

My main conclusion is:

> **A portfolio can produce strong returns and attractive risk-adjusted ratios while still exposing an investor to severe losses.**

The portfolio’s results were heavily influenced by its 60% combined allocation to NVIDIA and Microsoft. Therefore, its performance should not be interpreted as evidence of broad diversification.

---

## 🧠 What I Learned

### Python and data analysis

Through this project, I learned how to:

- Retrieve historical financial data using `yfinance`
- Work with pandas Series and DataFrames
- Clean and align time-series datasets
- Calculate daily percentage returns
- Construct a weighted portfolio-return series
- Handle assets with different available date ranges
- Use PyFolio to generate financial tear sheets
- Build a repeatable analysis instead of calculating results manually

### Financial concepts

I developed a better understanding of:

- Annualised return
- Annualised volatility
- Cumulative return
- Sharpe ratio
- Sortino ratio
- Calmar ratio
- Maximum drawdown
- Alpha and beta
- Value at Risk
- Skewness and kurtosis
- Benchmark comparison
- Risk-adjusted performance

Most importantly, I learned that generating a financial ratio is only the beginning of the analysis. A meaningful conclusion must explain:

- What the result means
- Which assumptions produced it
- What risks it captures
- What risks it may overlook
- Whether the result is likely to be repeatable

---

## 🌍 Project Impact

This project converts raw historical market prices into a structured and repeatable portfolio-analysis workflow.

It provides a foundation for building more advanced tools that could:

- Compare alternative investment allocations
- Evaluate portfolio risk
- Test different rebalancing strategies
- Examine performance under different market conditions
- Communicate financial results to non-technical users
- Support more informed, data-driven portfolio discussions

For my personal development, this project connects three areas that I want to continue strengthening:

- **Programming:** creating reproducible Python workflows
- **Data analysis:** cleaning and transforming financial time-series data
- **Financial reasoning:** evaluating returns in relation to risk and a benchmark

---

## 🛠️ Technologies Used

- Python
- Jupyter Notebook
- pandas
- yfinance
- pyfolio-reloaded
- Matplotlib

> The package is installed as `pyfolio-reloaded`, but imported in Python using `import pyfolio as pf`.

---

## 📁 Repository Structure

```text
portfolio-performance-analysis/
├── portfolio_analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/freyabytes/portfolio-performance-analysis.git
cd portfolio-performance-analysis
```

### 2. Create a virtual environment

#### Windows PowerShell

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

#### macOS or Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install the required libraries

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open `portfolio_analysis.ipynb`, select the virtual-environment kernel and run all cells from top to bottom.

Internet access is required because `yfinance` downloads current market data when the notebook runs.

---

## ⚠️ Assumptions and Limitations

This analysis has several important limitations:

- Historical performance does not predict future performance.
- Transaction costs, taxes, slippage and bid-ask spreads are excluded.
- The portfolio contains only three US-listed companies.
- The asset selection benefits from hindsight.
- NVIDIA and Microsoft were already known as historically successful companies.
- Results may change when Yahoo Finance updates its data.
- The analysis does not clearly implement a realistic rebalancing schedule.
- Applying the original weights to every day’s returns effectively assumes frequent rebalancing.
- SPY may not be the most appropriate benchmark for every investment objective.
- The post-2023 period is not a formal out-of-sample test.
- Alpha and beta depend on the selected model and historical period.
- Value at Risk does not represent the maximum possible daily loss.
- Dividends and corporate actions depend on the data adjustments made by the source.

Because the stocks and weights were selected with knowledge of their historical performance, the results contain both **selection bias** and **hindsight bias**.

---

## 🔮 Future Improvements

Future versions of the project could:

- Compare the portfolio with an equal-weighted allocation
- Test buy-and-hold, monthly and quarterly rebalancing
- Include transaction costs and slippage
- Include an explicit risk-free rate
- Add rolling asset correlations
- Create a correlation heatmap
- Calculate each stock’s contribution to portfolio risk
- Explore portfolio optimisation and the efficient frontier
- Use formally separated in-sample and out-of-sample periods
- Test the portfolio under different market conditions
- Compare results across multiple benchmarks
- Build an interactive dashboard
- Allow users to change tickers, weights and dates

---

## 🙏 Acknowledgements

The idea for this project was inspired by a NeuralNine portfolio-analysis tutorial. I independently built and extended the analysis, using finance books and the official pandas, yfinance and PyFolio documentation to understand and validate the calculations.

The portfolio construction, written explanations, findings, risk interpretations, limitations and proposed improvements are based on my own implementation and analysis.

---

## 📄 Disclaimer

This project was created solely for educational and personal-development purposes.

It does not constitute financial advice, investment research or a recommendation to buy or sell any security. The selected companies and portfolio weights are examples used to practise portfolio analysis.
