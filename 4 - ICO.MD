# ICO - Initial Coin Offering

when you code ICO smart contracts you have two options you can either call it from scratch or use the Open Zeppelin library.

I recommend the second solution because it's way faster and safer another benefit, for instance they offer you a lot of options to customize your ICOs

:warning: Crowdsales are included in OpenZeppelin Contracts 2.X, they are not in OpenZeppelin Contracts 3.X. :warning:

```bash
npm install @openzeppelin/contracts@2.5.1
```

---

**example:**

```solidity
pragma solidity ^0.5.0;

import '@openzeppelin/contracts/crowdsale/Crowdsale.sol';
import '@openzeppelin/contracts/crowdsale/distribution/PostDeliveryCrowdsale.sol';
import '@openzeppelin/contracts/crowdsale/time/IncreasingPriceCrowdsale.sol';

// ERC20 Interface
import '@openzeppelin/contracts/token/ERC20/IERC20.sol';

contract ICO is Crowdsale, PostDeliveryCrowdsale, IncreasingPriceCrowdsale {

  constructor(
    uint rate,
    address payable wallet,
    IERC20 token
  ) Crowdsale(rate, wallet, token) PostDeliveryCrowdsale() IncreasingPriceCrowdsale(3, 1) public {}
}
```

---

## Constructor

investor are going to send ether to this smart contract and in exchange they're going to receive ERC20 tokens.
all ethers sent are going to be stored in the declared walled.

`rate` price of the token.

`wallet` address of the wallet

`token` pointer to the token of the ICO

---

<div align="center">

`crowdsale/validation`

</div>

---

## Timed Crowdsale

you can set a beginning and end time for your ICO using standard ISO formats

---

## Whitelist Crowdsale

only whitelisted can participate
there are functions to add or remove from whitelist

---

## Pausable Crowdsale

shut down ICO, stop all transactions if there is a problem

---

## Capped Crowdsale

max market-cap that ICO can receive.
if threshold surpassed no other investments can be made

---

## Post Delivery Crowdsale

if you use this option your ERC20 tokens are not transferred right away to the investors,
instead you need to wait for the ICO to be finished and only then investor can call this function

the reason why you would want to do this is because you don't want to mix together the primary market and the secondary markets.

primary market is when you are doing the ICO and secondary market is when you can do trading, so any investor can go to any extent and buy or sell their their token but usually you want to separate these two phases because otherwise if they happen at the same time then you can have some some arbitrage opportunity that can arise between the primary an secondary market and then this is real mess.

so in most cases you probably will want to use this post-delivery cross sell option

---

## Increasing Price Crowdsale

initial price of coin, increases linearly until the end of the ICO

example: `IncreasingPriceCrowdsale(3,1)`

from 3 token for 1 wei to 1 token for 1 wei. (price is increasing)

---
