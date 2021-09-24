<div align="center">

![openzeppelin-by-logo](https://user-images.githubusercontent.com/55017307/134647314-fd33ae99-a46a-4b89-b9d4-7e9c2fc3dee1.png)

</div>

<br>

I have a question for you, when you write a smart contract do you write all the code from scratch?

the problem with this approach is that it can be a bit slow and you can also lead to a couple of security vulnerabilities.

there is another way to write your smart contract way faster and more securely and this way is by using the smart contract library Open Zeppelin

Open Zeppelin is a collection of solidity smart contracts that implement functionality that are commonly used in smart contract projects, for example we find implementation for the major token standards like ERC20 ERC721, etc.

there is a company that is called Zeppelin solutions that sells services for auditing smart contract and is also the main contributor to the Open Zeppelin project

the big advantage of having this library open source is that we have many eyes that can scrutinize the code and quickly find any security vulnerability and fix them.

and I think that is great about Open Zeppelin is that regularly the code is audited by another company that is linked to Zeppelin Solutions, so that they can have an independent opinion. Thanks to this you can be very confident that the code of Open Zeppelin is very secure.

written in solidity but it is actually distributed as an NPM package.

```bash
npm install @openzeppelin/contracts
```

the typical way of using a smart contract from Open Zeppelin is to first import the source code from the node module directory in your smart contract and after you're gonna create another smart contract that inherit from a smart contract in open Zeppelin
