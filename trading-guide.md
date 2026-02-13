# Trading Guide: Indices & Funds Indicators
### A Step-by-Step Playbook for 2H / 3H / 4H Timeframes

---

## How Your Indicator Actually Works (The 30-Second Version)

Your indicator scores every single bar across **five categories**, each weighted differently:

| Category | Weight | What It Measures |
|---|---|---|
| **Exhaustion** | 20% | Is the move running out of steam? (RSI oversold, Z-score extremes, volume climax, BB extremes) |
| **Reversal** | 18% | Are momentum indicators actively turning? (MACD crossover freshness, RSI crossing oversold/overbought, Stoch crosses) |
| **Structure** | 22% | Are price patterns confirming? (Engulfings, hammers, support/resistance, pivot breaks, divergences) |
| **Volume** | 22% | Is money flowing in the right direction? (OBV, CMF, Klinger, pressure ratio, Twiggs, NVI/PVI) |
| **Trend Alignment** | 18% | Do higher timeframes agree? (Daily, 4H, 1H, 15m, 5m EMAs + VWAP + Vortex + McGinley) |

The raw score from these five categories gets multiplied by **meta-multipliers** — bonus/penalty factors based on Z-score extremes, volatility rank, ADX regime, lagging indicator consensus, and VIX regime. The final score (0–100) must pass an **adaptive threshold** (top N% of the last 100 bars) to trigger.

A signal only fires when **all** of these are true simultaneously:

- Score ≥ adaptive threshold (top 10% by default)
- Buy dominance ≥ 8 points over sell (or vice versa)
- Dominance ratio ≥ 1.25×
- At least 3 of 5 categories agree
- At least some exhaustion + reversal signal present
- Cooldown period passed (default 5 bars)
- VIX regime not suppressing the direction
- R² regime is OK (trend or mean-reversion conditions valid)

**This means signals are rare and selective by design.** On a 2H chart, you might see a few signals per week on volatile instruments, or one every couple of weeks on calmer ones.

---

## Part 1: Setting Up Your Chart

### Recommended Default Settings for 2H–4H

The defaults are solid for indices and large-cap ETFs. Here are the only tweaks worth considering:

**Keep ON (defaults):**
- Display Buy/Sell Signal ✓
- Display SL/TP Levels ✓ (Zones mode)
- Display VWAP Line ✓
- Display MTF Trend Heatmap ✓
- Display Bollinger Bands ✓
- VIX regime filter ✓
- MA Stack Filter ✓
- Structure Filter ✓
- Candle Direction Filter ✓
- HTF RSI Filter ✓

**Turn ON for your setup (not default):**
- **Display Dashboard → ON** — this is your command center. It shows you every sub-indicator at a glance so you can double-check signals.
- **Display Historical Signals → ON** (temporarily) — use this to back-test visually on your chart. Turn it off once you're comfortable.

**Consider for crypto specifically:**
- VIX regime filter → OFF (VIX doesn't directly correlate to crypto; or keep it on for BTC which has some correlation to risk assets)
- Use Session Filter → OFF (crypto trades 24/7)

**Leave OFF unless you know what they do:**
- Extended oscillators (adds noise for 2-4H)
- SMC / Wyckoff / FVG (advanced — enable only once you understand them)

### Timeframe Setup

Open **three chart tabs** in TradingView:

1. **Your trading timeframe** (2H, 3H, or 4H) — this is where the indicator runs and signals appear
2. **One timeframe higher** (Daily) — for context: is the daily trend with you or against you?
3. **One timeframe lower** (1H or 30m) — for fine-tuning your entry after a signal

---

## Part 2: When a Signal Fires — The Full Workflow

### Step 1: The Signal Appears — Don't Touch Anything Yet (30 seconds)

A BUY or SELL arrow (▲ or ▼) appears on a **confirmed bar** (the bar has closed). You'll see:

- **Entry Zone** (blue box) — the ideal area to enter
- **Stop Loss** (red line/zone) — where you're wrong
- **Take Profit** (green line/zone) — your target(s)

**First thing: hover over the signal arrow.** The tooltip shows you everything:

```
Buy Signal
Dominance: +15.2 (×1.45)
Exhaustion:  71% (wt 20%)
Reversal:    54% (wt 18%)
Structure:   48% (wt 22%)
Volume:      62% (wt 22%)
Trend Align: 55% (wt 18%)
━━━━━━━━━━━━━━━━━━━━
Cats agree: 3 strong + 5/5 any
R²: 0.45 | Z: -1.8
HV Rank: 42%
P/D Zone: Discount ✓
Lagging bull/bear: 12/4 (of 16)
VIX regime: 17.3 OK
Divergence: Yes (+8)
━━━━━━━━━━━━━━━━━━━━
Entry: 5,432.15
SL: 5,388.50 (-0.8%)
TP: 5,519.80 (+1.6%)
R:R = 1:2.0
```

### Step 2: The Confidence Check (1–2 minutes)

Read the tooltip and evaluate signal quality using this grading system:

**Grade A Signal (highest confidence — full position):**
- Score ≥ 80 (the indicator calls this "High" confidence)
- 4+ categories agree at "strong" level
- Dominance ratio ≥ 1.5×
- Z-score is in your favor (negative for buys, positive for sells)
- P/D Zone shows "Discount ✓" for buys or "Premium ✓" for sells
- VIX regime shows "OK"
- Divergence: Yes

**Grade B Signal (good — standard position):**
- Score 65–80 ("Medium" confidence)
- 3+ categories agree
- Dominance ratio 1.25–1.5×
- Most conditions favorable

**Grade C Signal (proceed with caution — half position or skip):**
- Score < 65 but still triggered (means adaptive threshold is low — quiet market)
- Only 3 categories barely agree
- HV Rank > 85% with no exhaustion (⚠ means volatility is penalizing)
- Lagging indicators are split (e.g., 8/8 instead of clearly directional)

### Step 3: The Multi-Timeframe Cross-Check (2–3 minutes)

Now check your other chart tabs:

**Check the Daily chart:**
- Is price above or below the Daily EMA 50? (The indicator's HTF Trend filter already checks this, but look yourself)
- For a BUY: Is the daily making higher lows? Good. Making lower lows? Be more cautious — you're counter-trend.
- For a SELL: Is the daily making lower highs? Good. Making higher highs? Be more cautious.
- Check the Dashboard's MTF Heatmap: are the Daily and 4H dots green (for buys) or red (for sells)? If they conflict with your signal, reduce position size.

**Check the 1H chart:**
- Is the current 1H candle pulling back into the Entry Zone shown on your trading timeframe? This is ideal entry timing.
- Is the 1H showing a mini-trend in the signal direction? Even better.
- If the 1H is already extended far past the entry zone, you may have missed the optimal entry. Wait for a pullback or skip.

**Check VIX (for indices/funds):**
- The indicator already filters VIX, but glance at it. VIX > 20 with buy signal = be careful, reduce size. VIX < 15 with sell signal = the market is complacent, sells are harder.

### Step 4: Decide Your Position Size

Use this simple framework based on your signal grade:

| Grade | Position Size | Risk Per Trade |
|---|---|---|
| A | 100% of your standard | 1–2% of account |
| B | 75% of your standard | 1% of account |
| C | 50% of your standard | 0.5% of account |

**Example:** You have a $10,000 account, your standard risk is 1.5% ($150). A Grade B signal means you risk $112.50 max on this trade.

### Step 5: Place Your Entry

**Option A — Market Entry (simple, recommended for beginners):**
Enter at market price as soon as you've completed your checks. The signal bar has already closed, so the next bar is your entry. This works well because:
- The entry zone is designed around current price
- You don't risk missing the move waiting for a limit fill
- On 2-4H charts, the difference between market and "perfect" limit entry is usually small relative to your target

**Option B — Limit Order within Entry Zone (better R:R):**
Place a limit order at the **Entry** price shown in the tooltip (or the label on chart). The indicator specifically places this at VWAP, Fib 50, or Order Block if any of those fall within the entry zone. These are intelligent entry points. If price doesn't come back to your limit within 2–3 bars, enter at market or let the opportunity pass.

**Always place your stop loss immediately.** Use the SL level from the indicator. Don't widen it.

---

## Part 3: Managing the Trade

### The First Few Bars After Entry

**Do nothing.** Seriously. The indicator has calculated your SL and TP based on ATR, swing structure, and R:R. Give it room to work. On a 2H chart, "a few bars" means 4–8 hours. On a 4H chart, it means 8–16 hours.

What to watch for:
- If price immediately moves toward your TP: great. Don't touch anything.
- If price moves against you but stays above SL (for buys) or below SL (for sells): this is normal. That's what the stop is for.
- If a candle closes beyond your SL: exit. No second-guessing.

### When to Move Your Stop Loss (Trailing)

Move your SL only in these specific situations:

**After TP1 is hit (if you have two TPs):**
When price reaches TP1 (the first green target), move your stop to **breakeven** (your entry price) on the remaining position. You've now locked in profit on half and have a free trade on the rest.

**After 1× your risk in profit:**
If you entered at 100 and your SL was at 98 (2-point risk), once price reaches 102, move your SL to 100 (breakeven). This is the classic "move to breakeven after 1R" rule.

**On a clear new swing forming in your direction:**
If you bought and price has made a new higher low that's above your entry, move your SL to just below that new higher low (with a small ATR buffer). This is what the indicator's "Swing" SL type does — it anchors to structural levels.

**Never:**
- Move your SL further away from price (widening = adding risk)
- Move your SL based on hope or a "feeling" the trade will work

### When to Move Your Take Profit

**Yes, TPs can and should be adjusted.** Here's when:

**Move TP further (extend your target) when:**
- The MTF Heatmap turns fully green/red (all timeframes aligned after your entry) — the trend is strengthening
- ADX is rising above 25 and you're in a trend trade — momentum is building
- A new candle pattern in your direction forms (bullish engulfing in a buy trade) — confirmation of continuation
- Volume is surging higher in your direction (check the Dashboard's volume section)

In these cases, move your TP to the next structural target: the next resistance zone, Pivot R2 (for buys), or the upper Bollinger Band. The indicator's TP already attempts smart targeting, but strong trends can overshoot.

**Move TP closer (take profit early) when:**
- RSI enters overbought (>70) for buys or oversold (<30) for sells on your trading timeframe — exhaustion risk
- Bollinger Band %B is > 0.95 (price touching upper band) for buys — statistical extreme
- Volume is drying up as price approaches TP — the move is losing steam
- A counter-signal appears (a Sell signal while you're in a Buy trade) — the indicator is now saying the opposite
- VIX spikes sharply (for index trades) — risk-off event
- You see a strong rejection wick at or near your TP level

**Practical rule of thumb:** If price has covered 80% of the distance to TP and momentum is fading (RSI divergence, volume dropping, candle bodies shrinking), take the profit. Don't wait for exact TP hits.

### The Two-TP System

Your indicator automatically decides whether to show one or two TPs based on:
- Whether there are clear S/R zones between entry and the full TP
- Whether the total move is large enough (>8% by default) to justify splitting

When you see TP1 and TP2:
1. **At TP1:** Close half your position. Move SL to breakeven.
2. **At TP2:** Close the rest. Or if conditions are very strong (all MTF aligned, ADX rising), trail with a 1.5×ATR trailing stop beyond TP2.

---

## Part 4: Specific Playbooks by Asset Class

### Indices (S&P 500, Nasdaq, DAX, etc.)

**What works well:**
- The VIX filter is specifically designed for this. Trust it — if VIX > 20 and rising with backwardation, the indicator suppresses buy signals for a reason.
- Use the "Single TP at R:R" setting (default ON for indices). Indices tend to move to R:R targets more reliably than to fixed price levels.
- The yield curve filter adds macro context. Keep it OFF by default but consider turning it ON during periods of yield curve inversion headlines.

**Your edge on 2-4H:**
- Major indices tend to respect VWAP strongly intraday. The indicator uses VWAP as a preferred entry point within the zone — this is a high-probability level.
- Watch for signals that align with the US market session open (9:30 ET). A signal that fires on the bar including 9:30–11:30 AM is especially powerful because it catches the opening momentum.

**Caution:**
- FOMC days, NFP Fridays, CPI releases — the indicator doesn't know about scheduled events. If a signal fires within 4 hours of a major economic release, either skip it or use half size.

### ETFs and Funds (SPY, QQQ, IWM, Sector ETFs)

**What works well:**
- These are essentially indices with slightly different behavior. Same approach as above.
- The correlation filter (benchmarked to SPY for USD instruments) helps identify when a sector ETF is moving with or against the broad market. A buy signal on XLK (tech) while SPY is in a downtrend is counter-trend — reduce size.
- Relative strength (RS ratio > MA) tells you if the fund is outperforming its benchmark. Buy signals with strong RS are higher conviction.

**Tip:**
- For sector rotation plays, look for buy signals on sector ETFs when their relative strength is rising while SPY is neutral. This catches the "sector leadership" rotation.

### Crypto (BTC, ETH, SOL, etc.)

**Key differences from indices:**
- **Turn off VIX filter** for altcoins (no correlation). For BTC, you can keep it on — BTC has moderate correlation with risk assets.
- **Turn off Session Filter** — crypto trades 24/7.
- **Crypto is more volatile**, so the ATR-based SL will naturally be wider. This is correct behavior — don't manually tighten it.
- **Turn on "Use extended oscillators"** for crypto. The extra oscillators (TRIX, KST, Schaff, Coppock) can help detect cycle turns in crypto's more oscillatory nature.

**BTC/ETH on 4H specifically:**
- The 4H timeframe is ideal for crypto swing trading. You catch multi-day moves while filtering out the 15m/1H noise.
- Pay attention to the Z-score in the tooltip. Crypto regularly hits Z-scores of ±3 or more. A buy signal at Z < -2.5 in crypto is a strong mean-reversion setup.
- Volume analysis is less reliable on crypto (exchange volume is fragmented). Weight the Structure and Exhaustion categories more heavily in your mental assessment.

---

## Part 5: Risk Management Rules

These aren't suggestions — treat them as non-negotiable rules:

1. **Never risk more than 2% of your account on a single trade.** For a $10,000 account, that's $200 max loss per trade. Period. Calculate your position size from the SL distance shown by the indicator.

2. **No more than 3 correlated positions at once.** If you have a buy on SPY, a buy on QQQ, and a buy on AAPL, that's essentially one mega-position in US equities. If SPY drops, all three lose.

3. **Daily drawdown limit: 5%.** If you lose 5% of your account in one day, stop trading for the day. Close TradingView. Come back tomorrow.

4. **Respect the SL.** The indicator places SL based on either swing structure or ATR — these are logical invalidation levels. If price reaches your SL, your thesis was wrong. Accept it and move on.

5. **Don't overtrade.** The indicator has a built-in cooldown (5 bars by default). Respect it. On a 2H chart, that's 10 hours between signals. If you're tempted to take more trades, you're not following signals — you're gambling.

---

## Part 6: Quick-Reference Checklists

### Pre-Trade Checklist (Print This Out)

```
□ Signal fired on CONFIRMED bar (not mid-bar)
□ Read tooltip: Score, categories, dominance ratio
□ Grade the signal: A / B / C
□ Checked Daily chart for trend direction
□ Checked 1H chart for entry timing
□ Checked VIX (indices) or skipped (crypto)
□ No major economic event in next 4 hours
□ Position size calculated from SL distance
□ Risk ≤ 2% of account
□ Not exceeding 3 correlated positions
□ Entry order placed with SL set simultaneously
□ TP noted / set
```

### In-Trade Management Checklist

```
□ Price moving toward TP → Do nothing
□ Price hit TP1 → Close half, move SL to breakeven
□ Price 1R in profit → Move SL to breakeven
□ New swing formed → Trail SL to new structure
□ RSI diverging against position → Consider early exit
□ Counter-signal appeared → Exit or tighten SL hard
□ Price hit SL → Exit immediately, no exceptions
□ Price hit TP2 → Exit or trail with 1.5×ATR
```

### Post-Trade Review (Do This Every Time)

```
□ Did I follow the entry checklist?
□ What was the signal grade? Did the outcome match?
□ Did I move SL correctly, or too early/late?
□ Did I take profit at the right time?
□ What would I do differently?
□ Screenshot the trade and save it in a journal
```

---

## Part 7: Common Mistakes and How to Avoid Them

**"The signal fired but I waited and missed the move."**
On 2-4H charts, the entry zone is usually valid for 1–3 bars after the signal. If you didn't enter within that window, let it go. The next signal will come.

**"I moved my stop loss because I 'knew' it would come back."**
This is the #1 account killer. The indicator placed the SL at a structural or ATR level. If price invalidated that level, the trade thesis is dead. Moving your stop is like ignoring the smoke alarm because you don't smell fire yet.

**"I closed at TP but the price kept going."**
Good. You followed the plan and booked profit. The indicator's job isn't to call the exact top or bottom — it's to give you a positive-expectancy trade with defined risk. You won. Don't look back.

**"I keep getting stopped out right before price reverses."**
Check if your SL is too tight. Try increasing the ATR Multiplier SL from 2.0 to 2.5. On volatile instruments (crypto, small-cap ETFs), the default 2.0× ATR might be too close. Also make sure you're not entering mid-zone — enter at the Entry price level, not at the zone edge closest to SL.

**"I trade every signal and I'm losing."**
Grade your signals. Not every signal is Grade A. If you only take Grade A and B signals with proper position sizing, your win rate and R:R should improve significantly. Quality over quantity.

---

*This guide is based on the "Indices & Funds Indicators" by M. Ozolins. It is not financial advice. Always trade with money you can afford to lose and backtest any strategy before committing real capital.*