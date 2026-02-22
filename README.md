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
Not indsutry practise (just textbook knowlegde, it is a "sticky" spread , below model only care about the hedging cost ) 
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
Possible industry practise of quoting the future contract:
Bid/Ask price = TV + spread ( i.e. hedging cost,
