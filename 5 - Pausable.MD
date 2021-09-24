# Pausable

once you deploy a smart contract to the mainnet there is no way to update the code so if a hacker finds a security vulnerability you are absolutely defenseless.

One way you have to deal with this is to make some of the function of your smart contract "pausable".

You will temporarily deactivate them and you can do this with the Open Zeppelin library.

---

## Adding new Pausers

pause() can only be called when the smart contract is not paused and if the sender is not the poser address.
The poser address is basically the address that deployed a smart contract (onlyOwner)

`PauserRoles.sol`

```solidity
addPauser(address)
renouncePauser(address)
```

---

## Functions

```solidity
pause()
unpause()
```

---

## Modifiers

```solidity
whenNotPaused()
whenPaused()
```

---

## Integration

```solidity
pragma solidity ^0.5.0;

import "@openzeppelin/contracts/lifecycle/Pausable.sol";

contract MyContract is Pausable {

  constructor() Pausable() public {}

  function foo() whenNotPaused() external {
    //do something
  }

  function bar() whenPaused() external {
    //do something
  }
}

```
