# MTRN public chain snapshot — 2026-10-07

**Scope:** Existing Ethereum Sepolia pilot only. Apply to this repository only for the token and claim-pool addresses below. A separate proposed deployment or multisig has **not** been identified or verified.

**Nature:** Public state snapshot. Not an approval, signature, funding transfer, or launch confirmation. No wallet or transaction was used.

## Network

| Field | Value |
|-------|-------|
| Network | Ethereum Sepolia |
| Chain ID | 11155111 |
| Finalized snapshot block | 11,861,528 |
| Block hash | `0xe4d6a6144a2ba4d1a76df29028e89a93b3ac0687a70bb518fb3159d4f5c806af` |
| Block time (UTC) | 2026-10-07 07:35:48 |
| Block time (America/Chicago) | 2026-10-07 02:35:48 |
| Read ~ | 02:54 America/Chicago |

Confirming providers: Codex read-only RPC; PublicNode and Automata 1RPC matched at this block. dRPC returned HTTP 400 and was not counted.

## Addresses

| Role | Address |
|------|---------|
| Token (18 decimals, fixed 1e9 supply) | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Active WorkEpochClaims pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |

Explorers:

- Pool: https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract
- Token: https://sepolia.etherscan.io/token/0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB
- Block: https://sepolia.etherscan.io/block/11861528

## Balances / epochs (at snapshot)

| Item | Value |
|------|-------|
| Pre-funded balance **in active claim pool** | **0 MTRN** |
| Pool reserved | 0 MTRN |
| Treasury wallet balance | 1,000,000,000 MTRN (not a funded reward allocation in the claim pool) |
| Contract `latestEpoch` | 1 |
| Epoch 1 budget / claimed | 1 MTRN / 1 MTRN |
| Epoch 0 budget / claimed / root | zero / default |

**Implication:** No MTRN is currently available in the active claim pool for a new reward round. WorkEpochClaims requires each published epoch = `latestEpoch + 1`, so the next on-chain epoch would be **2**. The draft controls label “Epoch 0” is a **planning** label, not a funded on-chain epoch.

## Multisig / publisher

| Field | Status |
|-------|--------|
| Multisig scheme | **Unverified.** Min 2-of-3 is a draft requirement only; no deployed threshold confirmed. |
| Signer labels A/B/C | Unassigned / unverified |
| Current publisher | Existing treasury wallet; no multisig roster in reviewed records |
| Publisher code | EIP-7702 delegation indicator; does **not** establish a multisig threshold |
| Confirmed by | Codex + PublicNode + Automata 1RPC (balance/accounting only). Wallet signer identities, custody, and threshold remain unconfirmed. |

Agent result quorum and enrollment-root thresholds are separate draft policies and do not provide wallet signatures.

## Source note

Original read-only handoff also references `F:\OPEN_AI\MTRN_PUBLIC_CHAIN_SNAPSHOT_2026-10-07.json` (local to the operator). EIP-7702: https://eips.ethereum.org/EIPS/eip-7702
