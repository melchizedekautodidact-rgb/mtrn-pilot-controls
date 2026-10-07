# Epoch 0 hard caps (planning) — status from chain snapshot

**Status:** Absolute **claim-pool** pre-fund is **0 MTRN** at Sepolia finalized block **11,861,943** (recheck; prior 11,861,528). No new reward round can be funded from the active pool until tokens are transferred into it. See `CHAIN_SNAPSHOT_RECHECK_2026-10-07.md` and `CHAIN_SNAPSHOT_2026-10-07.md`.

**Rules from Controls Package v1.0:** Planning epoch budget ≤ 5% of pre-funded **claim-pool** balance; single beneficiary ≤ 15% of that epoch budget; max leaves = 33.

## Absolute caps (claim pool)

| Control | Rule | Absolute (snapshot) |
|---------|------|---------------------|
| Pre-funded balance (active WorkEpochClaims) | On-chain pool | **0 MTRN** |
| Planning epoch budget | ≤ 5% of pre-funded | **0 MTRN** |
| Single-beneficiary cap | ≤ 15% of epoch budget | **0 MTRN** |
| Maximum leaves | Exactly 33 | 33 (not open) |

Treasury holds 1,000,000,000 MTRN but that is **not** a funded reward allocation in the claim pool.

## Naming note

Draft “Epoch 0” is a planning label. On-chain `latestEpoch` is **1** (budget/claimed 1/1). Next publishable epoch index would be **2** if/when the pool is funded.

## Public tally seed

```
Epoch | Published Root | Total Committed | Remaining Balance | % of Pre-fund Used | Notes
------|----------------|-----------------|-------------------|--------------------|------
plan  | (none)         | 0 MTRN          | 0 MTRN           | n/a                | Pool unfunded; bounty closed
1     | (on-chain)     | 1 MTRN claimed  | 0 MTRN           | n/a                | Historical; do not reuse
```

## Still closed

Do not open the 33-datapoint bounty until the claim pool is funded, absolute caps are republished from a non-zero balance, and `PUBLISHER_KEY_MULTISIG.md` is actually confirmed (currently unverified).
