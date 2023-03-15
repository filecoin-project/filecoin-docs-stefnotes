---
title: "Ethers.js"
description: "Ethers.js is a JavaScript library that provides a simple and consistent interface for interacting with the Filecoin blockchain. It is designed to be easy to use, and provides a number of powerful features for building decentralized applications (dApps)."
lead: "[Ethers.js](https://docs.ethers.org/v5/) is a JavaScript library that provides a simple and consistent interface for interacting with the Filecoin blockchain. It is designed to be easy to use, and provides a number of powerful features for building decentralized applications (dApps)."
draft: false
images: []
type: docs
menu:
  smart-contracts:
    parent: "smart-contracts-developing-contracts"
    identifier: "ethers-js-74812ea32dc06ff7795da7dfb1db20ee"
weight: 100
toc: true
---

Ethers.js provides a range of tools for working with Filecoin, including:

- Contract interactions: Ethers.js allows you to interact with smart contracts on the Filecoin network using a simple, consistent interface.
- Wallet management: Ethers.js provides tools for managing Ethereum-style `0x` wallets, including support for mnemonic phrases, HD wallets, and more.
- Transaction management: With Ethers.js, you can easily create, sign, and send Filecoin EVM runtime transactions.

Ethers.js is widely used in the Ethereum ecosystem, and is a popular choice for building dApps and other blockchain-based applications. Because of the Filecoin EVM runtime, developers can use Ethers.js with the Filecoin network.

## The contract

Instead of writing and deploying a _fresh_ contract, we'll just use one that's already deployed to both the mainnet and Hyperspace testnet. The contract itself is a simple getter-setter application. You can see the variable called `theNote` to a string. You can then read this variable using the `readNote` function.

The contract is deployed at the following addresses:

- Mainnet: `0x2709b194B5ebb6e1933190554C16ec6B959e100c`
- Hyperspace: `0xFE357661DC7Ce68de17e5A7968BdeaaecC955223`

The ABI for the contract is:

```solidity
[
    {
        "inputs": [
        {
            "internalType": "string",
                "name": "newNote",
                "type": "string"
        }
        ],
        "name": "writeNote",
        "outputs": [],
        "stateMutability": "nonpayable",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "readNote",
        "outputs": [
        {
            "internalType": "string",
            "name": "",
            "type": "string"
        }
        ],
        "stateMutability": "view",
        "type": "function"
    },
    {
        "inputs": [],
        "name": "theNote",
        "outputs": [
        {
            "internalType": "string",
            "name": "",
            "type": "string"
        }
        ],
        "stateMutability": "view",
        "type": "function"
    }
]
```

<!-- 1. Create a blank HTML page. -->
<!--     1. Add ethers to the top. -->
<!--     1. Add a classless stylesheet. -->
<!--     1. Add a simple form to enter information and show the results. -->
<!-- 1. Connect MetaMask as the network interface. -->
<!-- 1. -->
