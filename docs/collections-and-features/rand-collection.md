---
sidebar_position: 3
---

# Randomized Collection

### Overview

Randomized collections let you create randomized "packs" from a larger pool of NFTs. This has been popularized by the generative PFP (profile pic) projects like CryptoPunks and collectible packs like NBA Top Shot. The mechanic is most similar to a gacha/loot box mechanic in which the buyer receives a random NFT from the greater pool that is often tiered by different rarities and traits. 

Randomized collections will share the same parameters as Standard Collections in addition to the following:

### Max Tokens per Wallet 

`max tokens per wallet` limits the # of NFTs buyers can buy with each wallet. This parameter is not required but highly encouraged to avoid whales and/or NFT botters from owning a disproportionate amount of the NFT pool. If any party, whale or botter, has too large a % of the NFTs, they will have an outsized ability to move (or crash) the market, especially when they liquidate. Most randomized projects aim to maximize the number of unique holders while still selling out - a tough balance, but crucial to keep in mind. 

A famous example is when many users botted the randomized G'EVOLs collection with no token cap per wallet and an individual owned 1,000+ G'EVOLs NFTs sold at an 8x premium immediately on OpenSea. This set an artificial floor for their market and the floor dropped with the botter making out like a bandit and the actual fans left holding the bag. 

### Max Tokens per Transaction

`max tokens per transaction` limits the # of NFTs buyers can buy per pack/transaction. This is another anti-botting tool making it harder for botters to accumulate large percentages of the NFT supply. 

### Randomization Methods: Reveal Now vs. Reveal Later

Creators have the option to choose whether or not their randomized NFTs are revealed upon purchase or revealed later at a certain date or event (typically when the collection is sold out). There are slight differences to each approach giving creators the flexibility to choose the option that fits in the greater NFT experience they are designing. 

**Reveal Now**

`reveal now` entails that the buyer can immediately see the NFT and its corresponding metadata as soon as they purchase the NFT. In this method, Token IDs are not acquired sequentially - e.g. the first token minted may not be `Token ID 0`. The randomization is actually performed on the blockchain, and as a result, there is a slightly higher gas fee for the end buyer that is minting. 

**Reveal Later**

`reveal later` entails that all buyers receive a placeholder NFT until the creator decides to reveal. The reveal is typically planned around either an event (most often selling out) or date (in situations where the max supply of NFTs have not sold out yet). Token IDs in this case are sequential - e.g. the first token minted will be Token ID 0. This helps to save on gas fees for the end buyer. 

A concern that many creators have is that once a reveal occurs, the IPFS directory with all the metadata is public. And since Token IDs are sequential, people can see the exact metadata of the next token before it is bought (and game for the more rare ones). But, Easely protects creators from this situation - if creators decide to reveal before all tokens are minted out, the randomization will be flipped on-chain meaning Token IDs will not longer be acquired sequentially!

The act of revealing is a blockchain transaction that the creator must execute (with a small gas transaction fee). The creator can only `reveal` once via Easely's contracts so buyers can have full faith that the NFTs they receive post-reveal are faily randomized and can never be changed, a fear often associated with contracts that allow for multiple instances of replacing the base token URIs.

### Creating Randomized NFTs

In a randomized collection, the creator must have all the images and metadata created in advance. Easely also offers a generative art tool for creators that have the individual components but need help putting it all together. Then the creator will do the following:

1. Ensure that metadata is in the correct format and the metadata ties correctly to each image
2. Double check your work - any mistakes will not be reversible on the blockchain
3. Upload images to IPFS and receive an IPFS CID (content identifier)
4. On Easely's platform, upload a metadata.csv file containing the metadata for each NFT and drop in the IPFS CID for the aforementioned directory of images for step 3

Randomized NFTs will have the following:
* `base name` a base name for all NFTs in the park. Creators can decide to append the # or not to the base name. It is important to note that the #s will not correspond with token IDs for `reveal later` collections to ensure true randomization for the buyers
* `base description` a description for all NFTs in the pack denoted on Easely's platform
* `file` as image (.png, .jpg, .gif), movie (.mp4, .mov, .webm), audio (.mp3, .flac, .wav), VR (.glb), and HTML (.html) files
* `properties` as key value pairs (max 100), denoted in the metadata.csv 

#### Metadata.csv format

For creators that don't use Easely's generative art tool, you can still create randomized collections on Easely. All you have to do is ensure that you upload a correct metadata spreadsheet. The metadata spreadsheet should be organized in the following manner: where column 1/A is always the file name and every subsequent column after that is a property (trait). Each row after the first row of headers are the files (NFTs) and their respective traits. **The filename must tie exactly to the file that is uploaded to IPFS and its traits must match the associated image.** If an NFT does not have said property, please leave that cell blank. 

| filename  | property 1 | property 2 | property 3 | property N... |
| --------- | ---------- | ---------- | ---------- | ----------    |
| file 1    | value 1    | value 1    | value 3    |               |
| file 2    |            | value 1    | value 1    |               |
| file N... | value 2    | value 2    | value 2    | value 6       |

When working with thousands of generative NFTs with hundreds of properties, it is imperative that you quadruple check your work. **NFTs, the blockchain, and IPFS are immutable by design and thus very unforgiving**. Changes cannot be made once they are created on the blockchain. If a filename doesn't tie to the filename in IPFS, it won't correctly render an image, ever. If the traits for an NFT are off by 1, you can't re-adjust that once they're minted. We can't stress enough how important it is to get it right the first time on MainNet, which is why heavy testing on TestNet is encouraged! 