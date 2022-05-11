# Risks

## Summary&#x20;

Porter Finance is heavily incentivized to mitigate, communicate, and accurately price the risk its users take. At launch, the Porter Finance platform will have two users, borrowers and lenders. Given borrowers do not face interest rate risk or liquidation risk, they effectively bear no platform related risk other than smart contract risk, which will be mitigated through auditing. Therefore, we will focus on the risk lenders are taking when using the platform.

## Active trading markets for the bonds may not develop&#x20;

The bonds are newly issued with no established trading markets. We cannot assure you trading markets for the bonds will develop or of the ability of holders of the bonds to sell their bonds or of the prices at which holders may be able to sell their bonds. If no active trading markets develop, you may be unable to resell the bonds at any price or at their fair market value.

## If trading markets do develop, changes in issuer creditworthiness or the financial markets could adversely affect the market prices of the bonds&#x20;

The market prices of the bonds will depend on many factors, including, but not limited to, the following:&#x20;

* Creditworthiness of the issuing DAO
* Time remaining until maturity of the bonds
* Prevailing interest rates being paid by other DAOs
* Results of issuer operations, financial condition and prospects
* Condition of the financial markets.

The condition of the financial markets and prevailing interest rates have fluctuated in the past and are likely to fluctuate in the future, which could have an adverse effect on the market prices of the bonds.

## DAOs may default on their promises to repay bonds issued

This may lead to complete or partial loss of user funds.

### Mitigating default risk

The Porter Finance team takes issuers through a verification process and [underwrites bond issuances](../participants/porter/underwriting-process-overview.md) by thoroughly reviewing the DAO's financials and analyzing the risk of the collateral provided.

## In the case of a default, collateral slippage may occur if lenders liquidate collateral

Collateral slippage can occur when there is not enough buy side liquidity for the amount of collateral a lender receives upon a default. Although a lender may not want to liquidate the collateral, and therefore won’t be subject to this risk, it’s important to mention for those who do not want to take delivery of the collateral asset upon default.

For example, let’s say XYZ DAO issues a bond and puts up some $XYZ tokens as collateral. At maturity, if XYZ DAO defaults, the lenders will receive the $XYZ being used as collateral. If there is $100M of $XYZ collateral, but only $1M of liquidity on the secondary market, it is unlikely there is enough buy-side demand to sell the collateral at the current price. Therefore, the price of $XYZ will be drastically reduced upon the sale of the collateral into that market leading to a loss in value for the lenders.&#x20;

## The use of collateral tokens introduce risk

### Mitigating collateral token risk

Borrowers use collateral tokens to back their issuances. The usage of these collateral tokens introduces risk for users. The following measures are to mitigate the risk faced by users and were taken from the [Tribe Turbo Launch Group proposal](https://tribe.fei.money/t/tribe-turbo-launch-group/3959) created by Brianna Montgomery. She is the head of security at Fei protocol and we trust her judgement on creating safety measures.

* Token contract must be verified on Etherscan.&#x20;
* Token contract has received an audit from a known security auditor&#x20;
* The project should have a publicly visible test environment&#x20;
* Administrative privileges over the protocol should not be owned by an EOA, any multisig must have known members.&#x20;
* If token supply is not fixed, conditions under which supply can increase needs to be made aware of and low risk&#x20;
* No restrictions on transferring or trading such as holding the tokens for a number of blocks before you can transfer them, fees/taxes on transfers etc&#x20;
* Token transfers shouldn’t be pausable or subject to a whitelist&#x20;
* Token ownership should be widely distributed with no address (whale) owning more than 30%&#x20;

## The use of smart contracts introduces risk

### Mitigating smart contract risk

The threat of contract vulnerabilities is taken extremely seriously by the Porter team. Our smart contracts have been audited by two security firms, Zellic and Spearbit. Our audits can be found [here](https://github.com/porter-finance/audits).
