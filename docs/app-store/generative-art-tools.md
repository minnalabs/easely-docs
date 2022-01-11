---
sidebar_position: 1
---

# Generative Art Tools

Easely also offers tools to help creators create their generative NFTs (aka PFP and avatar collections). Generative NFTs layer various traits (backgrounds, bodies, hats, accessories, etc.) on top of each other to randomly create unique NFTs. This has been popularized by CryptoPunks, Bored Ape Yacht Club, Pudgy Penguins, and many, many more collections. 

Although the value of these PFP projects started out purely as collector value, these NFTs have evolved into so much more: 
* Elgibility to receive additional incentives via airdrops and staking
* Membership to communities and DAOs 
* Access to real-world events as seen by the craze of NFT NYC, Art Basel Miami, and more 
* Gaming
* Metaverse 

And that is just the beginning - the beauty of NFTs is how interoperable they are, once you create your own collection and smart contract, you can integrate your NFT collection effortlessly with marketplaces, metaverses, social medias, and more. 

### Step 1: Creating the Layers 

Before even thinking about the blockchain, artists need to create the individual "layers" and "traits" that will be used to randomly generate the image. Typically, "layers" are the buckets of "traits" that are layered one on top of another. Not a lot of unique traits are needed to create an insanely high number of combinations - 5 layers with 6 traits each will create 15,000+ unique images. 

Some rules to keep in mind when you think about designing your layers:
* Traits are layered in sequential order (e.g. background --> body --> accessory)
* All traits should be the same dimension 
* All traits should have transparent background (outside of a background trait)
* Useful for later: take note of what "filters" need to be added (e.g. the Aliens in CryptoPunks don't have hair because, well, aliens don't have hair)
* Useful for later: take note of what "rarities" should be attributed to each trait and what the end rarity distribution for the entire collection should be

First, you want to determine what the layers are, how many there are, and the ordering in which they are layered. Then, you can begin creating the traits within each layer. It is important to create the traits in a manner in which they all "work" with each other (e.g. all the different "body" traits work with the various "accessory" traits). Filters can be added to guarantee or exclude certain combinations but can get complex if you add too many. 

Traits should be organized in a self-explanatory manner on your computer. Each "layer" should be a "folder" (and named properly) with the following traits as PNG files in each "layer folder". For example, all my "Background" PNG images should be in my "Background" folder. 

### Step 2: Prepping the Work Environment

In order to Easely's tools, it is required to download some basic dev apps. Don't worry - there will be no coding required - the actual "dev" work should be as trivial as copy and pasting code and filling out basic config details. 

#### Download VS Code

VS Code is a standard dev environment that you will need to use Easely's generative art program. You can download and install it [here](https://code.visualstudio.com/download)

#### Download Python3, pip, and required packages

Python is a coding language and is typically built into operating systems today, but the latest version is recommended to reduce issues. Python3 can be downlaoded and installed [here](https://www.python.org/downloads/https://www.python.org/downloads/)

pip is the Python installer program that is used to install packages that will be used for this tool. Open Terminal (Mac) or Command Line (Windows) and type the following:

```python
pip install Pillow pandas progressbar2
```

1. Pillow is an image processing library that layers your traits
2. Pandas is a data analysis library that will generate, manipulate, and store the metadata
3. Progress bar will provide a visualization on the progress of each job within the tool 

#### Download and Opening Easely's Code Repo

The last step is downloading Easely's [code repo](https://github.com/minnalabs/generative-art) that includes a set of programs for you to generate, revise, and finalize your art pieces. Unzip the file and move the folder inside (titled `easely-generative-art-tools`) to your preferred working location on your computer. 

Now, open VS Code that you installed earlier and go to 

```
file --> open folder --> select the `easely-generative-art-tools` folder --> open
```

VS Code will now open Easely's generative art programs and your work environment is successfully prepped! Here's a summary of the programs below and how they will be used throughout the rest of this guide:

#### Programs
1. `config.py`: File that defines all the parameters for your art generation: # of images, layer ordering, trait rarity probabilities, filters, and more. 
2. `generate.py`: Program that generates the # of images (NFTs) depending on your `config.py` parameters
3. `submit.py`: Program that generates the final images (NFTs) after revisions based on a final `metadata.csv` files 
4. `upload.py`: Program that uploads your final images (NFTs) to IPFS, the gold standard of storing NFTs. Your NFT collection on the blockchain will then link to this IPFS directory that will exist in perpetuity

#### Other
1. `README.md`: Instructions on how to operate the various programs 
2. `assets` folder: Folder where you will add your layers and traits to 
3. `output` folder: Folder where your generated images will be 
4. `final` folder: Folder that contains the final images / NFTs, metadata, and IPFS directory for your collection

### Step 3: Configurating and Generating the Collection

#### Configuration Parameters

```jsx
CONFIG = [
    {
        'id': 1,
        'name': 'Background',
        'directory': 'background',
        'required': True,
        'rarity_weights': None,
    },
    {
        'id': 2,
        'name': 'Body',
        'directory': 'body',
        'required': False,
        'rarity_weights': 'None',
    },
    {
        'id': 3,
        'name': 'Eyes',
        'directory': 'eyes',
        'required': True,
        'rarity_weights': [50,30,15,5], 
    },
    {
        'id': 4,
        'name': 'Body Accessory',
        'directory': 'body-acc',
        'required': False,
        'rarity_weights': [70,20,8,2], 
    }
```

1. `id`: This is the order in which layers are placed on top of each other sequentially, starting with 1 and incrementing by 1. The program will choose a random trait from `id = 1` and layer on a trait from `id = 2` and so on and so forth
2. `directory`: This is the folder name for the layer (and where the traits for that layer are located). This must match the exact folder name or the program will not run successfully 
3. `name`: This is the official metadata name for the layer: what gets stored on the blockchain and what gets populated in secondary marketplaces or rarity tools that read the blockchain. It is important that you have the exact syntax (capitalization, symbols, etc.) when generating the NFTs 
4. `required`: Whether or not a trait from this category is required for the NFT. Can take on either `True` or `False`
5. `rarity_weights`: One of the most important characteristics for large PFP collections is rarity distribution which can be configured here. There are two options: `None` and `Probability List`
    * `None`: This option results in equal weighting for all traits within that layer 
    * `Proability List`: This option lets you define the probabilities for each trait within each layer. The `Probability List` is defined within hard brackets **in which each number is the percentage that that trait shows up**. Let's use the following example reflecting the above config:
        
        ```jsx
        Layer/Name = `Eyes`,
        4 Traits: [`black`, `brown`, `red`, `violet`],
        Probability List: [50,30,15,5]
        ```
        This results in roughly a 50% chance for black eyes, 30% chance for brown, 15% for red, and 5% for violet. There are a few crucial things to note regarding Probability Lists:
    
    1. The Probability List applies to the traits within a `layer` folder in alphabetical order, as you can see in the above example. Be sure to sort your folder by ascending name as you define the probabilities 
    2. If the `required` parameter is false, this adds an additional trait that requires a probability: the probability that this trait **DOES NOT** show up at all. The probability for a `none` in this case will **always be the first number in the list**. The list will always have `number of traits + 1` probabilities. For the `Body Accessory` example above, there are only three traits, with the probability of **NO BODY ACCESSORY** being 70%. 
    3. The numbers within the probability list must add up to 100 (or 100%) and the number of probabilities will always equal the number of traits for `required: True` and number of traits + 1 for `required: False`


Once all parameters are set, let's move on to actual image generation!

#### Generation 

Once the CONFIGS are set (save all your files) open up the Terminal via VS Code `(menu --> Terminal --> New Terminal)`. A console should pop up underneath the code that you can type in. To run the generative art tool, simply type in 

```jsx
python3 generate.py
``` 

and hit enter. It will ask you to name this `draft` (that you can type in the Terminal) and will begin generating your NFTs at random based on your settings. Once the `generate.py` program is complete, go into the `output` folder and you will find the collection you just created. In that folder, you will find an `images` folder and a `metadata.csv` file that has the corresponding traits for each image.  

We highly encourage you to play around with the possible configurations and have a strong understanding of every parameter. There is no harm in generating small sample sizes to better understand rarity weights, layer ordering, and most importantly, what the layers look like on top of each other. **This is an incredibly iterative process and many edits to configs and layers and traits will be made throughout so do not feel like 1 generation is all that's required**.

### Step 4: Curating and Finalizing the Collection

No generation is perfect on the first try (unless you are creating on-chain generative art - which Easely will support soon!) and will require varying parameters and curating the final pieces **so the end collection really feels like magic**. Many creators recommend creating 20% more than the intended final collection size (e.g. 12,000 if the collection is 10,000) because you realize that a lot of combinations don't make sense or aren't up to par right off the bat. There are two standard methods when it comes to parsing the collection down and curating the final collection. 

#### Method 1: Delete Rows in the `metadata.csv` File (recommended)

The first method of curation is simply deleting the rows in the `metadata.csv` file for the NFTs that you would like to discard. This is recommended because any spreadsheet program will easily let you filter, manipulate, and delete rows (e.g. Excel, Google Sheets). If you are creating multiple `drafts` and want to add in the different metadata that you like, you can do so in a spreadsheet as well. 

Once you have the **final metadata.csv file**, drag that file to the `metadata` folder in the `final` folder. Then run the following program in terminal:

```jsx
python3 submit-metadata.py
```

This will re-generate all the images based solely on the final `metadata.csv` file. This step ensures that the images tie perfectly to the metadata file - a common mistake is for an NFT and its metadata to not match due to the difficulty in accurately manipulating thousands of NFTs. 

#### Method 2: Delete Images in the `output` Folder 

If you are not as savvy with spreadsheets / data analysis or working with smaller sample sets, you can also delete the images rather than deleting rows of metadata within the spreadsheet. For example if you had 12 images and you only wanted to keep 10, delete the 2 images - **you do not need to change the metadta file**. Then run the following:

```jsx
python3 submit-images.py
```

This program will ask you which `draft` folder you are working out of. `submit-images.py` will clean up the metadata file to only include the metadata of the images that you had kept. The final metadata and resulting images can be found in the `final` folder. Please note that it is imperative that you do not manually change any of the file names for images that were outputted. The program assumes that all the images will tie to the metadata by its final name. 

### Step 5: Uploading to IPFS and Turning the Collection into NFTs

The final step is to upload your collection to [IPFS](htpps://ipfs.io), the decentralizing file storing protocol and the industry standard for storing NFTs today. An easy way to store your files can be done via [Pinata](https://pinata.cloud) and it is recommended that you pin the NFTs yourself (so noone but you can ever possibly unpin them!). **If you have trouble pinning or prefer not to pin the images to your final generative art collection, feel free to contact the Easely team in our Discord and we will help you out!** Otherwise, see below instructions on pinning and uploading your images to IPFS. 

#### Create a Pinata Account

Create a [Pinata](https://pinata.cloud) account and choose the plan appropriate for your collection (pinata offers free hosting up to 1GB of data). 

#### Create and Store your API Keys

Login to your Pinata account, click on your profile in the upper right corner, and select `API Keys` (regular version is fine, V2 is not needed). Create a new API key and store the `API Key`, `API Secret`, and `JWT` in your secure password manager. 

#### Config and Run upload.py

Now pop open `upload.py` and paste in your `API Key`, `API Secret`, and `JWT` in rows 6, 7, and 8. Now run `upload.py` using the following in terminal: 

```jsx
python3 upload.py
```

You will be prompted to name the collection that you would like to submit and the program will begin uploading to IPFS. **Please note that pinning files to IPFS takes a bit of computing power and cannot be interrupted in between. As a benchmark, a computer with 16GB RAM can handle ~10GB upload. If you have issues with collection sizes being too large, contact the Easely team on Discord**. 

### Step 6: Save the IPFS CID and Create your Collection on Easely

Once the images have been saved to IPFS successfully, a new folder in `final` will be created with a single file that contains the IPFS CID (Content Identifier) for your NFTs! Now go ahead and head over to [Easely MainNet](https://app.easely.io) or [Easely TestNet](https://app.rinkeby.easely.io) and create a `Randomized Collection`. You now have the final images to your generative NFT collection via the IPFS CID that you will drop in once prompted in the NFT creation process!