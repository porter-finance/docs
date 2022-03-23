# Option pricing

The three biggest factors that determine the price of an option are:

* **Token price** - the token price relative to the strike price
* **Time** - the amount of time remaining until expiration
* **Implied volatility** - how much the token is expected to move until expiration

### Token Price

If an option is in the money, then it is said to have intrinsic value. For example, the $80 strike call for a token worth $100 can be immediately exercised to realize a $20 gain. When you buy this call, the $20 intrinsic value is baked into the price of the option (you don’t get it for free).

### Time

The more time to expiry, the more time there is for the token to move and the more expensive the option is. The price of an option is strictly increasing with respect to time**.**

### Implied volatility

The implied volatility (IV) __ of an asset expresses how much the asset is expected to move until expiration as a percentage. The _higher_ the IV of an asset, the _more_ it is expected to move, and the more expensive options are. Similarly, if IV is low, options will be cheaper.
