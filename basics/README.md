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