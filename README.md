### KlinesAPI — Indian Stock Market Screener & Backtesting Engine

KlinesAPI is a high-speed REST API built for backtesting and technical analysis of Indian equities. It provides adjusted OHLCV data starting from 2020, with daily updates by 10 PM IST covering all NSE listed instruments.

- Every dataset accounts for corporate actions that materially impact price continuity like splits, bonus issues, rights offerings, and mergers.
- Symbol changes are tracked daily, so a lookup for a ticker that was renamed simply works, without any manual adjustment on your end.
- The data is built for chart analysis and quantitative screening, not for taking actionable trading decisions.
- The screener supports 27 technical indicators out of the box including SMA, EMA, WMA, RMA, TEMA, HMA, VWAP, all pivot levels, Heikin-Ashi transforms, and more.
- Indicators can be chained, offset by days, and combined with arithmetic expressions to build complex multi-condition screens across the entire market in a single query.

### Pricing

Queries are credit-gated with a transparent, pay-as-you-go model so you only pay for exactly what you compute. Credits are the unit of usage. For 1 rupee recharge you get 50 credits.

- **Base deduction — Symbol query:**  
  Credits = CEIL((output cells / 500) × multipliers)  
  Output cells = filtered rows × columns requested.  
  Example: 200 rows × 3 columns = 600 cells = 1.2 credits = ₹0.024

- **Base deduction — All-symbol scan (no symbol filter):**  
  Credits = 42 × trading days in range × multipliers  
  Example: 1 day × SMA (CCM 1.2) = 50.4 credits = ₹1.01

- **Multipliers:**  
  - Operational cost multiplier — based on number of filter conditions  
  - Compute cost multiplier (CCM) — based on indicator complexity  
  - Both multipliers stack multiplicatively on the base.

- **Grace periods:**  
  - Identical queries within 24 hours are served from cache at no charge.  
  - Grace applies to credits only. Every request counts toward the monthly request limit regardless of grace.

### Plans

| Plan        | Recharge Criteria                                                                                                                                           | Key Features                                                                                                                                                                                                                             | Request Limit              |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| Test user   | Any recharge between ₹1 and ₹999 qualifies. Maximum 3 test recharges per user lifetime. After 3 test recharges, a minimum ₹1000 recharge is required to continue as a normal user. | Access to all endpoints and indicators.                                                                                                                                                                                                                                        | Up to 1000 requests per month |
| Normal plan | Total recharge below ₹5000.                                                                                                                                 | Access to all endpoints and indicators. Bug reports rewarded with 7500 credits. Support handled on a standard queue basis.                                                                                                              | Up to 2000 requests per month |
| Super plan  | Total recharge ₹5000 or above.                                                                                                                              | All normal plan benefits. Priority support queue. If a support request is not resolved within the committed SLA, 7500 credits are credited automatically for each day of delay. Bug reports rewarded with 25000 credits.                | Up to 10000 requests per month |

### Important notes

- All recharges are non-refundable regardless of whether credits are used.
- Credits do not expire.
- Use a just-in-time approach — recharge small amounts as you need them rather than in bulk.
- You are billed only for what you actually query.
- The data is adjusted for corporate actions with reasonable accuracy and is intended for research and backtesting purposes only.
- Results from this API should not be used to make investment decisions.

### Access

The API is currently available by invitation. To request access, email:

vkydtech@gmail.com  
Subject: KLINES API ACCESS

Include a brief note on your intended use case to suggest appropriate price plan.
