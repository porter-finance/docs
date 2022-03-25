# Simple

## Summary

Simple bonds allow DAOs and other on-chain entities to borrow stablecoins using their project tokens as collateral. At maturity, if the debt is not repaid, lenders can redeem their bonds for the collateral supplied.&#x20;

A Simple bond is most similar to a mortgage on a house. In the case of a default, the lender takes the house. When purchasing Simple bonds, lenders are effectively selling a [put option](../../financial-concepts/convertible-bonds/put-options.md) on the collateral token and purchasing a [zero coupon bond](../../financial-concepts/zero-coupon-bonds/).&#x20;

> Simple Bond = Zero Coupon Bond - Put Options

Therefore, they are exposed to the collateral token's downside past the option strike price but recieve an option premium for taking on this "default" risk. This results in boosted yields for the lender, while supplying a liquidation-free loan to the borrower.

## Why should investors buy Simple bonds?

Simple bonds offer investors superior returns compared to other DeFi lending platforms because they combine lending with the sale of options. In terms of risk profile, Simple bonds are closer to stablecoin farming than holding tokens.&#x20;

![](<../../.gitbook/assets/image (19) (1).png>)

Simple bonds are ideal for yield farmers who have a low/medium risk portion of their portfolio used to chase higher returns.

## Why should DAOs sell Simple bonds?

Simple bonds allow DAOs to borrow funds without the fear of liquidation by using their project tokens, which make up the majority of their treasuries. Borrowers using collateralized debt positions on other protocols must maintain a particular collateral ratio or risk being liquidated. DAOs are protected from extremely costly liquidations by the inherent put in the Simple bond.

If the protocol is expected to grow, a DAO might be better off delaying the sale of its project token, borrowing now, and selling fewer tokens at a higher price later. Or, even better, using increased protocol revenue from the growth funded by debt to pay off said debt and never having to sell governance tokens.

## Example

As of writing, Uniswap has \~$2B of UNI token in their treasury and no stablecoins, so they may want to borrow some stablecoins to diversify their treasury and fund expenses.

Let's say Uniswap issues 1,000,000 Simple bonds maturing in 12 months and backs each with 0.5 UNI as collateral. When selling these bonds, Uniswap is effectively selling a zero coupon bond and buying a put option with a strike price of $2.&#x20;

#### Put options strike price

The put options strike price comes from Uniswap's ability to default on the bond and "sell" the collateral for the value owed at maturity, which is $1. Uniswap having the ability to sell the collateral (0.5 UNI) for $1 means they have a UNI put option with a strike price of $2 ($1/0.5 UNI = $2/UNI strike price).

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

The value of the options is impossible to determine exactly, but we can use [Black Scholes](https://www.investopedia.com/terms/b/blackscholes.asp) to estimate it. Using a current UNI price of $10, strike price of $2, risk free rate of 5%, annualized volatility of 100%, and time to maturity of 1 year, we get a price of $0.08/option but we only need 0.5 because there are 0.5 UNI as collateral per bond. That gives us $0.04 for our puts.

#### Simple bond value at issuance

To get the value of the Simple bond at issuance, we subtract the value of the puts from the value of the zero coupon bond.

> Simple Bond = Zero Coupon Bond - Put Options
>
> Simple Bond = $0.95 - $0.04 = $0.91

So we can estimate the value of these Simple bonds to be $0.91 / bond at issuance.

### Simple bond value at maturity

To determine the value of the Simple bond at maturity, we again subtract the value of the put from the value of the zero coupon bond but this time, we determine the values at maturity. Let's determine the value of both starting with the zero coupon bond.

#### Zero coupon bond value at maturity

The value of the zero coupon bond at maturity will always be $1 regardless of the UNI token price as shown in the graph below.

![](<../../.gitbook/assets/image (38).png>)

This can be confirmed by solving for the zero coupon bond value when time to maturity (n) is 0.

> Zero Coupon Bond = F ÷ (1 + r)^n
>
> Zero Coupon Bond = $1 ÷ (1 + 0.05)^0 = $1

#### Put options value at maturity

Unless the price of UNI is below $2, the UNI puts are worthless at maturity. They increase to $1 as the price of UNI goes toward $0.

![](<../../.gitbook/assets/image (31).png>)

The put option pricing equation at maturity is greatly simplified when calculated at maturity.

> Put Option = MAX(Strike Price - Token Price, $0)

#### Simple bond value at maturity

Now, to get the value of the Simple bond at maturity, we subtract the value of the puts from the value of the zero coupon bond. Remember, we only need 0.5 put options because there are 0.5 UNI as collateral per bond.

> Zero Coupon Bond = $1
>
> Put Option = MAX(Strike Price - Token Price, $0)
>
> Simple Bond = $1 - 0.5 \* MAX(Strike Price - Token Price, $0)

As the price of the UNI token drops below $2, the value of the put increases which decreases the value of the Simple bond, because it is equal to the zero coupon bond minus the put option.

![](<../../.gitbook/assets/image (54).png>)

### Simple bond returns

If held until maturity, the returns of the Simple bond are equal to the value at maturity minus the value at issuance.

> Return = Simple Bond \[t=maturity] - Simple Bond \[t=issuance]

If a lender purchases the bonds at the price calculated above of $0.91 and the options expire worthless, the lender will redeem their bonds for $1 each and make $0.09, which is approximately a 10% return (0.09 / 0.91 ≈ 10%).
