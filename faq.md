# FAQ

### Do you have a token?

We have not launched a [token](protocol/prtr-token.md). However, when we do, early users and partners will be compensated.

### How is Porter different than OlympusDAO?

Although OlympusDAO uses the term "bond", they are not selling bonds. A bond is a debt security, under which the issuer owes the holders a debt and (depending on the terms of the bond) is obliged to pay them interest (the coupon) and to repay the principal at a later date, termed the maturity date. OlympusDAO's bonding mechanism can be simplified to selling tokens at a discount with a lockup period. From the OlympusDAO's documentation: _\[Bonding] allows Olympus to acquire its own liquidity and other reserve assets such as LUSD by selling OHM at a discount in exchange for these assets._

### How is Porter different than Maple/TrueFi?

Although Maple and TrueFi are also undercollateralized lending platforms, they are different in 3 key ways: sourcing, underwriting, product offering.

**Sourcing**

Maple and TrueFi allow lenders to deposit funds into pools where capital for loans is sourced from. This guarantees liquidity for borrowers on the platform but limits the amount of liquidity available to what is in the pool. Porter uses an auction model to source capital from the whole market. Therefore, a bond issuer on Porter has the ability to access more capital than what is available in a Maple/TrueFi pool.

**Underwriting**

Maple and TrueFi completely offload underwriting and capital allocation to third parties. This increases efficiency but limits the investor's control over their investment. Although Porter also facilitates underwriting through [Sherpas](protocol/sherpas.md), investors decide which on-chain entities' bonds they would like to invest in, giving them more control.

#### **Product offering**

Maple and TrueFi offer non-transferable loans. This is a fundamentally different product offering than bonds. Porter bonds implement the ERC-20 interface, making them tradable instruments. Porter also allows borrowers to issue bonds convertible into a project token, increasing their attractiveness to an investor.&#x20;

### What types of bonds can be issued on Porter?

At launch, Porter will support [zero coupon bonds](intro-to-bonds/zero-coupon-bonds/) with the option of making them [convertible](intro-to-bonds/convertible-bonds/). These instruments best address the needs of market participants at the current state. Porter will allow coupon bonds and other types of debt instruments to be issued in the future.
