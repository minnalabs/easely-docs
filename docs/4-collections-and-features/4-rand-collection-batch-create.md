---
sidebar_position: 3
---

# Batch Create Randomized NFTs

Randomized NFT collections inherently have 2+ NFTs in the collection if not hundreds or thousands of them. Because it is tedious and error-prone to manually create each one, Easely allows for the batch creation of NFTs in a simple and understandable manner. NFTs consist of two components: 

* the file (often a media file, particularly an image) 
* the metadata (text or numerical properties associated with the file). 

Easely will allow you to batch upload these both separately. If you use our [generative art engine](https://docs.easely.io/app-store/generative-art-tools), you will have all the files needed for this process. 

### Batch Uploading Files / Images

Easely follows the gold standard of NFTs by using IPFS (interplanetary File System), a peer-to-peer file storage protocol storing NFTs in a more decentralized manner. Everything stored in IPFS is given a CID (content identifier) that is used for NFTs to access the correct content.

#### "Not Your Pins, Not Your NFTs"

In crypto, there's a common saying: "Not your keys, not your crypto" meaning if you don't have access to your wallet, there's a risk one day you won't be able to access the crypto (also a snarky dig at centralized exchanges). IPFS works similarly: even though the protocol is decentralized, there's no guarantee that your content stays up ("pinned") forever **unless you are the one pinning it**. Thus we recommended that creators themselves pin their own content. 

#### Using Piñata with Easely

Pinning your images to IPFS is done easily via [Piñata](https://www.pinata.cloud/). It's as easy as uploading your folder with your images for your Randomized Collection, just like any file storage service. Keep in mind that once a folder directory is uploaded, it cannot be edited. The files themselves cannot be changes. New files can't be added, individual files can't be removed. **This is why IPFS works so perfectly with NFTs - NFT owners can be confident that the underlying files will not change in the future.**

If you've made a mistake or need to re-upload a directory, delete/unpin the existing one (to save storage) and re-upload the new folder. It's recommended to test on smaller sample sizes to understand the process. **The last step is to copy and save down the CID of your directory which you will then bring to Easely's platform.**

### Batch Uploading Metadata

NFT metadata, which most often includes the properties associated with each NFT (e.g. what layers and traits comprise the NFT) is important as they act as filters and labels that secondary marketplaces and other dapps use to organize and sort through your collection. The final format for metadata are often in `.JSON` files which aren't the easiest to work with for non-technical individuals. **As a result, Easely takes metadata in the form of a `.csv` file/spreadsheet.** `.csv` files can be easily edited in Excel, Numbers, or even online spreadsheet platforms like Google Sheets. If your metadata is already in a `.JSON` file, Easely is building a converter and can manually convert your files into the right format (just ping the team on Discord). 

The metadata should always be formatted like the following CryptoPunks example:

| filename  | Background | Punk       | Top        | Mouth      |
| --------- | ---------- | ---------- | ---------- | ---------- |
| 144.png   | blue       | zombie     | clown_hair | vape       |
| 145.png   | blue       | ape        | crazy_hair |            |
| 146.png   | blue       | male4      | half shaved|            |

It is crucial that the top left cell/header is labeled `filename`. It is also crucial that the **file names tie exactly to the image file names that you uploaded to Piñata/IPFS.** The file names are the indices that match the metadata (properties) with the correct image. So the image for `144.png` should match the traits for the `144.png` row in the CSV. We demonstrate that in the video below and the seamless process to upload folders into IPFS. 

<iframe width="900" height="506" src="https://www.youtube.com/embed/iRRcR2E9Pjo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

If you used our Generative Art Program, we will output the `metadata.csv` file for you in the correct format.


### Batch Creating on Easely

Once you have the IPFS CID for your images and the corresponding metadata.csv spreadsheet, drop those into Easely when you create your batch create NFTs. You will also be able to set basic and advanced parameters. 

<iframe width="900" height="506" src="https://www.youtube.com/embed/Or-lWV7AhIw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Basic Parameters
* Name: the name of your NFTs that will be used for all NFTs in the collection. Easely will also append the Token ID to the name. E.g. the name "Azuki" will show up as "Azuki #0" or "Azuki #9999" depending on the Token ID.
* Description: a description for your NFTs that will be the same for all NFTs in the collection. Optional.

Advanced Parameters
* Set Starting Token ID: Token IDs typically start with **Token ID #0** in the world of NFTs. That said, we can offset this to start at **Token ID #1** or whatever starting ID you prefer.
* Disable Easely Randomization: Easely randomizes the NFTs after the creator uploads their spreadsheet to 

Make sure to double check that your `metadata.csv` is formatted in the exact way you want your traits to appear on marketplaces and that **all images tie to their metadata correctly**. Happy building!