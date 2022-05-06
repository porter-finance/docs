# Simple bonds

## Summary

Simple bonds allow DAOs and other on-chain entities to borrow stablecoins using tokens they have in their treasury as collateral. Simple bonds give lenders a sustainable, fixed yield. Simple bonds are [zero coupon bonds](../../financial-concepts/zero-coupon-bonds/), which are sold at a discount to the face value and do not pay coupons, hence why they are called "zero coupon" bonds.

> Simple Bond = Zero Coupon Bond

## Why should investors buy simple bonds?

Simple bonds offer investors an alternative to yield farming by providing sustainable, fixed returns.

![](<../../.gitbook/assets/image (5).png>)

### Competitive yields

Both yield farming and simple bonds offer competitive yields. Historically, yield farming has provided 10-20% variable returns but those have compressed recently due to decreases in farming token prices. We expect lenders to earn 10-15% return on simple bonds issued through Porter.

### Sustainable returns

Yield farming programs are inherently unsustainable. The majority of yield earned through yield farming comes from the project providing their native token as a subsidy. Usually, around 10-30% of the APR comes from interest paid by borrowers while 70-90% comes from token subsidies.&#x20;

![](<../../.gitbook/assets/image (60).png>)

In contrast, the majority of yield earned through lending to DAOs comes from DAOs paying interest. This is because DAOs have revenue generating businesses which allow them to pay higher interest rates. This makes yield earned on DAO bonds much more sustainable because subsidies eventually stop, forcing the yield farming to look for greener pastures.

![](<../../.gitbook/assets/image (54).png>)

### Fixed rates

While yield farming returns are wildly variable depending on day to day borrow demand, bonds issued by DAOs provide fixed rates. This guarantees investors a predictable return.

### Low smart contract risk

To generate competitive returns, yield farmers are typically forced to deposit funds in complex protocols on non-mainnet Ethereum blockchains. This exposes investors to high smart contract risk as well as bridging risk. As illustrated by the [recent Wormhole hack](https://cointelegraph.com/news/wormhole-hack-illustrates-danger-of-defi-cross-chain-bridges), bridging funds adds a significant amount of risk to investor strategies.

Porter smart contracts are on Ethereum mainnet, which eliminates any bridging risk investors are exposed to. In addition, Porter contracts have gone through [two audits](https://github.com/porter-finance/audits) and are [relatively simple](https://github.com/porter-finance/v1-core/tree/main/contracts). This reduced complexity results in decreased risk for investors.

### No credit risk

Lending to DAOs does bear a risk that is not shared by yield farming. Credit risk. To mitigate this risk, Porter confirms creditworthiness through verification and underwriting. In addition, DAOs heavily overcollateralize their bond issuances to mitigate incentive to default. DAOs also use an on-chain signature service to promise they will repay the amount borrowed plus interest.

## Why should DAOs sell simple bonds?

Simple bonds allow DAOs to borrow funds without the fear of liquidation by using their project tokens, which make up the majority of their treasuries. Borrowers using collateralized debt positions on other protocols must maintain a particular collateral ratio or risk being liquidated.

![](<../../.gitbook/assets/image (16).png>)

If the protocol is expected to grow, a DAO might be better off delaying the sale of its project tokens, borrowing now, and selling fewer tokens at a higher price later. Or, even better, using increased protocol revenue from the growth funded by debt to pay off said debt and never having to sell governance tokens.
