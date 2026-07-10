# NFTfi Wind-Down

## What Happened

NFTfi is a peer-to-peer NFT lending protocol that is winding down. The team decided to wind down the business, with the platform fully closing on **August 31, 2026**. Full details are in the [announcement](https://x.com/NFTfi/status/2061804810752409998) and [founder letter](https://x.com/stephen_yo/status/2061804240629121370).

The **NFTfi Foundation** is a separate entity and is also winding down. See the [Foundation statement](https://x.com/NFTfiFoundation/status/2069770846160195648) for details on token unstaking.

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

## Questions

This repository is not maintained. There is no dedicated support team. Please use the guides above for self-service instructions.
