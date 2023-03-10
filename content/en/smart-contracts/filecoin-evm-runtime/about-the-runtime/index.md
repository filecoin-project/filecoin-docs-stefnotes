---
title: "About the runtime"
description: "This page details what exactly this EVM compatibility means, and any other information that Ethereum developers may need to build applications on the Filecoin virtual machine."
lead: "The Filecoin virtual machine (FVM) contains an Ethereum virtual machine (EVM) runtime, allowing Ethereum and Solidity developers to run their contracts on the FVM with little to no modifications. This page details what exactly this EVM compatibility means, and any other information that Ethereum developers may need before building applications on the FVM."
draft: false
images: []
type: docs
menu:
  smart-contracts:
    parent: "smart-contracts-filecoin-evm-runtime"
    identifier: "about-the-runtime-932a1ced1a966c0e7849ec231bb47424"
weight: 100
toc: true
---

The Ethereum Virtual Machine is an execution environment initially designed, built for, and run on the Ethereum blockchain. The EVM was revolutionary because, for the first time, any arbitrary code could be deployed to and run on a blockchain. This code inherited all the decentralized properties of the Ethereum blockchain. Before the EVM, a new blockchain had to be created with custom logic and then bootstrapped with validators every time a new type of decentralized application needed to be built.

Code deployed to EVM is typically written in the high-level language Solidity, although other languages, such as Vyper, exist. The high-level Solidity code is compiled to EVM bytecode which is what is actually deployed to and run on the EVM. Due to it being the first virtual machine to run on top of a blockchain, the EVM has developed one of the strongest developer ecosystems in Web3 to date. Today, many different blockchains run their own instance of the EVM to allow developers to easily port their existing applications into the new blockchain's ecosystem.

## Ethereum Virtual Machine

The Filecoin EVM runtime is the Ethereum virtual machine (EVM) virtualized as a runtime on top of the Filecoin virtual machine. It allows developers to port any existing EVM-based smart contracts straight onto the Filecoin network. The Filecoin EVM runtime is also completely compatible with any EVM development tools, such as Hardhat, Foundry, and MetaMask, making deploying and interacting with EVM-based actors easy! This is because Filecoin nodes offer the Ethereum JSON-RPC API.

## FEVM and native FVM

Eventually, developers will have the option to deploy actors on either the Filecoin EVM runtime or native FVM. But which should you choose? The decision can be summed up as such: if you want better performance, write actors that are compiled to WASM and deployed to native FVM. If you are familiar with Solidity and want access to the EVM ecosystem of tools, but don't mind less performance, deploy to the Filecoin EVM runtime:

| &nbsp; | FVM | FEVM |
| ------ | --- | ---- |
| **Pros** | Native execution speed and performance on Filecoin (i.e., less gas cost per unit of actor code executed).<br><br>Write actors in any language that compiles to WASM 1. | Take advantage of current Solidity and EVM tooling to quickly port or write actors. |
| **Cons** | Tooling is not yet as mature as EVM tooling. | Higher gas fees and lower performance due to the virtualization overhead of the FEVM. |

In both cases, you have access to all the awesome power of the Filecoin blockchain, including storage contracts as a native primitive!

## EVM compatibility

In the context of Filecoin and the Filecoin virtual machine (FVM), the term _EVM compatibility_ means that, as of the [v18 Hygge network upgrade (scheduled for Mar 2023)](https://github.com/filecoin-project/community/discussions/74?sort=new#discussioncomment-4313888):

- EVM runtime compiles to WASM, which allows the FVM to emulate EVM bytecode and support EVM as a foreign runtime.
- The new F4 addressing class allows an imported EVM to be addressed in the Filecoin network via it's Ethereum address.
- Familiar EVM tooling, like MetaMask, Hardhart, Remix and more, can interact with Lotus nodes via the Ethereum JSON-RPC API.
- An imported EVM can interact with the FVM, providing access to Filecoin-specific features, like built-in actors.

So, for developers, _EVM compatibility_ means that their existing Solidity or Yul smart contracts (with support for other EVM-compatible languages planned in later upgrades) can be ported into an EVM virtualized as a runtime on top of the Filecoin Virtual Machine, called the _Filecoin Ethereum Virtual Machine (FEVM)_. Through the FEVM, developers can create, test and deploy smart contracts using languages, concepts and tools that they are already familiar with, and enjoy the rich functionality of the Filecoin network at the same time. 

However, there are a number of tradeoffs that should be considered when choosing whether to deploy a smart contract onto the FEVM or the FVM:

- Due to the virtualization overhead, contracts on the FEVM have higher gas fees and lower performance than FVM_native contracts.
- FVM-specific tooling is not yet as mature as Ethereum-native tooling.

For a deeper dive into the concepts discussed on this page, see this presentation by [@truckerfling]('https://twitter.com/truckerfling') on Ethereum compatibility of FVM:

{{< youtube "lgUMVhM3FIM" >}}
