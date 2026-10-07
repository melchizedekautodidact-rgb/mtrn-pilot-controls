# Claim pool funding checklist (human-only)

**Purpose:** Fund the active WorkEpochClaims pool **before** any new reward round. Documentation and ops procedure only — this file does not authorize or perform transfers.

**Scope:** Ethereum Sepolia only. Testnet MTRN has **no assumed monetary value**.

**Status as of snapshot 2026-10-07 (block 11,861,528):** Active pool balance/reserved = **0 MTRN**. Treasury holds 1e9 MTRN; that is **NOT** pool allocation.

## Addresses (Sepolia)

| Role | Address |
|------|---------|
| Token (18 decimals) | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Active WorkEpochClaims pool (fund **this**) | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |

Explorers:

- Pool: https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract
- Token: https://sepolia.etherscan.io/token/0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB

## Explicit rules

1. Transfer MTRN **into** `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` on **Sepolia only**.
2. **Never** treat treasury balance as claim-pool pre-fund. Caps are computed from `balanceOf(pool)` (and pool reserved, if any), not from treasury holdings.
3. **Stop** if the intended transfer would exceed what ops intend to allocate. Do not over-fund “just in case.”
4. No assumed monetary value for testnet MTRN. Funding is an ops gate, not a valuation event.
5. Do **not** open the bounty, publish a Merkle root, or advertise paid work until this checklist, multisig verification, and republished caps are complete.

## Human procedure

1. Agree the exact Sepolia MTRN amount to place in the active claim pool (ops intent only).
2. Confirm destination is the **active** pool address above (not treasury, not a draft/alternate deployment).
3. Execute the token transfer as humans using their own custody tooling (outside this repo / agent). No agent or script in this package sends the tx.
4. After confirmation, **re-read** (read-only RPC or Etherscan):
   - Token `balanceOf(0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059)`
   - Pool reserved (if the contract exposes it)
   - New block number and block hash
5. Record post-fund evidence in the table below.
6. **Republish** `EPOCH_0_CAPS.md` with non-zero absolutes:
   - Planning epoch budget ≤ **5%** of post-fund claim-pool balance
   - Single beneficiary ≤ **15%** of that epoch budget
7. Only then revisit remaining Epoch 0 gates (`EPOCH_0_PREFLIGHT.md`). Multisig must still be verified separately.

## Post-fund evidence (fill after funding)

| Field | Value |
|-------|-------|
| Evidence URL (tx or explorer) | — |
| Amount funded (MTRN) | — |
| Block number | — |
| Block hash | — |
| Token `balanceOf(pool)` after fund | — |
| Pool reserved (if any) after fund | — |
| Who confirmed (read-only RPC / explorer) | — |
| Confirmed date (UTC) | — |

## Related

- Snapshot: `CHAIN_SNAPSHOT_2026-10-07.md`
- Caps (republish after fund): `EPOCH_0_CAPS.md`
- Preflight: `EPOCH_0_PREFLIGHT.md`
- Multisig (separate gate): `PUBLISHER_KEY_MULTISIG.md`
