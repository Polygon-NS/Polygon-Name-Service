# Polygon Name Service for Polygon zkEVM
This document will help you incorporate .pol into your projects. In the document, available functions are examined by including web3.js and .pol name service in your project.


### Requirements
>If you are not actively using it in your project, you should install web3.js.

**NODE**
```
npm install web3
```

**YARN**
```
yarn add web3
```

**In the Browser**
```javascript
<script src="https://cdn.jsdelivr.net/npm/web3@latest/dist/web3.min.js"></script>
```
or
```javascript
<script src="https://unpkg.com/web3@latest/dist/web3.min.js"></script>
```

### Installation

**NODE**
```
npm i polygonnameservice
```

**In the Browser**
```javascript
<script src="https://www.unpkg.com/polygonnameservice@1.0.0/index.js"></script>
```


### Usage
First, we connect with the libraries.

```javascript
const web3 = new Web3(Web3.givenProvider)
// First create a web3js provider

const polygonNS = new polygonNS(web3)
// You are now ready for .pol
```

## GETS

**Primary Address (Ethereum Address to .pol Name)**

Returns the primary address registered to this address.
```javascript
polygonNS.primaryAddress("ETH_ADDRESS")
.then(function(result){
    console.log(result)
    // Returns the primary address registered to this address.
})
```

**Resolve Address  (.pol Name to Ethereum Address)**

Returns the resolved ethereum address of the .pol name.
```javascript
polygonNS.resolveAddress("name.pol").then(function(result){
    console.log(result)
    // Returns the resolved ethereum address of the .pol name.
})
```

**Address Owners**

Returns the domains owned by an address.
```javascript
polygonNS.addressOwners("ETH_ADDRESS").then(function(resultOwners){
	console.log(resultOwners)
})
```  

**Last registered names**

Returns the last  registered .pol names
```javascript
polygonNS.lastAddresses(20).then(function(result){
    console.log(result)
    //Returns the last 10 registered .pol name
})
```

**Is this domain name taken ?**

Returns whether a domain name has been registered by another user.
```javascript
polygonNS.isTaken("polygon").then(function(resultTaken){
    if (resultTaken>0) {
        //This domain name has been registered.
    }
})
```


**Get Data**

Get domain name information.
```javascript
polygonNS.getData("name","data_name").then(function(result){
    console.log(result)
});
```


**Get Twitter Account**

Get Twitter account from .pol name.
```javascript
polygonNS.getTwitter(name).then(function(account_twitter){
     console.log(account_twitter)
})
```


**Get Instagram Account**

Get Instagram account from .pol name.
```javascript
polygonNS.getInstragram(name).then(function(account_instagram){
     console.log(account_instagram)
})
```

**Get Discord Account**

Get Discord account from .pol name.
```javascript
polygonNS.getDiscord(name).then(function(account_discord){
     console.log(account_discord)
})
```

**Get Telegram Account**

Get Telegram account from .pol name.
```javascript
polygonNS.getTelegram(name).then(function(account_telegram){
     console.log(account_telegram)
})
```

**Get URL**

Get URL from .pol name.
```javascript
polygonNS.getUrl(name).then(function(account_url){
     console.log(account_url)
})
```

**Get Email**

Get Email from .pol name.
```javascript
polygonNS.getEmail(name).then(function(account_email){
     console.log(account_email)
})
```


**Get Description**

Get Description from .pol name.
```javascript
polygonNS.getDescription(name).then(function(account_description){
     console.log(account_description)
})
```

**Get Avatar**

Get Avatar from .pol name.
```javascript
polygonNS.getKeywords(name).then(function(account_keywords){
     console.log(account_keywords)
})
```

## SETS

**Set New Primary Address**

Changes the primary address.
```javascript
polygonNS.setPrimaryAddress("name.pol","OWNER_ETH_ADDRESS").then(function(result){
    if (result['status']) {
     //Successful
     } else {
     //Failed
     }
})
```

**Set New Resolve Address**

Changes the resolve address.
```javascript
 polygonNS.setResolveAddress("name.pol","NEW_RESOLVE_ETH_ADDRESS", "OWNER_ETH_ADDRESS").then(function(result){
        if (result['status']) {
        //Successful
        } else {
        //Failed
        }
 })
```

**Register Domain**

Registers a new .pol address and returns the result.
```javascript
polygonNS.register("name.pol",YOUR_REF_ADDRESS,YOUR_ETH_ADDRESS,"3000000000000000").then(function(result){
    if (result['status']) {
        // Registration Successful
    } else {
        // Registration Failed
    }
})
```


**Set Data**

It allows you to add data for the domain name you have.
```javascript
polygonNS.setData("name","data_type","data_value", "Owner_Eth_Address").then(function(result){
    if (result['status']) {
     //Successful
     //eq: data_name: twitter, data_value: twitter_account
     } else {
     //Failed
     }
})
```
