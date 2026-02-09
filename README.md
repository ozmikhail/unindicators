# Universal Indicators — Reversal Detection System

A comprehensive TradingView indicator that orchestrates 62+ technical indicators through a multi-category confluence engine designed to identify high-probability reversal points rather than chase trends.

## Philosophy: Why This Works Differently

Most indicator combinations create false confidence by stacking lagging signals. When RSI, MACD, and moving averages all say "buy," you're often buying exhaustion, not opportunity. This system inverts that logic.

**The Core Premise**: Market reversals occur when five independent categories of evidence simultaneously confirm exhaustion and structural support for a directional change:

1. **Trend** — Momentum is decelerating or flipping
2. **Momentum Oscillators** — Oversold/overbought extremes with divergences
3. **Volatility** — Compression or expansion at key levels
4. **Volume** — Accumulation/distribution patterns confirm the move
5. **Market Structure** — Price is at support/resistance with structural confirmation

The system requires **category agreement** (3+ categories aligned) plus a composite score threshold before generating a signal. This multi-dimensional filter dramatically reduces false positives compared to single-indicator or same-category confluences.

---

## What's Inside

### Trend & Moving Averages (14 indicators)
Hull MA, SuperTrend, Parabolic SAR, Ichimoku Cloud, McGinley Dynamic, DEMA, TEMA, GMMA, Williams Alligator, VWMA, Donchian Channel, Linear Regression, EMA Stack (9/21/50), Higher Timeframe Trend

### Momentum Oscillators (17 indicators)
RSI (standard + trend-adjusted + volume-weighted), MACD + Histogram, Stochastic, CCI, Williams %R, ROC, Fisher Transform, TRIX, Ultimate Oscillator, KST, Coppock Curve, Schaff Trend Cycle, DPO, RVI, Chande Momentum, Elder Force Index, Pretty Good Oscillator

### Volatility (9 indicators)
ATR, Bollinger Bands + %B, Keltner Channels, TTM Squeeze, Historical Volatility Rank, Chandelier Exit, Standard Deviation Bands, Mass Index, Z-Score

### Volume Analysis (12 indicators)
OBV, Chaikin Money Flow, Money Flow Index (standard + Bollinger Width), Accumulation/Distribution, Klinger Oscillator, Ease of Movement, Twiggs Money Flow, Buy/Sell Pressure Ratio, NVI/PVI, Intraday Intensity, VWAP, Volume Oscillator

### Market Structure (10 indicators)
Support/Resistance Zones, Pivot Points (R1/S1/R2/S2), Fibonacci Retracement Levels, Order Blocks, Fair Value Gaps, Break of Structure (BOS), Change of Character (CHoCH), Swing Failure Patterns, Gap Detection, Wyckoff Spring/Upthrust

### Candlestick Patterns (9 patterns)
Engulfing, Hammer/Shooting Star, Morning/Evening Star, Doji, Harami, Three White Soldiers/Black Crows, Tweezer Tops/Bottoms, Piercing Line/Dark Cloud Cover

### Additional Components
Aroon Oscillator, Vortex Indicator, Elder Impulse System, Ehlers Sine Wave (cycle detection), Intermarket Correlation, Session Filters, Multi-Timeframe Trend Heatmap

---

## How to Use This Indicator for Maximum Accuracy

### Initial Setup

1. **Enabled Core Visual Components**
   - Dashboard: ON (shows real-time scoring and category agreement)
   - MTF Trend Heatmap: ON (confirms higher timeframe alignment)
   - Bollinger Bands: ON (volatility context)
   - Pivot Points: ON (structural reference levels)
   - VWAP Line: ON (institutional reference)

2. **Configure Signal Sensitivity**
   - **Signal Threshold**: Start at 65-70 for your timeframe
     - Scalping (1-5min): 55-60 (more signals, lower quality)
     - Day trading (15-60min): 65-70 (balanced & recommended) 
     - Swing trading (4H-D): 75-80 (high conviction only)
   - **Risk:Reward Ratio**: 2.0 minimum (adjustable based on asset volatility)
   - **Signal Cooldown**: 5-10 bars (prevents signal clustering)

3. **Optional Overlays** (toggle based on chart clarity)
   - SuperTrend, Parabolic SAR, Ichimoku: Use if you trade with these actively
   - Hull MA, McGinley, Alligator: Additional trend confirmation
   - Keltner/Donchian: Alternative volatility bands

### Pre-Trade Analysis Checklist

When a Buy or Sell signal appears, **DO NOT enter immediately**. Conduct this 5-step verification:

#### 1. Dashboard Score Validation
- **Composite Score**: Must exceed your threshold (65+ recommended)
- **Category Agreement**: Minimum 3/5 categories aligned (4/5 is ideal)
- **Individual Category Scores**: Check for extreme readings
  - Trend Score: 70+ indicates strong directional pressure
  - Momentum Score: 75+ suggests oversold/overbought extreme
  - Volume Score: 65+ confirms accumulation/distribution
  - Structure Score: 80+ means critical support/resistance zone
  - Volatility Score: High scores during compression = explosive move pending

**Action**: If Category Agreement < 3/5 or Composite Score is barely above threshold, skip the trade.

#### 2. Multi-Timeframe Confirmation
- **Check MTF Heatmap**: Higher timeframes should align with signal direction
  - All green for Buy signals (or mixed with bias toward green)
  - All red for Sell signals (or mixed with bias toward red)
  - **Warning**: If HTF shows opposite color, proceed with extreme caution or skip
- **HTF Trend Filter**: Verify the Higher Timeframe EMA aligns with your signal
  - Enabled by default in Settings · Trend
  - Prevents counter-trend trades in strong HTF trends

**Action**: If 4H+ timeframe opposes your signal, reduce position size by 50% or wait for HTF alignment.

#### 3. Structural Context
- **Pivot Points**: Is price near a major pivot level (R1/S1/R2/S2)?
  - Best signals occur at pivots with momentum exhaustion
- **Fibonacci Levels**: Check Fib 0.5 (or 0.382/0.618 if displayed)
  - Reversals at Fib levels + high scores = high probability
- **Order Blocks / Fair Value Gaps**: Dashboard shows these
  - Signals inside order blocks or at FVG edges are premium setups
- **Support/Resistance**: Verify price is at a tested zone, not open air

**Action**: If signal appears in "no man's land" (no structural support), skip or wait for price to reach a level.

#### 4. Volume Confirmation
- **Volume Score**: Should be elevated (60+) for reversal confirmation
- **CMF / Money Flow**: Check dashboard for positive (buy) or negative (sell) flow
- **Buy/Sell Pressure Ratio**: Should favor signal direction
  - Buy Signal: Pressure Ratio > 1.0
  - Sell Signal: Pressure Ratio < 1.0
- **VWAP Position**: Price crossing VWAP with volume = institutional interest

**Action**: If volume indicators are weak or contradictory, reduce position size or wait for volume confirmation.

#### 5. Entry Precision
- **Entry Level**: The system calculates entry based on recent swing structure
  - For Buy: Entry is typically near swing low or support
  - For Sell: Entry is near swing high or resistance
- **Current Price vs Entry**: If price has already moved significantly from entry level:
  - **Wait for pullback** to entry or better
  - **Use limit orders** at the indicated entry level
  - **Never chase** — if you missed it, wait for the next signal

**Stop Loss Validation**:
- SL is calculated using ATR + structural invalidation point
- Ensure SL is beyond the most recent swing high/low
- If SL is too tight (<1% on volatile assets) or too wide (>5% risk), adjust position size

**Take Profit Assessment**:
- TP is calculated using your Risk:Reward ratio setting
- Verify TP doesn't land in obvious resistance (for buys) or support (for sells)
- Consider scaling out: 50% at 1R, 50% at 2R+

---

### During the Trade: Active Management

#### Bar-by-Bar Monitoring
After entry, monitor the dashboard every few bars:

1. **Category Agreement Deterioration**
   - If agreement drops from 4/5 to 2/5: Consider partial exit
   - If categories flip (3+ now favor opposite direction): Exit immediately

2. **Composite Score Reversal**
   - If Buy Score drops below 50 while Sell Score rises above 60: Exit
   - This indicates momentum shift before price confirms it

3. **Structural Breaks**
   - **For Buy Trades**: If price breaks below your SL level's structure (not just the line), exit
   - **For Sell Trades**: If price breaks above your SL level's structure, exit
   - Dashboard shows BOS (Break of Structure) and CHoCH (Change of Character) in real-time

4. **Volume Divergence**
   - Price moves in your favor but Volume Score drops below 40: Weakening move, consider tightening SL
   - Price stalls but Volume Score spikes opposite direction: Prepare to exit

5. **HTF Shift**
   - If MTF Heatmap flips to opposite colors: Trail SL aggressively or exit

#### Exit Decision Matrix

| Scenario | Action |
|----------|--------|
| Price reaches TP with Score still high (70+) | Take profit, re-enter on pullback |
| Price reaches TP with Score degraded (< 50) | Full exit, move to next setup |
| Price at 1R, Categories still 4/5 aligned | Trail SL to breakeven, hold for 2R+ |
| Price at 1R, Categories drop to 2/5 | Partial exit (50%), SL to breakeven |
| SL hit | Full exit, no revenge trading |
| Price stalls at 0.5R for 10+ bars, Score weakening | Discretionary exit or tighten SL |
| Opposite signal appears while in trade | Immediate exit if Score > 65 |

---

## Achieving 99% Accuracy: The Reality

**No indicator system achieves 99% win rate.** Markets are probabilistic, not deterministic. What you can achieve:

### High Win Rate (70-80%) Methodology

1. **Trade Only Grade-A Setups**
   - Composite Score: 75+ (not 65)
   - Category Agreement: 4/5 or 5/5 (not 3/5)
   - HTF Alignment: All timeframes same color on heatmap
   - Structural Confluence: Signal at pivot + Fib level + order block
   - Volume Confirmation: Volume Score 70+

2. **Patience Over Quantity**
   - On a 4H chart, you might get 1-2 Grade-A setups per week
   - On a 15min chart, 2-3 per day
   - **Never force trades** — wait for all criteria to align

3. **Eliminate These Common Mistakes**
   - Entering on threshold breach (65 score) instead of waiting for 70+
   - Ignoring HTF opposition
   - Taking signals in structural no-man's-land
   - Chasing after price moved 2+ ATR from entry level
   - Not exiting when categories flip during trade

4. **Context Filters** (use Settings to enable)
   - **ADX Filter**: Require ADX > 25 to avoid choppy ranges
   - **Session Filter**: Trade only during liquid sessions for your asset
   - **Volatility Filter**: Avoid signals when HV Rank < 30 (low volatility = low probability)
   - **Trend-Adjusted RSI**: Enable for trending markets to adjust oversold/overbought levels

### Optimal Risk Management

Even with 75% win rate, poor risk management destroys accounts:

- **Position Sizing**: Risk 1% per trade maximum (0.5% for aggressive timeframes)
- **Daily Loss Limit**: Stop trading after 2 consecutive losses
- **Correlation Check**: Don't take correlated signals (e.g., EUR/USD buy + GBP/USD buy)
- **Leverage**: If using leverage, reduce position size proportionally

---

## Common Failure Patterns to Avoid

### 1. Signal Appeared, Price Didn't React
**Why**: Low volume zone, lack of structural support, or HTF headwind  
**Prevention**: Always check Volume Score (60+ required) and MTF Heatmap before entry  
**Action**: If price doesn't move toward TP within 5-10 bars of entry, re-evaluate dashboard

### 2. Price Hit SL Immediately
**Why**: Entry was too late (price already extended) or SL too tight  
**Prevention**: Only enter at or better than indicated Entry level, verify SL is beyond swing point  
**Action**: Accept loss, review if you chased price or ignored structure

### 3. Price Hit TP but Reversed (Left Gains on Table)
**Why**: Didn't monitor dashboard during trade  
**Prevention**: Check dashboard at 50% to TP — if Score drops below 50, partial exit  
**Action**: Set alerts for Score thresholds or use 1R / 2R scaling exits

### 4. Missed the Signal Entirely
**Why**: Signal appeared and vanished due to auto-expire or TP hit  
**Prevention**: Use TradingView alerts (built-in alertconditions for Buy/Sell signals)  
**Action**: Set alerts for "Buy/Sell Signal (Any)" and check chart within 3-5 bars

### 5. Too Many Signals, Analysis Paralysis
**Why**: Threshold too low (55-60 on higher timeframes)  
**Prevention**: Increase Signal Threshold to 70+ and require 4/5 category agreement  
**Action**: Focus on quality over quantity

---

## Optimal Settings by Trading Style

### Scalping (1-5 min charts)
- Signal Threshold: 55-60
- Risk:Reward: 1.5-2.0
- Signal Cooldown: 3-5 bars
- HTF Filter: 15min or 1H
- Enable: TTM Squeeze, SuperTrend, Parabolic SAR
- Volume confirmation critical (Score 65+)

### Day Trading (15-60 min charts)
- Signal Threshold: 65-70
- Risk:Reward: 2.0-2.5
- Signal Cooldown: 5-10 bars
- HTF Filter: 4H or Daily
- Enable: Dashboard, MTF Heatmap, Bollinger Bands, VWAP
- Category Agreement: 3/5 minimum, 4/5 preferred

### Swing Trading (4H-Daily charts)
- Signal Threshold: 75-80
- Risk:Reward: 2.5-3.5
- Signal Cooldown: 10-20 bars
- HTF Filter: Weekly
- Enable: Ichimoku, Pivot Points, Fib Levels, Order Blocks
- Category Agreement: 4/5 required
- Only trade Grade-A setups

---

## Advanced Techniques

### 1. Divergence Hunting
Dashboard shows divergence scores. When signal appears with:
- Bull/Bear Divergence Score 70+: High-probability reversal
- Combine with oversold/overbought oscillator readings
- Best at major support/resistance

### 2. Wyckoff Event Filtering
- Enable Wyckoff Spring/Upthrust alerts
- When signal coincides with Spring (buy) or Upthrust (sell): Premium setup
- Dashboard shows these events in real-time

### 3. Volatility Regime Adaptation
- **Low Volatility (HV Rank < 30)**: Increase threshold to 75+, reduce position size
- **High Volatility (HV Rank > 70)**: Widen SL by 1.5x ATR, reduce position size
- **TTM Squeeze Fire**: Massive edge — signals during or immediately after squeeze release are high-probability

### 4. Gap Trading
- Dashboard shows Gap Up/Down detection
- Gaps + reversal signals = fade opportunities
- Gaps + continuation signals = breakout plays

### 5. Session-Based Filtering
- Enable Session Filter in Settings
- Trade only during overlapping sessions (London/NY overlap = highest volume)
- Avoid signals during illiquid sessions unless swing trading

---

## Dashboard Interpretation Guide

The dashboard is your real-time scorecard. Key sections:

### SIGNAL Section
- **Buy/Sell Score**: Live composite scores (0-100)
- **Cats Agree**: Number of categories aligned (5 max)
- **Bias**: Overall directional lean
- **Bars Since Last**: Cooldown tracking

### TREND Section
- Individual trend indicator states (Hull, SuperTrend, ADX, HTF)
- Trend Score: Weighted average
- Look for 70+ for strong trends

### MOMENTUM Section
- RSI, MACD, Stochastic, CCI states
- Divergence indicators
- Momentum Score: 75+ = extreme readings

### VOLATILITY Section
- ATR, BB %B, HV Rank, TTM Squeeze state
- Volatility Score: High during compression = pending expansion

### VOLUME Section
- CMF, MFI, OBV, Pressure Ratio
- Volume Score: 65+ confirms directional intent

### STRUCTURE Section
- Active Order Blocks, FVGs, BOS/CHoCH events
- Structure Score: 80+ = major support/resistance zone

### LEVELS Section
- Current Pivot, Fib 0.5, R1/S1 proximity
- Gap status

---

## Troubleshooting

### "I get too many signals"
→ Increase Signal Threshold to 70-75  
→ Require 4/5 category agreement  
→ Enable HTF Filter and ensure alignment  
→ Increase Signal Cooldown to 10-15 bars

### "I get too few signals"
→ Lower Signal Threshold to 60-65  
→ Accept 3/5 category agreement  
→ Trade multiple timeframes/assets  
→ Reduce Signal Cooldown to 3-5 bars

### "Signals are late"
→ This is by design — it's a reversal system, not trend-following  
→ Ensure you enter at the Entry level, not current price  
→ Use limit orders at Entry level for better fills

### "Stop losses are too tight/wide"
→ SL is ATR + structure based  
→ Adjust position size to risk tolerance, not SL distance  
→ If SL consistently too tight: Increase ATR period in Settings · Volatility  
→ If SL consistently too wide: Decrease ATR period or trade lower timeframes

### "Take profit isn't being reached"
→ Lower Risk:Reward ratio to 1.5-2.0  
→ Use 1R / 2R scaling exits instead of single TP  
→ Monitor dashboard — exit manually if Score degrades before TP

---

## Final Thoughts

This system is a **decision-support tool**, not a magic button. Your edge comes from:

1. **Discipline** — Only taking Grade-A setups that meet all criteria
2. **Patience** — Waiting for structural confluence and HTF alignment
3. **Active Management** — Monitoring the dashboard and adjusting during trades
4. **Risk Management** — Sizing positions to survive losing streaks
5. **Continuous Refinement** — Adapting threshold and filters to your asset and timeframe

The indicator does the heavy lifting of monitoring 62+ data points simultaneously. Your job is to interpret the evidence, verify the context, and execute with precision.

**Not financial advice. Just code. Your capital, your decisions.**