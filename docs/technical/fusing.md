---
nav_order: 2
parent: Technical
title: Fusing Names
layout: default
permalink: technical/fusing
---

# Fusing Names

To mint a Namespace NFT, users fuse one or more tiles from any number of [Tray NFTs](trays.md) held in their wallet. Upon fusing, the Tray NFTs corresponding to the fused tiles are burnt, regardless of how many tiles were used from each tray.

Names must be between 1 and 13 characters long.

## Base Names

CNS registers a simplified version of each name (the *base name*) consisting of only unstylized letters and numbers. This enables users to enter and lookup names using characters on their keyboard.

Base names are generated by removing emojis and converting stylized letters (i>1) into unstylized letters (i=0). Since every Namespace NFT must have a **unique base name**, it is not possible to fuse a name if:
* the resulting base name is already registered
* the name consists of only emojis

| **Name** | **Base Name**        |
|:-----------|:---------------------|
| 𝒶𝔩iƈ🅴 | alice |
| 🤝bob | bob |
| 12345 | 12345 |

The cost to fuse a name depends on the length of the base name.

## The `fuse` Method

The `fuse` method on `Namespace.sol` is responsible for minting Namespace NFTs. This method takes an array of `CharacterData` structs as its only input. Each `CharacterData` item identifies a specific tile in a Tray NFT and modifies its skin tone (for supported emojis). The order of items in the array determines the order of characters in the resulting name.

```solidity
    struct CharacterData {
        /// @notice ID of the Tray NFT
        uint256 trayID;
        /// @notice Offset of the tile within the tray. Valid values 0..TILES_PER_TRAY - 1
        uint8 tileOffset;
        /// @notice Emoji modifier for the skin tone. Can have values of 0 (yellow) and 1 - 5 (light to dark). Only supported by some emojis
        uint8 skinToneModifier;
    }
```

`fuse` can be called by both EOAs and smart contracts:
* If called by an EOA, the user must have approved the Tray NFTs and $NOTE for transfer by `Namespace.sol`.
* If called by a smart contract on behalf of a user, the user must have approved the Tray NFTs for transfer by the smart contract, and the smart contract must have approved $NOTE for transfer by `Namespace.sol`.

Both `approve` and `setApprovalForAll` on `Tray.sol` can be used to approve Tray NFTs for transfer by `Namespace.sol`.