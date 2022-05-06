# How does lending work?

Lending is facilitated through the purchasing of [bonds](../../protocol/bonds/). Bonds can be purchased through participation in [offerings](../../protocol/offerings/).

{% hint style="info" %}
If you're interested in becoming a lender, fill out this [lending form](https://forms.gle/LaDvgXJMZi788LmM6) and we will get back to you shortly.
{% endhint %}

## Example

Let's assume Uniswap issues 1,000,000 Convert bonds maturing in 12 months and backs each with 0.5 UNI as collateral with each bond being convertible into 0.04 UNI. The value of this bond at issuance was estimated to be $0.97.

### Offering

Uniswap decides to sell their convertible bonds via an auction with a minimum price of $0.943. After doing some due-dilligence, a lender decides the value to them at $0.96, so they submit a bid with $100,000 volume at a price of $0.96 / bond. The auction closes and the clearing price ended up being $0.95. Because the bid price was greater than the close price, the lender's order gets fulfilled at the lower $0.95/bond closing price instead of the $0.96 offered. Therefore, the lender purchases 105,263 bonds ($100,000 / $0.95) for $100,000 which can be redeemed at maturity for $105,263.

![](<../../.gitbook/assets/image (19).png>)

### Redemption

#### **Full repayment**&#x20;

If Uniswap fully repays the bonds before the 12 months have passed, the lender will be able to withdraw $1/bond.

#### Partial repayment

If Uniswap defaults on their promise and pays half the principal and interest but fails to repay the remaining half by the maturity date, the lender will be able to redeem their bonds for $0.5 and 0.25 UNI (half the amount owed and half the collateral).

#### No repayment

If Uniswap defaults on their promise and does not repay the bonds by maturity, the lender will get the full amount of collateral, 0.5 UNI/bond.

#### Converting bonds

If UNI appreciates in value to $50, the lender may elect to convert their bonds into the 0.04 convertible UNI tokens which would be valued at $2/bond for a \~111% return (\[$2 - $0.95] / $0.95).
