---
sidebar_position: 1
---

# Lazy Minting

### Overview

The most prevalent form of selling NFTs today is `lazy minting`. To understand this, we must review two concepts: 
* `minting` is the act of officially creating the NFT on the blockchain. An NFT not on the blockchain is not technically an NFT yet - it is just a file with text properties.
* `gas fees` are incurred in every transaction on the Ethereum network paid to the miners. `gas fees` are non-trivial and developers solve for keeping them as low as possible.

The natural workflow is to `mint` the NFT such that it exists on the blockchain then `sell (aka transfer)` the NFT to the buyer. But, this flow incurrs **two gas fees**: one to `mint` and one to `sell`. In order to save on `gas fees`, developers have combined the `mint` and `sell` functions into one function: the `lazy mint`. Instead of the creator minting and then transferring the NFT, the buyer directly `lazy mints` the NFT and there is no transfer necessary, eliminating half the gas fees for the creator. 

This is the recommended approach for Easely creators. Though Easely creators can mint each NFT first then sell them, the `gas fees` stack up quickly. Easely provides a suite of tools to help creators facilitate `lazy minting` and optimize selling their NFTs.