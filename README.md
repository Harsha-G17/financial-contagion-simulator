# financial-contagion-simulator

# Financial Contagion and Liquidity Crisis Simulator
## Version 1: Fund fire-sale contagion

### Objective
Explore how investor withdrawals cause forced bond sales,
price declines and additional losses across funds.

### Data
Bank of England nominal spot curves, 2016–2024.
Simulation maturities: 2, 5, 10, 20 and 30 years.
Historical yield changes are applied as instantaneous shocks.

### Model
Five synthetic funds hold zero-coupon bond portfolios and cash.
Withdrawals depend on a base rate and investment losses.
Funds use cash first, then sell bonds proportionally.
Combined sales cause a common price decline.
Additional losses can trigger further withdrawal rounds.

### Validation
- Fund accounting balances.
- Zero price impact produces zero contagion losses.
- Sufficient cash prevents forced selling.
- Exhausted holdings leave unpaid withdrawals.
- Notebook runs from a restarted session.

### Findings
All 2,272 tested historical intervals settled under the
tested two-fund assumptions.
Increasing price impact increased losses and selling rounds.
Funds could suffer contagion losses without selling themselves.

### Limitations
Fund holdings, cash, withdrawal behaviour and market depth
are synthetic assumptions, not calibrated estimates.
Price impact is shared across maturities.
Tests are independent scenarios, not a continuous backtest.
Banks, leverage, margin calls and funding networks are excluded.
Results are simulated outcomes, not observed fund losses.
