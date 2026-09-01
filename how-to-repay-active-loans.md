# Repay the Remaining Active NFTfi Loans

NFTfi's web app is no longer available. The loans below can be
repaid directly through Etherscan on Ethereum mainnet.

> Verified against Ethereum mainnet on 2026-09-01. Check the live payoff again
> immediately before signing.

## Choose the loan

| Loan ID | Collateral | Token links | Exact payoff | Expected collateral recipient |
| --- | --- | --- | --- | --- |
| `13623` | [CloneX #14354](https://opensea.io/item/ethereum/0x49cF6f5d44E70224e2E23fDcdd2C053F30aDA28B/14354) | [WETH — Read](https://etherscan.io/address/0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2#readContract) · [Write](https://etherscan.io/address/0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2#writeContract) | `1128684931506849200` wei (`1.1286849315068492 WETH`) | `0x3Da40AF749da10644fCd1816e34E62f0095B2Bd8` |
| `16392` | [Keatsian Capybara #478](https://opensea.io/item/ethereum/0x4440732b0d85e2a77dcb2caedfd940154241249a/478) | [USDC — Read](https://etherscan.io/address/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48#readContract) · [Write](https://etherscan.io/address/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48#writeContract) | `4049315068` base units (`4,049.315068 USDC`) | `0x41DD1c6338e5b3cdF9Dc69e20DaD9834aE36A6D3` |

The repayment contract is [NFTfi V3 Asset — Read Contract](https://etherscan.io/address/0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6#readContract)
and [Write Contract](https://etherscan.io/address/0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6#writeContract).

## Repayment steps

1. Use a wallet that has ETH for gas and at least the exact payoff in the
   required WETH or USDC. This is the **paying wallet**. Any wallet can pay;
   the collateral goes to the recipient shown above, not to the paying wallet.
2. Open the selected token's **Read** link in the table, click **Connect to
   Web3**, and connect the paying wallet.
3. Open the token's **Read Contract** tab and expand `allowance`. Enter:

   - `owner`: the paying wallet address;
   - `spender`: `0x6730697f33d6D2490029b32899E7865c0d902Ca0`.

   Click **Query**. If the result is at least the exact payoff, skip to step 5.
4. Otherwise, open the token's **Write** link in the table and expand `approve`.
   Enter the same `spender` and the exact payoff from the table as `amount`.
   Enter the raw integer shown in the table — without decimal points, commas, or
   the token symbol.
   Click **Write** and confirm the approval transaction. Wait for it to
   confirm.
5. Open [V3 Asset — Read Contract](https://etherscan.io/address/0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6#readContract).
   First call `loanRepaidOrLiquidated` with the Loan ID; it must return `false`.
   Then call `getPayoffAmount` with the same ID; it must equal the exact payoff
   in the table.
6. Open [V3 Asset — Write Contract](https://etherscan.io/address/0x9F10D706D789e4c76A1a6434cd1A9841c875C0A6#writeContract),
   click **Connect to Web3**, and connect the same paying wallet. Expand
   `payBackLoanSafe`, enter the Loan ID as `_loanId`, click **Write**, and
   confirm the transaction.
7. Wait for the transaction to confirm. A successful receipt has status
   **Success** and emits `LoanRepaid`. Verify that the NFT is transferred to
   the expected recipient in the table.

## Important

- Approval is optional only when the paying wallet already has enough
  allowance; it is required when allowance is lower or zero.
- The lender does not need to approve anything.
- Use `payBackLoanSafe`, not `payBackLoan` or a foreclosure function.
- If a transaction fails, do not retry blindly. Save its hash and revert
  message, then repeat step 5 before taking another action.
