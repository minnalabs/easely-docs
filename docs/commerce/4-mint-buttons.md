---
sidebar_position: 4
---

# Mint Button Overview

## **Mint Buttons, Payments, Transactions**

Once a listing has been created, the next and final step is connecting that listing to your own native website. Easely does not provide digital storefronts because we encourage creators to create beautiful experiences for their communities. And because there are a suite of tools that exist today that make it really, really easy to make beautiful websites. 

There are two ways of connecting your Easely listing to your website: 

1. Create a button: Create and customize a generic button on Easely that you can drop right into your site. This is generally available for any website builder that allows you to embed HTML code
2. Connect a button: Connect an Easely listing to your pre-designed button and/or input field on your site for a fully native experience. This is only available on Webflow or React/web-dev site

Below we provide detailed instructions and examples for connecting Easely to the primary no-code website builders:

### **Webflow**

Webflow is a no-code website builder that is our personal favorite and works best with Easely. Webflow lets you set custom component IDs which lets you as the creator connect Easely’s Web3 functionalities native to the components you create in Webflow. A beautiful example can be found [here](http://secondselfnft.com). Webflow requires a [basic plan](https://webflow.com/pricing) at the minimum to insert custom code but you can get started with a trial for free. 

**Webflow - Create a Button:**

1. Choose a template or start with a blank page
2. In the top left there is a “+” button that lets you add Elements. Click it
3. Scroll to the bottom and select the “Embed” component
4. Add the component onto your page where your mint button will be
5. Paste in the “Create a Button —> embed code” from Easely into the empty box
6. Publish the page, preview it, and you’ll see your mint button that will automatically connect to your listing and work with Metamask on your site! 
    
<iframe width="900" height="506" src="https://www.youtube.com/embed/40Mf8_O-_44" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

**Webflow - Connect a Button:**

1. Requirements: you must have a “Button” component and/or an “Input” component to connect a listing to your pre-existing components 
2. Label the “Button” and “Input” component IDs in Webflow by selecting the component and navigating to the top right settings (gear icon) and name the IDs to your preference. If you have multiple listings on one page, **be sure that all “Input” and “Button” IDs are unique** 
3. In the top left there is a “+” button that lets you add Elements. Click it
4. Scroll to the bottom and select the “Embed” component
5. Add the component anywhere on your page (you can drop it at the bottom so it doesn’t get in the way or add it to your `<head>` tag if you are more experienced with Webflow)
6. Paste in the “Connect a Button —> embed code” from Easely into the empty box
7. In the code there’s a line (or two for a variable quantity listing)

```jsx
buttonId: "<BUTTON_ID>",
amountId: "<AMOUNT_ID>",
```

Re-label the <BUTTON_ID> and/or <AMOUNT_ID> to the IDs you set in your Webflow components. For example: 

```jsx
buttonId: "button",
amountId: "amount",
```

1. Publish the page, preview it, and you’ll see your pre-existing “Input” and “Button” components should not have changed visually. But, input a quantity and press your designated button and Metamask will prompt with the respective listing you connected! As you can imagine, you can get pretty creative in designing your input fields and buttons so they look and feel native to your experience ([e.g. SecondSelf](http://secondselfnft.com)).
    
<iframe width="900" height="506" src="https://www.youtube.com/embed/tc3Myh057PQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

### **Wix**

Wix is a no-code website builder that is a bit more user-friendly than Webflow but not as powerful. Wix lets you embed custom code on their free plan but you will need to use their paid plan to connect your own domain. You can find an example [here](https://www.vanalpertnft.com/). **It is important to note that a few of Easely’s features are not compatible with Wix today: primarily “Connect a Button” and minting via mobile.**

**Wix - Create a Button:**

1. Choose a template or start with a blank page 
2. In the top left there is a “+” button that lets you add various components. Click it
3. Find and select “Embed Code”. To the right under Popular Embeds, select “Embed HTML”. A gray box with a frowny-page-face will appear 
4. Double click the gray box and an empty box will appear labeled “Add your code here” will appear. Paste in the “Create a Button —> embed code” from Easely
5. On Wix you’ll be able to see the preview of your mint button immediately. You’ll also be able to move it around exactly where you want it on your site
6. Publish the page, preview it, and click your mint button which will automatically connect to your listing and work with Metamask on your site! 
    
<iframe width="900" height="506" src="https://www.youtube.com/embed/7Q0HV-JCSpA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

### **Shopify**

Shopify is a no-code website builder most often used for e-commerce. At the time, there is no easy way to embed or connect a button with code in a no-code manner. Easely is working on a native app but until then, please direct any Shopify inquiries to studio@easely.io and we will personally help you with an integration. A beautiful, native Shopify integration for a brand with Easely can be viewed [here](https://saysh.com/pages/nft). 

### **Squarespace**

Squarespace is a no-code website builder that offers aesthetic templates but is on the more rigid side of things. You can find a Squarespace example [here](https://streetartnft.xyz/). You can trial a website for a few weeks before having to pay though you will need to use their paid plan to connect your own domain and once the trial period ends.

Squarespace - Create a Button:

1. Choose a template or start with a blank page 
2. Squarespace components are called “blocks”. You can add a block with each “+” button that you see next to existing blocks. Click a “+” where you want your mint button to be added
3. Find and select `</> Code`. A modal will appear with a text box (likely with a `hello world` line). Delete everything so the code box is empty 
4. Paste in the “Create a Button —> embed code” from Easely
5. On Squarespace, it will say “script disabled” in your config mode. Publish the page and you will see the button live
6. Publish the page, preview it, and click your mint button which will automatically connect to your listing and work with Metamask on your site! 
    
<iframe width="900" height="506" src="https://www.youtube.com/embed/m2vEhOVi0Kg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>    

### **Other**

There are plenty of other website builders. As long as you can embed HTML code in your website, it is likely that Easely’s embed buttons will work. If you have any questions with a website builder or website that you are creating, please contact studio@easely.io and we will attend to your shortly!