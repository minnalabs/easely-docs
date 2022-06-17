---
sidebar_position: 2
---

# Standard Collection Listings

A `listing` defines the sales parameters for an NFT (individual or via a randomized collection). Typical parameters such as price and quantity can be set in a listing. In the future, different transaction types like auctions will be added as well. 

### Standard Collection Listings

Creators can create a max **1** listing for each NFT in the collection. A standard listing defines the sale parameters for an NFT and has the following fields:
* `name` name for the listing stored for organizational purposes
* `listing type` two types: single fixed price and auction. Auction listings are a work in progress
* `price` in ETH 

Once these parameters are defined, creators finalize a listing by signing a web3 transaction (MetaMask pop-up that asks you to sign a message requiring no fees). 