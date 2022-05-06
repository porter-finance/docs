# How does borrowing work?

Borrowing is facilitated through the creation of a [bond](../../protocol/bonds/) and its sale through an [offering](../../protocol/offerings/).

{% hint style="info" %}
If your DAO is interested in becoming a borrower, fill out this [early access form](https://forms.gle/fEqeM5URwRs8K8Fr7) and we will get back to you shortly.
{% endhint %}

## Example

Let's say Uniswap issues 1,000,000 convertible bonds maturing in 12 months and backs each with 0.5 UNI as collateral with each bond being convertible into 0.04 UNI.

### Offering

Uniswap decides to sell the bonds via an auction with a minimum price of $0.943, knowing that they are happy to borrow at or below 6% interest (\[1 - $0.943] / $0.943 = 6%). The more demand, the higher the bonds will sell for which lowers the interest rate Uniswap pays. During the auction, there was sufficient demand and the clearing price ended up being $0.95. Therefore, Uniswap raised $950,000 (1,000,000 bonds \* $0.95/bond) and will owe $1,000,000 in 12 months, which translates to an effective interest rate of 5.3% ($0.05/$0.95).

![](<../../.gitbook/assets/image (23).png>)

### Repayment

For every bond that is repaid, Uniswap is able to withdraw the collateral/bond which is 0.5 UNI.

#### **Full repayment**&#x20;

If Uniswap fully repays the $1,000,000 before the 12 months have passed, they will be able to withdraw all their collateral.

#### Partial repayment

If Uniswap defaults on their promise and only repays $500,000 (failing to repay the remaining $500,000 by the maturity date) the bondholders will be able to redeem their bonds for $0.5 and 0.25 UNI.

#### No repayment

If Uniswap defaults on their promise and does not repay the bonds by maturity, the bondholders will get the full amount of collateral, 0.5 UNI/bond.

#### Repaying convertible bonds

If UNI appreciates in value and bondholders elect to convert their bonds into the convertible UNI tokens, UNI will owe $1 less for every bond converted. Also, for every bond repaid, Uniswap will be able to withdraw the collateral/bond **until there are only convertible tokens left.** Convertible tokens cannot be withdrawn until maturity to ensure the bondholders have the ability to convert their bonds.
