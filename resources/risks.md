# Risks

## Purpose&#x20;

Porter Finance is heavily incentivized to mitigate, communicate, and accurately price the risk its users take. At launch, the Porter Finance platform will have two users, borrowers and lenders. Given borrowers do not face interest rate risk or liquidation risk, they effectively bear no platform related risk other than smart contract risk, which will be mitigated through auditing. Therefore, we will focus on the risk lenders are taking when using the platform and how we believe it should be priced.&#x20;

## Default risk

Due to the nature of the protocol, all risks taken on by lenders materialize in the case of a default. The possibility of default is increased if the value of the collateral drops below the amount owed by the borrower.

### Pricing default risk&#x20;

As shown in our documentation, Porter Finance bonds are the summation of zero-coupon bonds and options. Assuming a borrower defaults 100% of the time the collateral value is below the owed amount at maturity, the risk of default can be priced using [Black Scholes](https://www.investopedia.com/terms/b/blackscholes.asp).

#### Options pricing&#x20;

We use the Black Scholes option pricing model which needs historical token volatility, expiration date, and token strike price. We can determine each of these values from the bond attributes:&#x20;

* The option historical token volatility comes from the historical volatility of the bond collateral token.&#x20;
* The option expiration date comes from the bond’s maturity date.&#x20;
* The option strike price comes from the number of collateral tokens provided for puts and the convertible tokens provided for calls. [See here](https://docs.porter.finance/portal/protocol/bonds/convert#put-option-strike-price) for an explanation.

Therefore, we can price these risks using Black Scholes.

### Mitigating default risk

To mitigate default risk at launch, we are limiting usage of the platform in the following ways:

* Collateral tokens must have a historical volatility less than 150% over the last 90 days
* Bonds cannot be issued with tenors over 12 months
* Bonds must be at least 250% collateralized



## Collateral slippage risk

Collateral slippage can occur when there is not enough buy side liquidity for the amount of collateral a lender receives upon a default. Although a lender may not want to liquidate the collateral, and therefore won’t be subject to this risk, it’s important to mention for those who do not want to take delivery of the collateral asset.

For example, let’s say XYZ DAO issues a bond and puts up some $XYZ tokens as collateral. At maturity, if XYZ DAO defaults, the lenders will receive the $XYZ being used as collateral. If there is $100M of $XYZ collateral, but only $1M of liquidity on the secondary market, it is unlikely there is enough buy-side demand to sell the collateral at the current price. Therefore, the price of $XYZ will be drastically reduced upon the sale of the collateral into that market leading to a loss in value for the lenders.&#x20;

### Pricing collateral slippage risk

As collateral slippage does not apply to all users and is difficult to determine (due to future market conditions being unknown), we will not attempt to price collateral slippage. However we want users to be aware of it and know that we are taking actions to mitigate it.&#x20;

### Mitigating collateral slippage risk

In order to mitigate collateral slippage, we are limiting the users of the platform to DAOs who use a collateral token with:&#x20;

* An average $1M+ 24h volume over the last 30 days&#x20;
* An average $50M+ market cap over the last 30 days

These metrics increase the likelihood of the secondary market being able to absorb collateral being liquidated by lenders. It should also be taken into consideration that the secondary market demand may be much larger than the available volume occurring over 24 hours due to OTC deals that are not reflected in known volume data distributors. The likelihood of secondary market demand increases when there are existing well-capitalized investors behind the borrower.&#x20;

## Collateral token risk&#x20;

### Mitigating collateral token risk

Borrowers use collateral tokens to back their issuances. The usage of these collateral tokens introduces risk for users. The following measures are to mitigate the risk faced by users and were taken from the [Tribe Turbo Launch Group proposal](https://tribe.fei.money/t/tribe-turbo-launch-group/3959) created by Brianna Montgomery. She is the head of security at Fei protocol and an absolute chad. We trust her judgement on creating safety measures.

* Token contract must be verified on Etherscan.&#x20;
* Token contract has received an audit from a known security auditor&#x20;
* The project should have a publicly visible test environment&#x20;
* Administrative privileges over the protocol should not be owned by an EOA, any multisig must have known members.&#x20;
* If token supply is not fixed, conditions under which supply can increase needs to be made aware of and low risk&#x20;
* No restrictions on transferring or trading such as holding the tokens for a number of blocks before you can transfer them, fees/taxes on transfers etc&#x20;
* Token transfers shouldn’t be pausable or subject to a whitelist&#x20;
* Token ownership should be widely distributed with no address (whale) owning more than 30%&#x20;

## Smart Contract Risk&#x20;

### Mitigating smart contract risk

The threat of contract vulnerabilities is taken extremely seriously by the Porter team. The platform is being audited by two security firms, Zellic and Spearbit. When finished, our audits will be found here.
