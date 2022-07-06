---
sidebar_position: 3
---

# General FAQs

### Why are you called Easely? 

Because nothing about the blockchain and NFTs is easy today and we are going to change that, no-coding one feature at a time. Our platform also supports your creations like an easel does an artist's paintigs :)  

### Who are you? 

We're a team of ex-Web2 builders (AirBnB, Carta, Pinterest, Stripe, Uber, etc.) that have been NFT fans since we graduated college early and were building ERC-721 apps in 2018. When we saw the world beginning to adopt NFTs but the development infrastructure had not changed, we knew millions of non-technical creators were being gatekept from building in Web3. We immediately quit our Web2 jobs to build this bridge and provide creators access to the beautiful technology that is NFTs. 

### What can I even do with an NFT? 

Plenty! Many NFTs have value inherently as art or a collectible. But beyond that, you can show it off in your [Gallery](https://gallery.so/), re-sell them on [OpenSea](https://opensea.io/) or [Rarible](https://rarible.com/), access community features and roadmaps, and so much more. 

### Why is it so cheap to deploy my own smart contract / NFT collection? 

It is true that personal NFT contracts can cost anywhere between 0.5 - 1.0+ ETH. But, we are using a technique called "proxy contracts" (that many others are adopting today as well) to allow creators to create their own NFT contracts without paying a fortune. A proxy contract simply creates a copy of Easely's original contract, but with the parameters that you as a creator selected. 

### Why is gas so expensive? 

This is simply a function of the Ethereum network - all transactions cost gas, and gas will fluctuate depending on how congested the network is. Easely has taken steps to optimize its contracts to be as gas-friendly for its creators and their communities. 

Your next question may be: well why do people create NFTs on Ethereum? For better or worse, Ethereum (and ERC-721) is the gold standard for NFTs. There are plenty of NFTs created on other, no/low-gas blockchains (e.g. Polygon, Solana, Flow) that **Easely will incorporate in the near future.**

### Why does it take so long for my contract to deploy? Why does everything take so long? 

The contract specifically takes a few minutes to confirm because we want to ensure that your deployment went through on the Ethereum network. Every now and then a block of transactions can get reversed (aka uncled blocks) - in the off-chance that your contract is on one of those blocks, we want to make sure that our platform correctly reflects that. Thus it is industry standard to wait a few more blocks to ensure your deployment wasn't reversed.

Ethereum is "slower" because it maximizes decentralization and security within the network. 