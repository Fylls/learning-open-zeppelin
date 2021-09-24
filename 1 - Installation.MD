<div align="center">

![openzeppelin-by-logo](https://user-images.githubusercontent.com/55017307/134647314-fd33ae99-a46a-4b89-b9d4-7e9c2fc3dee1.png)

# Installation

</div>

when you want to install dependency with Node it's very easy with NPM .
however for solidity smart contracts we don't have the equivalent of NPM but there are some handy libraries like Open Zeppelin

```bash
npm install @openzeppelin/contracts
```

---

add this line to your solidity smart contract

```solidity
import '@openzeppelin/contracts/:PATH';
```

PATH is referred to the one you see on github

@openzeppelin/contracts = https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/contracts

navigate the file system until you find the contract that you are interested in.

what's important to understand is that on our local file system is not resolving from github but it's resolving from our node module directory where we have installed NPM package of Open Zeppelin

inside node modules then here we have the open Zeppelin directory and inside we have all the folder structure that we saw on GitHub before, but this is installed locally
