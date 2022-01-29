# Porter Document Portal

This Portal links to the key resources on Porter to understand the fundamentals of the Protocol. Please join the discussion on [Porter community Discord server](http://discord.gg/9hJKzXPjHm); our team and members of the community look forward to helping you learn about Porter.&#x20;

## Porter: A Bond Issuance Protocol

### Abstract
Porter allows DAOs and other on-chain entities to obtain financing by selling long-term debt in the form of tokenized bonds. It facilitates debt pricing, issuance, and repayment.

### Introduction
#### The value of credit
The creation of credit is an efficient way to allocate resources in a capitalistic ecosystem. It allows for the transfer of capital from parties who cannot competitively create value to those who can in return for a yield. Value-producing parties that have access to credit have a large advantage over players that do not. If properly deployed, their borrowed capital should translate to a higher level of value production. In a competitive market, players with access to credit will, on average, outperform others and thrive, while those who lack access will struggle to compete.

#### DAOs lack access to credit
Permissionless credit markets predicated on social capital remain nascent. Notable pioneers like TrueFi or Maple Finance, while allowing for permissionless lending, still require contractual agreements on behalf of borrowers.<sup>12</sup> Such constraints help explain why these types of credit lines have not yet been made available to DAOs. DAOs need dynamic, on-chain financing options that provide long-term capital and flexible repayment schedules to fit their timelines and goals. Bonds are flexible, long term debt securities which have satisfied the credit needs of corporations for centuries and will do the same for DAOs.

#### DAOs need credit
The sale of equity-equivalent, governance tokens is the current, dominant strategy for DAOs looking to raise capital. While valuable as a method to initially fund development, selling governance tokens productively becomes increasingly difficult for a DAO as it matures. To start, there is not enough liquidity for large cap DAOs to sell any meaningful number of tokens on the open market without collapsing the price.<sup>3</sup> Moreover, attempts by DAOs to sell tokens privately to raise funds have sparked community backlash by members wanting to avoid centralization.<sup>4</sup> Even if the community allowed for private sales, the maximum supply inherent to most governance token contracts renders selling them unsustainable. Issuing bonds offers a sustainable way for mature DAOs to raise the capital needed for protocol development.

Token buybacks are another potential use of proceeds obtained through bond sales. If a community feels as though its token is undervalued, it can issue a bond with the intention of using the proceeds to purchase the token. This rewards token holders similar to how share buybacks reward equity holders in traditional finance.

#### Investing in bonds
Bonds have a lower risk profile than equity investments as a result of their predetermined return, duration, and seniority within the issuer’s capital structure. Their risk is primarily dependent on the issuer’s ability to repay the amount borrowed plus interest. In contrast, the risk and return from equity depends on the value assigned to the selling organization by the equity market. Currently, the valuations of DAOs are quite speculative, leading to elevated risks and rewards for equity investors. For parties looking to hedge their risk with a productive asset, bonds remain an attractive option.

Investors who purchase debt issued by DAOs benefit from increased accessibility and transparency. Traditionally, investors do not have access to purchase debt securities until they have been touched by many fee-taking middlemen. Decentralized bonds can be sold directly to investors without gatekeepers, leading to better terms for both sides. In addition, the transparency of DAO financials leads to lower risk for bond holders — both DAO cash flows and balance sheets exist on-chain in real-time.

### Bond implementation
Bonds are issued as ERC-20 tokens using a new contract for each issuance event. The bond tokens are part of a multi-contract architecture that uses collateral and repayment contracts to facilitate such functions. The bond tokens can be represented as zero coupon bonds. Each bond has a par value of 1 USD and provides a return through the discount at which it is purchased.

#### Repayment
A bond issuer is responsible for paying borrowed principal plus interest to a repayment contract before maturity. At maturity, bond holders can redeem their bond tokens for their share of principal and interest.

#### Default and delinquency
If a bond issuer does not pay the owed amount by the maturity date, the bond becomes delinquent. Subsequently, Porter alerts the bond holders as well as credit protocols. If the principal and interest is not paid after a reasonable amount of time, the bond is declared to be in default and the aforementioned parties are alerted once again. Once a bond is defaulted on, bond holders will be able to exchange their bond tokens for a prorated share of the collateral provided at issuance from the collateral contract.

#### Mitigating default risk
A default would have a negative impact on the value of a DAO’s governance token. If the issuing party used their governance token as collateral, a large supply of their governance token would be released to the bond holders in the event of a default. The bond holders would likely sell the collateral on the open market to recoup their investment, pushing down the token price. Because bond status is publicly available, front-runners would preempt the trade, knowing that a large supply of tokens are likely to be sold. This would amplify the price impact and be to the further detriment of the bond issuer who defaulted.

A bond issuer’s credit is also at stake. As touched upon in the introduction, the ability to attain credit is essential to survival in a capitalistic ecosystem. Defaulting on debt would render the issuer uncreditworthy, preventing them from obtaining financing in the future and damaging their competitiveness.

#### Convertibility
To compensate investors for the default risk taken, DAOs can elect to make their bonds convertible to the collateral deposited at issuance. Convertibility gives bond holders the option to redeem their bonds for a prorated share of the collateral provided at any time. This provides bond holders a call option on the asset in the collateral contract with the breakeven price being determined by the amount of the collateral and the price of the bond with respect to the collateral asset. The value of convertibility is shown below in Figure 1.

![convertibility chart](assets/convertibility_chart.png)
**Figure 1:** Value of convertible bond. Assumes price of collateral asset is 1 USD at issuance and non-convertible bond is valued at 1 USD.

### Bond offering
A bond offering constitutes the initial pricing, issuance, and sale of bonds. To start a bond offering, bond issuers choose the following parameters, among others.

- Auction period
  - Start and end datetime of the bond offering
- Funding threshold
  - Desired borrow amount
- APR cap
  - Maximum interest rate issuer is willing to pay
- Term length
  - Amount of time until bond matures
- Collateral
  - Amount and type of collateral securing debt
- Convertibility
  - Whether or not the bonds will be redeemable for the collateral provided

Once the parameters are chosen and the required assets are deposited, the debt auction is scheduled.

#### Auction
The debt offering is structured as a batch auction where bidders submit public bids with their desired allocation and interest rate. At the auction clearing, the bond interest rate is calculated. Bids are included in the order of lowest interest rate to highest with a higher bid amount breaking ties. The minimum interest rate required to reach the funding threshold is chosen. As shown in Figure 2, this is where supply and demand intersect. This is the final rate for all participants. Bidders who specified an interest rate lower than or equal to the final clearing interest rate receive bonds at the clearing interest rate. Bidders that specified an interest rate higher than the final clearing interest rate do not receive any bonds and have their funds refunded.

![auction chart](assets/auction_chart.png)
**Figure 2:** Interest rate discovery of batch auction

If the funding threshold is not surpassed, there is no auction settlement and bidders’ funds are returned. 

### Acknowledgments
This paper is heavily indebted to discussions with Max Fiege, Anthony DeMartino, Ben Forman, Dan Elitzer, Sidney Powell, Joey Santoro, Elliot Friedman, Russell Ratcliffe, and Nick Estorga.

### References
1.	TrustToken. <i>Introducing TrueFi, the DeFi Protocol for Uncollateralized Lending.</i> URL: https://blog.trusttoken.com/introducing-truefi-the-defi-protocol-for-uncollateralized-lending-9bfd6594a48
2.	Katya Ternopolska. <i>Guide to Lending on Maple.</i> URL: https://maplefinance.ghost.io/lending/
3.	Hasu. <i>A New Mental Model for Defi Treasuries.</i> URL: https://uncommoncore.co/a-new-mental-model-for-defi-treasuries/
4.	0xMaki. <i>Sushi Phantom Troupe - Strategic Raise.</i> URL: https://forum.sushi.com/t/withdrawn-sushi-phantom-troupe-strategic-raise/4554

### Disclaimer
This paper is for general information purposes only. It does not constitute investment advice or a recommendation or solicitation to buy or sell any investment and should not be used in the evaluation of the merits of making any investment decision. It should not be relied upon for accounting, legal or tax advice or investment recommendations. The opinions reflected herein are subject to change without being updated.
