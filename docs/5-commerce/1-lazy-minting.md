---
sidebar_position: 1
---

# Lazy Minting

### Overview

On Easely, your NFTs will be `lazy minted`. To understand this, we will review to concepts: 

- `minting` is the act of officially creating the NFT on the blockchain. The images you upload onto Easely are not technically NFTs until they get minted. They’re just images with metadata!
- `gas fees` are incurred in every transaction on the Ethereum network paid to the miners. `gas fees` are non-trivial and developers constantly innovate to keep them as low as possible.

The straight-forward workflow is to `mint` the NFT then `sell` the NFT to the buyer - this is how it works on [Foundation](http://foundation.app). But, this flow incurs **two gas fees**: one to `mint` and one to `sell`. But most importantly, it requires you to **pay a fee (mint) when a sale may never occur.** 

In order to save on `gas fees`, developers have combined the `mint` and `sell` functions into one function: the `lazy mint`. Instead of the creator minting and then transferring the NFT, the buyer directly `lazy mints` the NFT and there is no transfer necessary, eliminating half the gas fees for the creator, and eliminating any upfront costs prior to the NFT being bought.

