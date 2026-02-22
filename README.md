## Pricing_Future

### Cost of Carry Model
The Cost of Carry Model is the standard approach in the industry for pricing future/forward contracts.  
Main concept:
Future price = Spot price + Cost of buying now - Benefit of buying now

### Product type
1. Equity Future
- Single stock future
- Index future
2. Commodity Future

-------------------------------------------------------------------------------------------------------------------  
Not indsutry practise (just textbook knowlegde, it is a "sticky" spread , below model only care about the hedging cost ) \
Tv = ( bid price + ask price )/2 
- Bid price --> the max price willing to buy future --> implied short stock (short sales stock)
  - Paying the borrowing cost of stock (short sales borrowing cost)
  - Paying back the dividend to stock lender (broker)
  - Gaining the interest of cash amount from short selling the stock 

Bid price = Spot price + (short sales borrowing cost + dividend) - (interest of cash amount from short selling the stock )
    
- Ask price --> the min price willing to sell future --> implied long stock
  - Borrowing cash to long stock ( financing cost)
  - Gaining dividend 

Ask price = Spot price + (financing cost) - dividend

---------------------------------------------------------------------------------------------------------------------
Industry practise of quoting the future contract:

Bid quote = TV - Spread function/2 \
Ask quote = TV + Spread function/2

TV = ( MidPriceₜ× Forecastₜ × Scaling) + InventorySkewₜ \
Remark:
- MidPriceₜ: midpoint of best bid and ask in the market.
- Forecastₜ: model estimate of relative fair value vs. market (e.g. expected drift, short-term alpha).
- Scaling: adjustment to normalize forecast into price space (think: converting z-score or expected return into basis points).
- InventorySkewₜ: bias adjustment to manage position inventory (e.g. if long, shift FV down to encourage selling).

Spread function = f(Risk,MarketSpreadₜ,Aggressiveness)\
Remark:
- where f= α⋅MarketSpreadₜ + β⋅RiskPenalty − γ⋅AggressionFactor  (α, β, γ: tunable coefficients.)
- MarketSpreadₜ: observed bid–ask spread.
- RiskPenalty: widens spread when volatility, inventory, or gamma exposure increases.
- AggressionFactor: tightens spread when trying to capture flow or compete for order flow.

Optional adjustment: \
Remark:
- Adverse selection penalty: widen quotes during momentum or when market depth thins out.
- Latency buffer: add a time-decay penalty to prevent stale quotes.
- Cross-asset skew: bias FV based on correlated assets or synthetic parity (e.g. ETF vs. basket).

Your fair value is your model-adjusted midprice, including any intentional skew to manage your book.
Your spread is a function of how risky it is to quote tightly and how aggressive you want to be.
Your quotes are just that fair value plus/minus the spread.

