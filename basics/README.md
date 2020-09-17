# Basics of Ethereum

## History
* Halloween 2008 - "White paper" came out about a system to allow peer rot peer payments with no central authority [Original White paper link](https://bitcoin.org/bitcoin.pdf)
* Jan 2009 - First bitcoin network online
* December 2013 - Vitalik Buterin publishes "White paper" to create block chain for far more than just bitcoin, he created the smart contract concept. [white paper link](http://web.archive.org/web/20131228111141/http://vbuterin.com/ethereum.html)
* July 30th 2015 - Ethereum system goes online

## What is a blockchain?
Think of a blockchain as a database that stores all transactions in full

## What is Ethereum
* Network of nodes (computers) each of these nodes have the ethereum software running and connect to the ethereum network
* Anyone can run a node if you have a computer. All you need is the software and anyone can be a part of it
* Each node has a complete copy of the blockchain
  
## How can I connect to ethereum network?
* web3.js library (allows you do anything with code)
* metamask (chrome extension)
* Mist Browser

## Install Metamask
1. Get the chrome browser [metamask extension](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn)
2. Create an account with a password

You will see a dropdown with different ethereum networks
* Main Ethereum Network: production network where actual transactions are happening
* number different test networks for testing and playing around with ethereum:
  * Ropsten
  * Kovan
  * Rinkeby 
  * Goerli
* Localhost 8545 - used to test against a locally running ethereum network
* Custome RPC lets you connect to a remote network


## Ethereum Account Details
* Account Address: unique identifier for your account like email or username
* Public Key: 
* Private Key

All above stored as hexadecimals

Unique thing about creating an account with ethereum is that that same account works for any Ethereum network that you connect to.


## What is an ethereum transaction?
A Transaction is when one account attempts to send money to another account. A Transaction is created when two accounts exchanged money. In web3.js you create a transaction object that has a few different properites:
* Nonce: How many times the sender has sent a transaction
* to: Address of account this money is going to
* value: amount of ether to send to the target address
* gasPrice: amount of ether the sending is willing to pay per unit gas to get this transaction processed
* startGas/gasLimit: Units of gas that this transaction can consume
* v, r, s
  * cryptographic pieces of data that can be used to generate the senders account address. Generated from the sender's private key. 
  * If you have the private key, you can generate v,r,s. But if you only have v,r,s you cannot generate the private key. The existence of v,r,s is how you know it is a legitimate transaction.
* Why does transaction take so long?
  * When transaction obj gets sent to the ethereum network it gets sent to one node on the network, not the entire network
  * When the transaction(s) (could be more than one transaction at one time) is received by the node it creates a block (list of transactions). It then runs some validation logic on the new block. This validation logic is what takes a long time on the transaction. This validation logic is called mining


## Mining
Mining involves computing a hash of the data, and nonce that outputs a hash. That hash is then converted to a base 10 number and is checked if it is less than some number, if it isn't then it increments the nonce value. The ethereum network tries to keep mining at around 15 seconds. So it will adjust the base 10 converted hash number up or down depending on how much computing power there is on the ethereum network. Why? Because people are logging on/off of the network so the computing power is always in flux. 

## Smart Contract
An account on ethereum network that is controlled by code. Not a human user.
What does this contract account consist of?
* Balance: Amaount of ether this account owns
* Storage: Data storage for this contract
* Code: Raw machine code for this contract

Contract account cannot be accessed across different ethereum networks. Unlike our external account created through metamask that can be accessed the same on any network. 


## Solidity Programming Language
`.sol` files, strongly typed language.

We write `.sol` files, which are then compiled by the solidity compiler and it outputs two different things. 
1. Byte code ready for deployment
2. ABI (Application Binary Interface)
   1. This ABI is used for javascript code to interface with the byte code. Because the javascript cannot talk to the ABI