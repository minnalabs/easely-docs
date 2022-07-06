---
sidebar_position: 3
---

# Randomized Collection Listings

Randomized Collection listings offer more functionality than a standard collection listing because you are working with multiple NFTs. The biggest differences are that you can create multiple listings and listings can encompass multiple NFTs. There are two important features to understand:
1. General vs. Restricted Listings
2. Fixed vs. Variable Quantity Listings

### General vs. Restricted Listings

#### General Listing

A general listing can be accessed by any wallet address at any time once the embed is connected to your website. This is used for the "general sale" portion of many mint experiences

#### Restricted Listing

One of the most popular features associated with high volume, randomized NFT drops is a restricted sale (aka white list, allowed list, pre-sale, etc). The creators offer a pre-determined list of people (wallet addresses) the exclusive ability to mint with different prices/quantities than the general population. With the popularity of [premint.xyz](https://www.premint.xyz/), you can easily export the winners in a csv and load it into Easely when creating a restricted listing. Otherwise, creators can manually collect wallet addresses and upload them following [this format](files/white-list-format.csv).

In your `white-list-csv`, you can add a `quantity` column that denotes varying quantities of NFTs each wallet can mint in the restricted listing (you'll see this in the exmaple csv above). This is useful if you have raffle winners or collaborators that get more free mints than the typical whitelisted individual. If you set varying quantities in your spreadsheet, it will override the `quantity` parameter you set in the restricted listing on Easely's platform; otherwise, the quantity set on Easely's platform will be applied to all addresses in the whitelisted spreadsheet of addresses. 

Each restricted listing can only have **one price** meaning every whitelisted address will be able to mint at the price set in the respective listing. If you would like to permission different groups to mint at different prices, you can create multiple restricted listings. Each listing must be connected to a button on your site: some creators choose to swap the listing code out during each phase, create multiple buttons, etc. 

Please note that Easely does not read `.eth` addresses today - ensure that your spreadsheet wallet addresses are all in the `0x...` format. You can find the `0x...` address linked to a `.eth` address via Etherscan.

#### Fixed Quantity Listing

A fixed quantity means that the listing (and mint button) will always mint for a pre-set amount of tokens. The buyer will not be able to input how many NFTs they want to mint. Each button/listing will correspond to a fixed # of NFTs. This is used to create multiple buttons that can provide bulk discounts to minters (e.g. mint 1 listing costs 0.05 ETH per NFT but the mint 5 listing costs 0.04 ETH per NFT)

Below is an example of embedding a fixed quantity listing into Webflow. 

<iframe width="900" height="506" src="https://www.youtube.com/embed/40Mf8_O-_44" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

#### Variable Quantity Listing

A variable quantity allows the minter to select their desired quantity via an input on the creator's website. The min quantity will be 1 token and the max quantity will be the “max tokens per mint” parameter (or unlimited if that parameter is not set).

Below is an example of embedding a variable quantity listing into Webflow. 

<iframe width="900" height="506" src="https://www.youtube.com/embed/tc3Myh057PQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

#### Concluding Thoughts

The way Easely sets up its listings provide plenty of flexibility for creators. They can create restricted listings after mint has started, add anyone that was missed on accident, create new listings to decrease price - the experience should be akin to having your own dev on the team without having to code!