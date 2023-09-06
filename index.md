---
nav_order: 1
title: Overview
layout: default
permalink: overview
---

# Overview

Canto Namespace Protocol (CNS) is a subprotocol for the Canto Identity Protocol that allows users to mint on-chain display names. To [mint a name](fusing.md), users must fuse tiles (characters) from Tray NFTs they have purchased. Tiles include stylized and unstylized Latin letters, numbers, and emojis.

![Example Name](assets/sample_name.svg)

For every name minted, CNS registers a simplified version of the name (a *base name*) consisting of only unstylized letters and numbers. Base names resolve to specific wallets, enabling users to enter and lookup names using characters on their keyboard.

## Architecture

CNS consists of three smart contracts:

* [`Namespace.sol`](https://github.com/mkt-market/canto-namespaces-protocol/blob/master/src/Namespace.sol)
* [`Tray.sol`](https://github.com/mkt-market/canto-namespaces-protocol/blob/master/src/Tray.sol)
* [`Utils.sol`](https://github.com/mkt-market/canto-namespaces-protocol/blob/master/src/Utils.sol)

### Namespace.sol

`Namespace.sol` is an ERC721 contract responsible for the [minting of Namespace NFTs](fusing.md). Additionally, it acts as a registry of base names enabling name resolution/lookups.

### Tray.sol

`Tray.sol` is an ERC721 contract responsible for the minting of [Tray NFTs](trays.md).

### Utils.sol

`Utils.sol` is a helper contract which contains methods to:

* convert characters to unicode bytes
* generate SVGs for an array of tiles
* generate pseudorandom numbers
* get character UTF-8 encoding