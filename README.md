# Wicked-Attack-Vectors-Audit-Checklist

<p align = center>
<img src= "./images/20230530_113017.png" height="200">
<br>
</p>
![](https://tenor.com/view/naruto-orochimaru-smirk-gif-7893986)
- Can the require checks be bypassed in any way?
- Are the comments untruthful to you?
- Can collusion of different roles - such as borrower, lender and liquidator - pull off a heist?
- Does the contract allow payment in any token like a shitcoin?
- Is there any way to lock the tokens forever in the contract? Such as by breaking the flow in which the contract functions are supposed to be called.
- safetransferFrom address(this) to another address is a bad idea, if no approve is used in the contract code.
