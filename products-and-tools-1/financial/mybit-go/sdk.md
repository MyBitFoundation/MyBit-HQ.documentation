# SDK

The MyBit Software Development Kit \(SDK\) is a suite of smart contracts, JavaScript classes, and user interface \(UI\) libraries that streamline the process of building decentralised financial applications on top of the [MyBit Network protocol ](https://developer.mybit.io/portal/mybit-ecosystem/mybit-network)without needing in depth blockchain knowledge.

**What is a Decentralised Financial Application \(Financial dApp\)?**

In short, a Financial dApp refers to any application that can transfer, manage, fund, or control the representation of digital assets through Ethereum smart contracts. These digital assets are represented in the form of trade-able tokens, which are able to receive and distribute payments directly to token holders.

**Why is it valuable?**

The MyBit SDK empowers developers to build great Financial DApps in an inclusive, diverse, and global digital asset wealth ecosystem while abstracting away complicated protocol operations such as asset creation and revenue redistribution.

**Components**

The following software components make up the MyBit SDK. Each component has its own GitHub repository and documentation.

[UI Kit](https://developer.mybit.io/ui)

* A series of predefined tools and pre-coded frontend components that allow anyone to quickly build Financial dapps without having to worry about their design limitations.

[​Network.js](https://developer.mybit.io/web)​

* The main JavaScript-based web client for interacting with the MyBit Network protocol. Network.js is our main JavaScript library that wraps around all MyBit Network contracts through a series of JavaScript classes. By importing Network.js as a package from NPM, one is able to access all MyBit Network contract’s interfaces.

[​Contracts​](https://developer.mybit.io/network)

* These consist of Ethereum Solidity smart contracts that compress the business logic of the MyBit Network. The smart contracts are the open source equivalent of the MyBit Network protocol as they allow the deployment of a local instance of the network that is pre-compiled for natural local development.

[​Chain​](https://developer.mybit.io/chain)

* A pre-compiled local instance of the MyBit Network for natural development.

[​Hello Network](https://developer.mybit.io/hello-network)​

* The equivalent of a “Hello World” application using the MyBit Network.

If a use case for a Financial dApp is identified, JavaScript objects can be used to interact with the blockchain and create a Financial dApp of using the MyBit SDK toolkit.

**Roles and Terminology**

The MyBit Network is a **protocol** that comprises a series of actors that interact with each other. The main actors and their roles are:

* **Operator**: Responsible for producing, delivering, installing, and maintaining assets for Asset Managers. In return, the operator receives a portion of the asset’s revenue.
* **Asset Manager**: Responsible for creating the digital asset and initiating the asset crowdfunding period. The Asset Manager deals with most real-world operations pre and post funding along with the Operator, including asset maintenance. An Asset Manager locks tokens as collateral \(“staking”\) to incentivise appropriate asset management.
* **Investor**: Anyone who owns asset tokens purchased via crowdfunding or exchange.
* **Platform Owner**: Responsible for high-level upgrades and authorisation changes made on the platform.

The SDK contracts contain the basic infrastructure to enable these different roles to work together in the decentralised asset economy. While the MyBit-Go platform uses the SDK, the full potential for these tools in building Financial dApps is not yet realised. Therefore, we are continuing to develop further capabilities such as governance and authenticated anonymity, which will cater to institutions that want to keep sensitive information private.

**Usage**

A common use case that benefits from using the MyBit SDK is to create crowdsales for a shared digital venture. For example, a dApp creator could create a new asset that would directly receive the dApp fee. The creator could then receive funds from the asset crowdsale and the investors would share in the revenue produced from that dApp. The dApp creator would be the Asset Manager in this scenario. Anything that is capable of receiving a payment in Ether or ERC20 tokens can be turned into an asset and distributed.

Another example use case would be for a dApp that creates and manages intellectual property if one wants to crowdfund a creative venture and share the ownership of that creative venture with the investors.

To create an asset on the blockchain:

1. Import the MyBit Network object using npm

* const Network = require\(‘@mybit/network.js’\);

2. Add an Operator and let them accept ETH or ERC20

* addOperator\( account, name, owner \) returns \( bytes32 operatorID\)
* await Network.acceptEther\(id, operatorAddress\);

3. Approve burner

* await Network.approveBurn\(operatorAddress\);

4. Create asset

* var response = await Network.createAsset\(\), with parameters
* assetURI: “ipfs/QmZfSNpHVz/”,
* operatorID: operatorID,
* fundingLength: 2629800,
* amountToRaise: 49557286634011000832 //about $10,000
* assetManagerPercent: 0,
* assetManager: operatorAddress //operator is also broker

This will return the address of the new asset-token. This address can receive payment and the token holders will be able to withdraw this payment according to their token holdings.

For the full list of functionality, see the [Network.js](https://developer.mybit.io/web) docs.

For a more detailed walkthrough, see the [Hello-Network](https://developer.mybit.io/hello-network) documentation.

**Additional Use Cases**

Some additional use cases that fit into the dynamic of the MyBit SDK include, but are not limited to, generating security tokens, intellectual property management, real-estate, token swaps, and IoT investment such as [MyBit-Go](https://go.mybit.io/). The SDK is a work in progress and we are working towards implementing governance and privacy preserving crowdsales using [Enigma](https://enigma.co/).

**Limitations**

Although the MyBit Network provides a Software Development Kit \(SDK\) to interact with its protocol of digital assets and actors over the network, the agreements, contracts, and verifications required to interact with the physical world equivalent of these assets cannot be done through the Network and must be performed individually by the representative individual or business entities involved.

This is just the beginning for the MyBit SDK. It will remain a key focus for the MyBit development team as it continues evolving over the coming months and years.

To learn more about using the MyBit SDK please visit the [MyBit Developer Portal](https://developer.mybit.io/portal/mybit-ecosystem/mybit-network)

