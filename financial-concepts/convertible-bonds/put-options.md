# Put options

### Understanding Put Options  <a href="#mntl-sc-block_1-0-9" id="mntl-sc-block_1-0-9"></a>

A put option gives the holder the right to sell 1 token at the strike price up until the expiration date.

For example, a single put option contract may give a holder the right to sell 1 UNI token at $5 up until the expiration date six months later. As the value of UNI goes down, the price of the option contract goes up, and vice versa. The put option buyer may hold the contract until the expiration date, at which point they can sell the 1 UNI token.

You pay a fee to purchase a put option, called the [premium](https://www.investopedia.com/terms/p/premium.asp). It is the price paid for the rights that the put option provides. If at expiration the underlying token is above the strike price, the put buyer loses the premium paid. This is the maximum loss.

### Value at expiration

If the underlying token's market price is below the strike price at expiration, the profit is the difference in prices, minus the premium.

For example, if UNI is trading at $4 at expiry, the option contract strike price is $10, and the options cost the buyer $2, the profit is $(10 - 2) - $4 = $4

Now, if at expiration UNI is trading above $10, obviously the buyer won't exercise the option to sell the token at $10 apiece, and the option expires worthless. The buyer loses $2 for each contract they bought.

![](<../../.gitbook/assets/image (34).png>)
