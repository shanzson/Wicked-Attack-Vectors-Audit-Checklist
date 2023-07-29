# Wicked-Attack-Vectors-Audit-Checklist

<p align = center>
<img src= "./images/20230530_113017.png" height="200">
<br>
</p>

- Can the require checks be bypassed in any way?
- Are the comments untruthful to you?
- Can collusion of different roles - such as borrower, lender and liquidator - pull off a heist?
- Does the contract allow payment in any token like a shitcoin?
- Is there any way to lock the tokens forever in the contract? Such as by breaking the flow in which the contract functions are supposed to be called.
- Using safetransferFrom on address(this) to another address is a bad idea, if no approve is used in the contract code. Use it and transfers will fail.
- Mapping inside a mapping will persist even if you delete the outer mapping. You don't want old and dirty values to be used, do you? 
- Is the transferFrom being called on an arbitrary address instead of msg.sender? This can mess up things in weird ways. 
- Are the public functions vulnerable to critical frontrun attacks like [this](https://github.com/sherlock-audit/2023-01-ajna-judging/issues/140)? Hiding in plain sight? Don't let non-owners steal assets of the actual owners.
- Is the math for rewarding tokens depending on a variable that can be exploited by users? Lookout for proportionality to measure impact!
- Can the owner frontrun the sh*t out of users like [this](https://consensys.net/diligence/audits/2021/06/growthdefi-wheat/#frontrunning-attacks-by-the-owner)?
- Are the parameters of functions used in a convoluted way? Like the money is being sent to the seller instead of the buyer?
