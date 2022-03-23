# Convert

## Summary

Convert bonds allow DAOs and other on-chain entities to borrow stablecoins using their project tokens as collateral. Any time before the maturity date, bondholders can convert their bonds into a set amount of collateral tokens. At maturity, if the debt is not repaid, the bondholders can redeem their bonds for the collateral supplied.&#x20;

A Convert bond is most similar to convertible debt. It gives the lender upside in the project token along with the interest rate and any option premium earned. When purchasing Convert bonds, lenders are effectively selling a put option on the collateral token, buying a call option on the collateral token, and purchasing a zero coupon bond. Therefore, they are exposed to the collateral token's downside past the option strike price but recieve an option premium and a call option for taking on this "default" risk. This results in boosted yields and token upside for the lender, while supplying a liquidation-free loan to the borrower.

> Convert Bond = Zero Coupon Bond - Put Options + Call Options

## Example

As of writing, Uniswap has \~$2B of UNI token in their treasury and no stablecoins, so they may want to borrow some stablecoins to diversify their treasury and fund expenses. But they want to lower their cost of borrowing as much as possible so they issue a Convert bond.

Let's say Uniswap issues 1,000,000 Convert bonds maturing in 12 months and backs each with 0.5 UNI as collateral with each bond being convertible into 0.04 UNI.  When selling these bonds, Uniswap is effectively selling a zero coupon bond, buying a put option with a strike price of $2, and selling a call option with a strike price of $25.&#x20;

#### Put Options Strike Price

The put options strike price comes from Uniswap's ability to default on the bond and "sell" the collateral for the value owed at maturity, which is $1. Uniswap having the ability to sell the collateral (0.5 UNI) for $1 means they have a UNI put option with a strike price of $2 ($1/0.5 UNI = $2/UNI strike price).&#x20;

#### Call Options Strike Price

The call options strike price comes from the ability of the bondholder to convert their bonds into 0.04 UNI, effectively "buying" the collateral for the value owed at maturity, which is $1. The bondholder having the ability to buy the convertible tokens (0.04 UNI) for $1 means they have a UNI call option with a strike price of $25 ($1/0.04 UNI = $25/UNI strike price).&#x20;

To determine the value of the Convert bond, we have to subtract the price of the puts from the zero coupon bond and add the price of the calls. Note that only 0.5 puts are being sold because there are only 0.5 UNI being used as collateral and there are only 0.04 calls being sold because there are only 0.04 UNI being used as convertible tokens.

### Value at issuance

#### Zero Coupon Bond

The value of the zero coupon bond at issuance is determined by the required rate of interest and the time until maturity. The equation below is further explained in [ZCB pricing](../../financial-concepts/zero-coupon-bonds/zcb-pricing.md). We will assume a required rate of interest of 5%.&#x20;

> Zero Coupon Bond = F ÷ (1 + r)^n
>
> Zero Coupon Bond = $1 ÷ (1 + 0.05)^1 = $0.952

The value of the zero coupon bond at issuance is $0.952 regardless of the UNI token price.

#### Put Options

The values of the options are impossible to determine exactly, but we can use Black Scholes to estimate them. Using a current UNI price of $10, strike price of $2, risk free rate of 5%, annualized volatility of 120%, and time to maturity of 1 year, we get a price of $0.1756/option but we only need 0.5 because there is 0.5 UNI as collateral per bond. That gives us $0.0878 for our puts.

#### Call Options

Using a current UNI price of $10, strike price of $25, risk free rate of 5%, annualized volatility of 120%, and time to maturity of 1 year, we get a price of $2.30/option but we only need 0.04 because each bond is only convertible into 0.04 UNI. That gives us $0.0920 for our calls.

#### Convert Bond

To get the value of the Convert bond at issuance, we subtract the value of the puts from the value of the zero coupon bond and add the call options.

> Convert Bond = Zero Coupon Bond - Put Options + Call Options
>
> Convert Bond = $0.9523 - $0.0878 + $0.0920 = $0.957

If both options expire worthless, and the bond is repaid, Uniswap will have paid \~5% for their debt. Using a Convert bond issuance, Uniswap was able to reduce their cost of borrowing from \~16%, as determined in the [Simple example](simple.md), to \~5%.

### Value at maturity

#### Zero Coupon Bond

The value of the zero coupon bond at maturity will always be $1 regardless of the UNI token price as shown in the graph below.

![](<../../.gitbook/assets/image (21).png>)

#### Put Options

In contrast, the UNI puts are worthless unless the price of UNI is below $2. They increase to $1 as the price of UNI goes toward $0.

![](<../../.gitbook/assets/image (45).png>)

#### Call Options

The calls are start to gain value once the price of UNI is above $25. There is no cap to how much the calls can be worth.

![](<../../.gitbook/assets/image (28).png>)

#### Convert Bond

Now, to get the value of the Convert bond at maturity, we subtract the value of the puts from the value of the zero coupon bond and add the value of the call options. See below.

![](<../../.gitbook/assets/image (50).png>)

As the value of the UNI token drops below $2, the value of the put increases which decreases the value of the Convert bond. As the value of the token of the UNI increases above $25, the value of the call increases which increases the value of the Convert bond.

## Why should investors buy Convert bonds?

Convert bonds offer investors superior returns compared to other DeFi lending platforms because they combine lending with the sale and purchase of options. In terms of risk profile, Convert bonds sit in between stablecoin farming and longing tokens.&#x20;

![](<../../.gitbook/assets/image (56).png>)

Convert bonds are ideal for yield farmers who have a medium risk portion of their portfolio used to chase higher returns. They are also for investors looking to derisk while still maintaining upside in a project.

## Why should DAOs sell Convert bonds?

Convert bonds allow DAOs to borrow funds without the fear of liquidation by using their project tokens, which make up the majority of their treasuries. Borrowers using collateralized debt positions on other protocols must maintain a particular collateral ratio or risk being liquidated. DAOs are protected from extremely costly liquidations by the inherent put in the Convert bond. To reduce their cost of borrowing, DAOs may find it worthwhile to sell call options on their tokens.

If the protocol is expected to grow, a DAO might be better off delaying the sale of its project tokens, borrowing now, and selling fewer tokens at a higher price later. Or, even better, using increased protocol revenue from the growth funded by debt to pay off said debt and never having to sell governance tokens.
