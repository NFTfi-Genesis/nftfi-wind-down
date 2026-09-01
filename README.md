# NFTfi Wind-Down

NFTfi has shut down. This repository contains everything you need to manage existing loans, retrieve staked tokens, and access historical data — without relying on any NFTfi-operated service.

## What Happened

NFTfi was a peer-to-peer NFT lending protocol. The team decided to wind down the business, with the platform fully closing on **August 31, 2026**. Full details are in the [announcement](https://x.com/NFTfi/status/2061804810752409998) and [founder letter](https://x.com/stephen_yo/status/2061804240629121370).

The **NFTfi Foundation** is a separate entity and is also winding down. See the [Foundation statement](https://x.com/NFTfiFoundation/status/2069770846160195648) for details on token unstaking.

---

## NFTfi — the lending protocol

### What is still possible on-chain

The NFTfi lending contracts have been paused. New loans and refinancing are no longer possible, but the contracts still allow the following actions:

- Borrowers can repay existing loans directly on-chain.
- Lenders can foreclose defaulted loans directly on-chain.

### In this repository

- **[`how-to-repay-active-loans.md`](./how-to-repay-active-loans.md)** — step-by-step Etherscan instructions to repay the remaining active loans.
- **[`how-to-foreclose-defaulted-loans.md`](./how-to-foreclose-defaulted-loans.md)** — for lenders who have not yet foreclosed defaulted loans. Includes loan IDs, collateral links, contract addresses, and direct Etherscan links needed to claim collateral.
- **[`loan-history-2026-08-31T11-30-55.csv`](./loan-history-2026-08-31T11-30-55.csv)** — every loan ever made on NFTfi, across all contract versions, for record-keeping, tax purposes, or research.

### Contract addresses

| Version | Address |
|---------|---------|
| V1 | [`0x88341d1a8F672D2780C8dC725902AAe72F143B0c`](https://etherscan.io/address/0x88341d1a8F672D2780C8dC725902AAe72F143B0c) |
| V2 | [`0xf896527c49b44aAb3Cf22aE356Fa3AF8E331F280`](https://etherscan.io/address/0xf896527c49b44aAb3Cf22aE356Fa3AF8E331F280) |
| V2 (Collection) | [`0xE52Cec0E90115AbeB3304BaA36bc2655731f7934`](https://etherscan.io/address/0xE52Cec0E90115AbeB3304BaA36bc2655731f7934) |
| V2.1 | [`0x8252Df1d8b29057d1Afe3062bf5a64D503152BC8`](https://etherscan.io/address/0x8252Df1d8b29057d1Afe3062bf5a64D503152BC8) |
| V2.3 | [`0xd0a40eB7FD94eE97102BA8e9342243A2b2E22207`](https://etherscan.io/address/0xd0a40eB7FD94eE97102BA8e9342243A2b2E22207) |
| V2.3 (Collection) | [`0xD0C6e59B50C32530C627107F50Acc71958C4341F`](https://etherscan.io/address/0xD0C6e59B50C32530C627107F50Acc71958C4341F) |
| V3 (Asset) | [`0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6`](https://etherscan.io/address/0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6) |
| V3 (Collection) | [`0xB6adEc2ACc851d30d5fB64f3137234BCDCBBad0D`](https://etherscan.io/address/0xB6adEc2ACc851d30d5fB64f3137234BCDCBBad0D) |

---

## NFTfi Foundation — the NFTFI token

### What is still possible on-chain

The Foundation's unstaking portal closed on **July 8, 2026**. Staked tokens can still be withdrawn directly on-chain from the lock contract that holds them.

### In this repository

- **[`howto-unstake-nftfi-tokens.md`](./howto-unstake-nftfi-tokens.md)** — for NFTFI token holders. A wallet lookup table with the exact Etherscan contract, withdraw function, and parameter values needed to withdraw staked tokens directly on-chain.

### Contract addresses

| Contract | Address |
|----------|---------|
| NFTFI Token (ERC-20) | [`0x09D6F0F5A21f5BE4f59e209747E2d07F50BC694C`](https://etherscan.io/address/0x09D6F0F5A21f5BE4f59e209747E2d07F50BC694C) |
| Token Lock (current) | [`0x8a63B7D2B66FB054705731Cc7964b05e7Ad095cF`](https://etherscan.io/address/0x8a63B7D2B66FB054705731Cc7964b05e7Ad095cF#writeContract) |
| Token Lock (legacy) | [`0xe53FfaCaDbc4744bE405BAD4AbE9852348eBeC02`](https://etherscan.io/address/0xe53FfaCaDbc4744bE405BAD4AbE9852348eBeC02#writeContract) |

Your tokens are held in whichever lock contract you originally staked through. Use the unstaking lookup guide above to find the correct contract, function, and parameter values to unstake.

---

## Open Source

The NFTfi source code is available in the [NFTfi Open Source repository](https://github.com/NFTfi-Genesis/nftfi-opensource).

## Questions

This repository is not maintained. There is no dedicated support team. Please use the guides above for self-service instructions.
