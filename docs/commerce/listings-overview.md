---
sidebar_position: 2
---

# Listings Overview

### Standard Collection Listings

Creators can create a max **1** listing for each NFT in the collection. A standard listing defines the sale parameters for an NFT and has the following fields:
* `name` off-chain name for the listing for organizational purposes
* `listing type` two types: single fixed price and auction. Auction listings are a work in progress
* `price` in ETH 

Once these parameters are defined, creators finalize a listing by signing a web3 transaction (MetaMask pop-up that asks you to sign a message requiring no fees). 

### Randomized Collection Listings

Creators can create **multiple** listings for a pack of NFTs in a randomized collection. An example use case of multiple listings is when creators want to offer bulk discounts or conduct a restricted sale and a general sale in parallel. The listings may vary in price, quantity, and access but will all follow the same randomized mint logic from the pool of NFTs in a randomized collection. A randomized listing has the following fields:
* `name` off-chain name for the listing for organizational purposes
* `listing type` has two types: single fixed price and auction. Auction listings are a work in progress
* `price` in ETH per NFT
* `quantity`is the # of NFTs that an eligible wallet can **and must** mint (e.g. 2 at a time or 4 at a time)
* `access` has two types: general and restricted. Restricted sales can create a listing only eligible for a set of wallet addresses provided. The list of addresses that are in the AllowList is not publicly disclosed via Easely - creators are encouraged to be transparent in how they conduct restricted sales (what addresses are eligible and how the selection was decided) for best practices. 

In standard general access listings, creators will finalize the listing by signing a web3 transaction. For restricted listings, Easely will sign on the creator's behalf because it is not practical for a creator to manually sign thousands of addresses individually. 

### Restricted Listings

One of the most popular features associated with high volume, randomized NFT drops is a variation of a restricted sale (aka white list, allowed list, pre-sale, etc). The goal remains the same: to offer a pre-determined list of people (wallet addresses) the exclusive ability to mint via a separate avenue than the general population. How this list is determined depends on what the creator is looking to accomplish. Here are a few examples:
* **Prevent gas wars by restricting the full drop:** Gas wars often occur when there's an outsized amount of buying demand during the first few seconds or minutes of the drop. Creators have worked to avoid this by conducting a raffle before the drop and **only allowing those that won the raffle to mint by adding them to a allowed list**. Mekaverse famously did this - where the whole drop was "restricted" and the raffle for which addresses won were conducted well in advance of the drop. 
* **The "revese airdrop"** Most successful NFT drops are not singular drops - they are experiences. And what of the most common roadmap features is additional NFTs over time. These are often executed (and expected) as an airdrop - where NFTs are sent directly to holders' wallets. But, this is often extremely pricey for creators due to gas and thus many have opted for a "reverse airdrop" - creating additional NFTs that holders have access to mint for free. This can be executed by simply creating a restricted sale for only existing holders and thus the holders bear the cost of gas individually.  
* **Reward early adopters / super fans:** Another common use case for restricted sales is to permission early community members by allowing them to buy early (time gas better) or buy for cheaper (or even free sometimes). 

The concept of restricted sales has certainly been controversial in the NFT world. At the end of the day, it is another tool for creators to incorporate into their NFT experience - and they should have the option and flexibility to do so. All a creator needs to do on Easely is create a listing with `restricted` access type and **upload a .csv file with a list of addresses that should be permissioned.** All wallet addresses would then have access to the price / quantity combination associated with the listing (e.g. 0 ETH, 1 QTY). 

| Wallet Address | 
| -------------- | 
| 0x...          |
| 0x...          | 
| 0x...          |
