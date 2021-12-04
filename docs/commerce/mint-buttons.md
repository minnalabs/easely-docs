---
sidebar_position: 3
---

# Mint Button Overview

### Mint Button Studio

Once listings are created and signatures are signed and generated, the respective NFTs can be lazy minted with the signature. From here, Easely provides the ability to create embeddable `mint buttons` that creators can drop right into their own websites. `mint buttons` facilitates payment from the buyer to the creator and the NFT from the creator to the buyer directly via their wallets. The buttons can be configured using the Easely Button Studio and font size, width, text and button parameters can be customized for each collection.

Easely then provides the javascript code that creators can copy and paste into their own html/JS-based website. `mint buttons` can also be dropped into any no-code website builder like WordPress, Wix, Squarespace, Shopify, or Webflow. The button will link the respective listing and NFT and directly facilitate a transaction native to your website. Once pressed, the buyer will be prompted to pay the `price` in ETH and if the transaction is accepted, the buyer will `lazy mint` the NFT directly and the `price` will go to the creator less any rev share and Easely's 5% primary sale fees. 

There are a few states that the button will automatically change to depending on the scenario:

| Button Text         | Cause                                                        | Upon Click                       |
| -----------------   | ------------------------------------------------------------ | -------------------------------- |
| Install Wallet      | User does not have MetaMask/web3 in their browser            | Redirect to download MetaMask    |
| Connect Wallet      | User has MetaMask/web3 in their browser but is not logged in | Prompts user to login to wallet  |
| Insufficient Funds  | User does not have enough ETH in their wallet to mint        | Unavailable                      |
| Mint (customizable) | User connected to MetaMask and has sufficient ETH to mint    | MetaMask `lazy mint` transaction | 
| Sold                | NFT has been minted and is no longer available               | Redirect to etherscan of tx hash |
