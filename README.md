# Pine Strategy Indicators v1

## Overview

A collection of fundamental technical analysis indicators implemented in Pine Script v5 for TradingView. These indicators provide clean, customizable implementations of commonly used trading tools including moving averages, oscillators, and volume analysis.

## Included Indicators

### Trading Volume

**Purpose:** Displays relative volume compared to its moving average to identify abnormal trading activity.

**Core Logic:** Calculates volume relative to its 20-period SMA and plots as a histogram. Bars are highlighted in green when volume exceeds the moving average (relative volume > 1).

**Key Parameters:**
- SMA Period: 20 (hardcoded, not user-configurable)

![Trading Volume](images/volume_chart.png)

**Typical Use Case:** Confirm breakouts or trend strength by identifying periods of above-average trading activity. High relative volume during price movements suggests conviction.

---

### Simple Moving Average (SMA)

**Purpose:** Smooths price data to identify trend direction and potential support/resistance levels.

**Core Logic:** Calculates the arithmetic mean of the selected price source over a configurable period. Uses TradingView's built-in `ta.sma()` function.

**Key Parameters:**
- Length: Period for averaging (default: 14)
- Source: Price input (default: close)

![SMA](images/sma_chart.png)

**Typical Use Case:** Identify trend direction via price-to-SMA relationship. Crossovers between price and SMA, or between multiple SMAs, generate potential entry/exit signals.

---

### Exponential Moving Average (EMA)

**Purpose:** Provides a trend indicator that responds more quickly to recent price changes than SMA.

**Core Logic:** Applies exponential weighting to the selected price source, giving greater emphasis to recent data. Calculated using TradingView's `ta.ema()` function.

**Key Parameters:**
- Length: Period for EMA calculation (default: 14)
- Source: Price input (default: close)

![EMA](images/ema_chart.png)

**Typical Use Case:** Suitable for fast-moving markets or shorter timeframes where responsiveness to recent price action is prioritized over smoothness.

---

### Relative Strength Index (RSI)

**Purpose:** Measures momentum by comparing the magnitude of recent gains to recent losses.

**Core Logic:** Calculates RSI using TradingView's `ta.rsi()` function over a configurable period. Horizontal lines mark overbought and oversold thresholds.

**Key Parameters:**
- Length: Period for RSI calculation (default: 14)
- Overbought Level: Upper threshold (default: 70)
- Oversold Level: Lower threshold (default: 30)
- Source: Price input (default: close)

![RSI](images/rsi_chart.png)

**Typical Use Case:** Identify potential reversal zones when RSI enters overbought or oversold territory. Divergences between price and RSI can signal trend weakness.

---

### Stochastic Oscillator

**Purpose:** Compares the current closing price to its price range over a specified period to identify overbought/oversold conditions.

**Core Logic:** Calculates %K by determining where the close sits relative to the high-low range over a lookback period. %K is smoothed with an SMA, and %D is an SMA of smoothed %K. Overbought and oversold levels are marked at 80 and 20.

**Key Parameters:**
- Stoch Length: Lookback period (default: 14)
- %K Smoothing: SMA smoothing for %K (default: 3)
- %D Smoothing: SMA smoothing for %D (default: 3)
- High Source: Price input for high (default: high)
- Low Source: Price input for low (default: low)
- Close Source: Price input for close (default: close)

![Stochastic Oscillator](images/stochastic_chart.png)

**Typical Use Case:** Identify potential reversal points when %K and %D are in extreme zones (>80 or <20). Crossovers between %K and %D lines generate buy/sell signals.

---

## How to Use

1. Open the TradingView platform and access the Pine Editor
2. Copy the desired indicator code from the `/indicators` folder
3. Paste into the Pine Editor and save
4. Click "Add to Chart" to apply the indicator
5. Adjust parameters via the indicator's settings panel as needed

## Disclaimer

These indicators are provided for educational purposes only. They are not financial advice and should not be used as the sole basis for trading decisions. Always perform your own analysis and risk management.
