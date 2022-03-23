# Auctions

Auctions allow borrowers to set a minimum price for their bond sales and allow market demand to set the final price. Setting a minimum price also sets a maximum interest rate the borrower is willing to pay.&#x20;

Auctions are implemented as batch auctions where lenders submit public bids with their desired amount and interest rate. Bids are included in the order of lowest interest rate to highest with a higher bid amount breaking ties. At auction end, the minimum interest rate required to reach the funding threshold is determined. This is the final rate for all participants. Lenders who specified an interest rate lower than or equal to the final clearing interest rate receive bonds at the clearing interest rate. Lenders that specified an interest rate higher than the final clearing interest rate do not receive any bonds and have their funds refunded.

![](<../../.gitbook/assets/image (44).png>)

If the funding threshold is not surpassed, there is no auction settlement and lenders’ funds are returned.

{% hint style="info" %}
Auctions are powered by Gnosis Auction. For more details, [read their docs](https://gnosis-auction.eth.link/#/docs#topAnchor).
{% endhint %}
