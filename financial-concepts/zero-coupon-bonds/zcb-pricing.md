# ZCB pricing

### Pricing formula

The price of a zero-coupon bond can be calculated as:

> Price = F ÷ (1 + r)^n

where:

* F = Face value of the bond
* r = required rate of interest
* n = number of years until maturity

If an investor wishes to make a 10% return on a bond, with 1 USDC par value, that is due to mature in 1 year, they will be willing to pay the following:

> 1 USDC / (1 + 0.1)^1 = 0.91 USDC

If the borrower accepts this offer, the bond will be sold to the investor at 0.91 USDC / 1 USDC = 91% of the face value. Upon maturity, the investor gains 1 USDC - 0.91 USDC = 0.09 USDC, which translates to 10% interest per year. The greater the length of time until the bond matures, the less the investor pays for it, and vice versa.

The following graph, courtesy of the [FiatDAO whitepaper](https://fiatdao.com/\_next/static/ee94825d84674d155ad1.pdf), shows the pricing of zero coupon bonds for different interest rates ranging from 0 (dark blue line color) to 10% (dark red line color). As expected, the fair price converges to the ZCB’s face value when the remaining time-to-maturity approaches 0.

![](<../../.gitbook/assets/image (42).png>)

### Duration and convexity

Bonds will rise or fall in value as interest rates change. The sensitivity to changes in the interest rate environment is called **duration**. The use of the term duration in this context can be confusing to new bond investors because it does not refer to the length of time the bond has before maturity. Instead, duration describes how much a bond’s price will rise or fall with a change in interest rates.

The rate of change of a bond’s sensitivity to interest rates (duration) is called **convexity**. These factors are difficult to calculate, and the analysis required is usually done by professionals.
