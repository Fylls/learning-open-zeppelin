# Reetrancy Guard

in 2016 on etherium the DAO smart contract got stolen hundreds of millions of ether.

hackers use a technique called a `re-entrant attack`,if your smart contract developer that's very important
to understand how it works and how can you protect against it

```solidity
pragma solidity ^0.5.0;

import '@openzeppelin/contract/utils/ReentrancyGuard.sol';

interface ReceiverInterface {
  function onReceive() external;
}

contract SecureContract is ReentrancyGuard {
  constructor() ReentrancyGuard() public {}

  function withdraw(uint amount) nonReentrant() external {

    //Check if `msg.sender` balance is enough
    //Send `amount` tokens to `msg.sender`
    ReceiverInterface(msg.sender).onReceive();
    //Decrease its balance
  }
}
```

```solidity
contract Attacker {
  uint count = 0;

  function start() external {
    onReceive();
  }

  function onReceive() external {
    if(count < 9) {
      count += 1;
      MyContract(0x...).withdraw(1 ether);
    }
  }
}

```
