# svd-cross-sectional-alpha

**Project Zero.** Rebuilding, from a blank file, the cross-sectional factor pipeline
I worked on during my summer 2026 internships (Sunlux and SRM faculty). The goal is
not a better result; it is to be able to explain and defend every line.

## The question

Can singular value decomposition (SVD) applied to a panel of stock characteristics
extract a signal that predicts next-month returns across stocks?

## Data

- About 475 US stocks, 2017–2024, downloaded with `yfinance` (daily prices,
  monthly rebalancing).
- Nine characteristics per stock per month, including 12-month momentum,
  1-month reversal, 60-day volatility, and size/turnover. 

## Pipeline (one stage per week, in order)

1. `data.py` – download and cache prices
2. `features.py` – compute the nine characteristics
3. `portfolios.py` – rank-standardise, build one managed portfolio per characteristic
4. `svd.py` – centre the panel, decompose, form weights
5. `deciles.py` – sort stocks into ten groups by predicted return
6. `walkforward.py` – rolling out-of-sample loop
7. `stats.py` – Newey–West t-statistics and figures

Stages completed so far: none (repository created 27 Sep 2026; target 24 Dec 2026).

## How to run

```bash
pip install -r requirements.txt
python run.py
```

One command reproduces every figure. Not yet implemented.

## Results

Pending the rebuild. Numbers will be added only once they are reproduced here.


## Limitations I already know about

- Survivorship bias: the universe is today's list, not the list as it was each month.
- No transaction costs, taxes or borrowing costs.
- Small sample: seven years, one market.

## Author

Sai Nithin Garuda · B.Tech Mathematics & Computing, SRMIST · 
[LinkedIn](https://www.linkedin.com/in/nithin-garuda-a4b30a287/)
