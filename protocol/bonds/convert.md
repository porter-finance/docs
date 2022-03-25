# Convert

## Summary

Convert bonds allow DAOs and other on-chain entities to borrow stablecoins using their project tokens as collateral. Any time before the maturity date, lenders can convert their bonds into a set amount of collateral tokens. At maturity, if the debt is not repaid, lenders can redeem their bonds for the collateral supplied.&#x20;

A Convert bond is most similar to convertible debt. It gives the lender upside in the project token along with the interest rate and any option premium earned. When purchasing Convert bonds, lenders are effectively selling a [put option](../../financial-concepts/convertible-bonds/put-options.md) on the collateral token, buying a [call option](../../financial-concepts/convertible-bonds/call-options.md) on the collateral token, and purchasing a [zero coupon bond](../../financial-concepts/zero-coupon-bonds/).&#x20;

> Convert Bond = Zero Coupon Bond - Put Options + Call Options

Therefore, they are exposed to the collateral token's downside past the option strike price but recieve an option premium and a call option for taking on this "default" risk. This results in boosted yields and token upside for the lender, while supplying a liquidation-free loan to the borrower.

## Why should investors buy Convert bonds?

Convert bonds offer investors superior returns compared to other DeFi lending platforms because they combine lending with the sale and purchase of options. In terms of risk profile, Convert bonds sit in between stablecoin farming and longing tokens.&#x20;

![](<../../.gitbook/assets/image (56).png>)

Convert bonds are ideal for yield farmers who have a medium risk portion of their portfolio used to chase higher returns. They are also for investors looking to derisk while still maintaining upside in a project.

## Why should DAOs sell Convert bonds?

Convert bonds allow DAOs to borrow funds without the fear of liquidation by using their project tokens, which make up the majority of their treasuries. Borrowers using collateralized debt positions on other protocols must maintain a particular collateral ratio or risk being liquidated. DAOs are protected from extremely costly liquidations by the inherent put in the Convert bond. To reduce their cost of borrowing, DAOs may find it worthwhile to sell call options on their tokens.

If the protocol is expected to grow, a DAO might be better off delaying the sale of its project tokens, borrowing now, and selling fewer tokens at a higher price later. Or, even better, using increased protocol revenue from the growth funded by debt to pay off said debt and never having to sell governance tokens.

## Example

As of writing, Uniswap has \~$2B of UNI token in their treasury and no stablecoins, so they may want to borrow some stablecoins to diversify their treasury and fund expenses. But they want to lower their cost of borrowing as much as possible so they issue a Convert bond.

Let's say Uniswap issues 1,000,000 Convert bonds maturing in 12 months and backs each with 0.5 UNI as collateral with each bond being convertible into 0.04 UNI.  When selling these bonds, Uniswap is effectively selling a zero coupon bond, buying a put option with a strike price of $2, and selling a call option with a strike price of $25.&#x20;

#### Put options strike price

The put options strike price comes from Uniswap's ability to default on the bond and "sell" the collateral for the value owed at maturity, which is $1. Uniswap having the ability to sell the collateral (0.5 UNI) for $1 means they have a UNI put option with a strike price of $2 ($1/0.5 UNI = $2/UNI strike price).&#x20;

#### Call options strike price

The call options strike price comes from the ability of the bondholder to convert their bonds into 0.04 UNI, effectively "buying" the collateral for the value owed at maturity, which is $1. The bondholder having the ability to buy the convertible tokens (0.04 UNI) for $1 means they have a UNI call option with a strike price of $25 ($1/0.04 UNI = $25/UNI strike price).&#x20;

To determine the value of the Convert bond, we have to subtract the price of the puts from the zero coupon bond and add the price of the calls. Note that only 0.5 puts are being sold because there are only 0.5 UNI being used as collateral and there are only 0.04 calls being sold because there are only 0.04 UNI being used as convertible tokens.

### Simple bond value at issuance

To determine the value of the Simple bond at issuance, we have to subtract the value of the put from the value of the zero coupon bond at issuance.

> Simple Bond = Zero Coupon Bond - Put Options

Let's determine the value of both starting with the zero coupon bond.

#### Zero coupon bond value at issuance

The value of the zero coupon bond at issuance is determined by the required rate of interest and the time until maturity. The equation below is further explained in [ZCB pricing](../../financial-concepts/zero-coupon-bonds/zcb-pricing.md). We will assume a required rate of interest of 5%.&#x20;

> Zero Coupon Bond = F ÷ (1 + r)^n
>
> Zero Coupon Bond = $1 ÷ (1 + 0.05)^1 ≈ $0.95

Therefore, the value of the zero coupon bond at issuance is $0.95.

#### Put options value at issuance

The value of the options is impossible to determine exactly, but we can use [Black Scholes](https://www.investopedia.com/terms/b/blackscholes.asp) to estimate it. Using a current UNI price of $10, strike price of $2, risk free rate of 5%, annualized volatility of 100%, and time to maturity of 1 year, we get a price of $0.08/option but we only need 0.5 because there are 0.5 UNI as collateral per bond. That gives us $0.04 for our puts ($0.08 \* 0.5 = $0.04).

#### Call options value at issuance

Using a current UNI price of $10, strike price of $25, risk free rate of 5%, annualized volatility of 100%, and time to maturity of 1 year, Black Scholes gives a price of $1.53/option but we only need 0.04 because each bond is only convertible into 0.04 UNI. That gives us $0.06 for our calls ($1.53 \* 0.04 = $0.06).

#### Convert bond value at issuance

To get the value of the Convert bond at issuance, we subtract the value of the puts from the value of the zero coupon bond and add the call options.

> Convert Bond = Zero Coupon Bond - Put Options + Call Options
>
> Convert Bond = $0.95 - $0.04 + $0.06 = $0.97

So we can estimate the value of these Convert bonds to be $0.97 / bond at issuance.

### Convert bond value at maturity

To determine the value of the Convert bond at maturity, we again subtract the value of the puts from the value of the zero coupon bond and add the value of the calls but this time, we determine the values at maturity. Let's determine the value of all three starting with the zero coupon bond.

#### Zero coupon bond value at maturity

The value of the zero coupon bond at maturity will always be $1 regardless of the UNI token price as shown in the graph below.

![](<../../.gitbook/assets/image (21).png>)

This can be confirmed by solving for the zero coupon bond value when time to maturity (n) is 0.

> Zero Coupon Bond = F ÷ (1 + r)^n
>
> Zero Coupon Bond = $1 ÷ (1 + 0.05)^0 = $1

#### Put options value at maturity

Unless the price of UNI is below $2, the UNI puts are worthless at maturity. They increase to $1 as the price of UNI goes toward $0.

![](<../../.gitbook/assets/image (45).png>)

The put option pricing equation at maturity is greatly simplified when calculated at maturity.

> Put Option = MAX(Strike Price - Token Price, $0)

#### Call options value at maturity

Unless the price of UNI is above $25, the UNI calls are worthless at maturity. There is no cap to how much the calls can be worth.

![](<../../.gitbook/assets/image (28).png>)

The call option pricing equation at maturity is greatly simplified when calculated at maturity.

> Call Option = MAX(Token Price - Strike Price, $0)

#### Convert bond value at maturity

ow, to get the value of the Simple bond at maturity, we subtract the value of the puts from the value of the zero coupon bond and add the value of the call options. Remember, we only need 0.5 put options because there are 0.5 UNI as collateral per bond and 0.04 call options because there are 0.04 UNI as convertible tokens per bond.

> Zero Coupon Bond = $1
>
> Put Option = MAX(Strike Price - Token Price, $0)
>
> Call Option = MAX(Token Price - Strike Price, $0)
>
> Convert Bond = $1 - 0.5 \* MAX(Strike Price - Token Price, $0) + 0.04 \* MAX(Token Price - Strike Price, $0)

As the price of UNI drops below $2, the value of the put increases which decreases the value of the Convert bond. As the price of UNI rises above $25, the value of the call increases which increases the value of the Convert bond.

![](<../../.gitbook/assets/image (50).png>)

### Convert bond returns

If held until maturity, the returns of the Convert bond are equal to the value at maturity minus the value at issuance.

> Return = Convert Bond \[t=maturity] - Convert Bond \[t=issuance]

If a lender purchases the bonds at the price calculated above of $0.97 and the options expire worthless, the lender will redeem their bonds for $1 each and make $0.03, which is approximately a 3% return ($0.03 / $0.97 ≈ 3%).

However, if the value of UNI increases above $25, the return could be much higher. What would the return be if UNI increased to $50?

> Zero Coupon Bond = $1
>
> Put Option = MAX($2 - $50, $0) = $0
>
> Call Option = MAX($50 - $25, $0) = $25
>
> Convert Bond = $1 - 0.5 \* $0 + 0.04 \* $25 = $2

If UNI is trading at $50, the lender will convert their bonds into 0.04 UNI valued at $2 and make $1.03 ($2 - $0.97), which is approximately a 106% return ($2 / $0.97 ≈ 106%).
