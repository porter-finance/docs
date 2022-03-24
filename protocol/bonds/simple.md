# Simple

## Summary

Simple bonds allow DAOs and other on-chain entities to borrow stablecoins using their project tokens as collateral. At maturity, if the debt is not repaid, the bondholders can redeem their bonds for the collateral supplied.&#x20;

A Simple bond is most similar to a mortgage on a house. In the case of a default, the lender takes the house. When purchasing Simple bonds, lenders are effectively selling a put option on the collateral token and purchasing a zero coupon bond. Therefore, they are exposed to the collateral token's downside past the option strike price but recieve an option premium for taking on this "default" risk. This results in boosted yields for the lender, while supplying a liquidation-free loan to the borrower.

> Simple Bond = Zero Coupon Bond - Put Options

## Example

As of writing, Uniswap has \~$2B of UNI token in their treasury and no stablecoins, so they may want to borrow some stablecoins to diversify their treasury and fund expenses.

Let's say Uniswap issues 1,000,000 Simple bonds maturing in 12 months and backs each with 0.5 UNI as collateral. When selling these bonds, Uniswap is effectively selling a zero coupon bond and buying a put option with a strike price of $2.&#x20;

#### Put Options Strike Price

The put options strike price comes from Uniswap's ability to default on the bond and "sell" the collateral for the value owed at maturity, which is $1. Uniswap having the ability to sell the collateral (0.5 UNI) for $1 means they have a UNI put option with a strike price of $2 ($1/0.5 UNI = $2/UNI strike price).&#x20;

To determine the value of the Simple bond, we have to subtract the price of the put from the zero coupon bond. Note that only 0.5 puts are being sold because there are only 0.5 UNI being used as collateral.

### Value at issuance

#### Zero Coupon Bond

The value of the zero coupon bond at issuance is determined by the required rate of interest and the time until maturity. The equation below is further explained in [ZCB pricing](../../financial-concepts/zero-coupon-bonds/zcb-pricing.md). We will assume a required rate of interest of 5%.&#x20;

> Zero Coupon Bond = F ÷ (1 + r)^n
>
> Zero Coupon Bond = $1 ÷ (1 + 0.05)^1 = $0.952

The value of the zero coupon bond at issuance is $0.952 regardless of the UNI token price.

#### Put Options

The values of the options are impossible to determine exactly, but we can use Black Scholes to estimate them. Using a current UNI price of $10, strike price of $2, risk free rate of 5%, annualized volatility of 120%, and time to maturity of 1 year, we get a price of $0.1756/option but we only need 0.5 because there is 0.5 UNI as collateral per bond. That gives us $0.0878 for our puts.

#### Simple Bond

To get the value of the Simple bond at issuance, we subtract the value of the puts from the value of the zero coupon bond.

> Simple Bond = Zero Coupon Bond - Put Options
>
> Simple Bond = $0.9523 - $0.0878 = $0.865

Assuming the option expires worthless and the bond is repaid, the lender will get a \~16% return.

### Value at maturity

#### Zero Coupon Bond

The value of the zero coupon bond at maturity will always be $1 regardless of the UNI token price as shown in the graph below.

![](<../../.gitbook/assets/image (38).png>)

#### Put Options

In contrast, the UNI puts are worthless unless the price of UNI is below $2. They increase to $1 as the price of UNI goes toward $0.

![](<../../.gitbook/assets/image (31).png>)

#### Simple Bond

Now, to get the value of the Simple bond at maturity, we subtract the value of the puts from the value of the zero coupon bond. See below.

![](<../../.gitbook/assets/image (54).png>)

As the value of the UNI token drops below $2, the value of the put increases which decreases the value of the Simple bond, because it is equal to the zero coupon bond minus the put option.

## Why should investors buy Simple bonds?

Simple bonds offer investors superior returns compared to other DeFi lending platforms because they combine lending with the sale of options. In terms of risk profile, Simple bonds are closer to stablecoin farming than holding tokens.&#x20;

![](<../../.gitbook/assets/image (19) (1).png>)

Simple bonds are ideal for yield farmers who have a low/medium risk portion of their portfolio used to chase higher returns.

## Why should DAOs sell Simple bonds?

Simple bonds allow DAOs to borrow funds without the fear of liquidation by using their project tokens, which make up the majority of their treasuries. Borrowers using collateralized debt positions on other protocols must maintain a particular collateral ratio or risk being liquidated. DAOs are protected from extremely costly liquidations by the inherent put in the Simple bond.

If the protocol is expected to grow, a DAO might be better off delaying the sale of its project token, borrowing now, and selling fewer tokens at a higher price later. Or, even better, using increased protocol revenue from the growth funded by debt to pay off said debt and never having to sell governance tokens.
