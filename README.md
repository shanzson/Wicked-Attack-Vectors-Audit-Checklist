# Wicked-Attack-Vectors-Audit-Checklist

<p align = center>
<img src= "./images/20230530_113017.png" height="200">
<br>
</p>

1. Can the require checks be bypassed in any way?
2. Are the comments untruthful to you?
3. Can collusion of different roles - such as borrower, lender and liquidator - pull off a heist?
4. Does the contract allow payment in any token like a shitcoin?
5. Is there any way to lock the tokens forever in the contract? Such as by breaking the flow in which the contract functions are supposed to be called.
6. Using safetransferFrom on address(this) to another address is a bad idea, if no approve is used in the contract code. Use it and transfers will fail.
7. Mapping inside a mapping will persist even if you delete the outer mapping. You don't want old and dirty values to be used, do you? 
8. Is the transferFrom being called on an arbitrary address instead of msg.sender? This can mess up things in weird ways. 
9. Are the public functions vulnerable to critical frontrun attacks like [this](https://github.com/sherlock-audit/2023-01-ajna-judging/issues/140)? Hiding in plain sight? Don't let non-owners steal assets of the actual owners.
10. Is the math for rewarding tokens depending on a variable that can be exploited by users? Lookout for proportionality to measure impact!
11. Can the owner frontrun the sh*t out of users like [this](https://consensys.net/diligence/audits/2021/06/growthdefi-wheat/#frontrunning-attacks-by-the-owner)?
12. Are the parameters of functions used in a convoluted way? Like the money is being sent to the seller instead of the buyer?
13. Are you missing any edge cases, by being too edgy?
14. Are the modifiers too [weak](https://twitter.com/BlockSecTeam/status/1692533280971936059?t=pZijRKlnlcFfo9fdEk8dSQ&s=19) to keep off hacker zombies? Are there any if statements or require statements in it, which they can eat off through, to get to you?
15. Are the terms like buyer and seller in docs, been flipped during coding? E.g. The buyer himself can perform actions of seller which in fact should have only been performed by the seller.
16. Is the contract relying on require statements that contain strict equality comparisons with **balanceOf(address(this))** ? So that the attacker can wreck it all by sending just 1 tiny token?
17. Are the indices of array assignments so messed up that they feel like dark magic?
18. Are the decimals of token not scaled to the [same](https://dacian.me/precision-loss-errors#heading-no-precision-scaling) units while calculation? Hope that you don't scale it [excessively](https://dacian.me/precision-loss-errors#heading-excessive-precision-scaling) so as to take your eye balls out! Also watch out for [hardcoded](https://dacian.me/precision-loss-errors#heading-mismatched-precision-scaling) eye balls! 
19. Can the attacker Inflate your Vault by frontrunning the victim and greedily giving zero share to him and running with all the bazookas like [this](https://blog.openzeppelin.com/a-novel-defense-against-erc4626-inflation-attacks)?
20. Does the protocol allow borrowing and lending in the same block? If yes, then Congrats! You are vulnerable to a Flash Loan Attack. Disallow depositing and borrowing in the same block.
21. Does the rescueToken() function rescue tokens which are meant for users(like the unvested tokens in the contract) in Money Heist style? 
22. 
