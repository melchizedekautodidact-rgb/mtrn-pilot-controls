# MTRN Sepolia chain recheck — 2026-10-07

**Nature:** Read-only public state recheck (`eth_call` / `balanceOf` / block reads only). No wallet, no transaction, no funding, no launch confirmation.

**Prior snapshot:** `CHAIN_SNAPSHOT_2026-10-07.md` (finalized block 11,861,528).

## Network (this recheck)

| Field | Value |
|-------|-------|
| Network | Ethereum Sepolia |
| Chain ID | 11155111 |
| Finalized block | **11,861,943** |
| Block hash | `0x688564f73e19a8cff47bfdc8ab9c0302fdc71571a20a830c16b52b38ea3feb48` |
| Block time (UTC) | 2026-10-07 08:59:00 |
| Block time (America/Chicago) | 2026-10-07 03:59:00 |
| Read performed (UTC) | ~2026-10-07 09:14 |

Confirming providers (matched at the same finalized block / balance): **PublicNode** (`ethereum-sepolia-rpc.publicnode.com`, User-Agent required), **Tenderly** (`sepolia.gateway.tenderly.co`), **MEW** (`nodes.mewapi.io/rpc/sepolia`). Automata 1RPC / bare PublicNode without UA returned 403 or unusable chain id in this environment; dRPC returned HTTP 400 (not counted).

## Addresses (unchanged)

| Role | Address |
|------|---------|
| Token (18 decimals) | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Active WorkEpochClaims pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |

Explorers:

- Pool: https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract
- Token: https://sepolia.etherscan.io/token/0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB
- Block: https://sepolia.etherscan.io/block/11861943

## Balances / epochs (at recheck)

| Item | Value |
|------|-------|
| Token `balanceOf(pool)` | **0 MTRN** (raw `0`) |
| Contract `totalReserved()` | **0** |
| Contract `latestEpoch()` | **1** |
| `epochBudgets(1)` | 1 MTRN (`1e18` wei) |
| `claimedAmounts(1)` | 1 MTRN (`1e18` wei) |
| `merkleRoots(1)` | `0xbabe10214231eb215f6e7815f7fb33b9a810b4d0aed874c8613a389ac7c44731` |
| Epoch 0 budget / claimed / root | 0 / 0 / zero |
| `rewardToken()` | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` (matches token) |

**Delta vs prior snapshot (block 11,861,528):** Pool balance remains **0 MTRN**. `latestEpoch` remains **1**. Epoch 1 budget/claimed remain 1/1. No new reward funds in the active claim pool.

**Implication:** Absolute planning caps stay **0 / 0**. Bounty stays **CLOSED**. Next publishable on-chain epoch index would still be **2** only after the pool is funded. Draft “Epoch 0” remains a planning label.

## Multisig / publisher

Unchanged from prior snapshot: **UNVERIFIED**. No signer roster confirmed in this read-only pass. Do not invent signers. Immutable publisher-related address observed on-contract (selector `0xcf43a27a`): `0xc10Fe9EAa90A64d59968a7b79Eb09e0AbA3891D9` (also shown as contract creator on Etherscan). EIP-7702 / custody / 2-of-3 threshold still not established by this recheck.

## Method note

- Token balance: ERC-20 `balanceOf(address)` (`0x70a08231`) via `eth_call` at finalized block.
- Pool getters: `latestEpoch()`, `totalReserved()`, `rewardToken()`, `epochBudgets(uint64)`, `claimedAmounts(uint64)`, `merkleRoots(uint64)`.

---

## Recheck #2 (2026-10-07 ~10:14 UTC)

**Nature:** Read-only public state recheck (`eth_call` only). No wallet, no transaction, no funding, no launch confirmation.

| Field | Value |
|-------|-------|
| Finalized block | **11,862,230** |
| Block hash | `0x02bcf960a98f47cfd30f104aedcd8b16b8616bc587418aacc1aa91190535c002` |
| Block time (UTC) | 2026-10-07 09:56:36 |
| Block time (America/Chicago) | 2026-10-07 04:56:36 CDT |
| Read performed (UTC) | ~2026-10-07 10:14 |

Confirming providers (matched at the same finalized block / values): **PublicNode** (`ethereum-sepolia-rpc.publicnode.com`, User-Agent set), **Tenderly** (`sepolia.gateway.tenderly.co`). MEW Cloudflare-blocked; Automata 1RPC usage-limited (not counted).

| Item | Value |
|------|-------|
| Token `balanceOf(pool)` | **0 MTRN** (raw `0`) |
| Contract `totalReserved()` | **0** |
| Contract `latestEpoch()` | **1** |
| `epochBudgets(1)` / `claimedAmounts(1)` | 1 MTRN / 1 MTRN |
| `merkleRoots(1)` | `0xbabe10214231eb215f6e7815f7fb33b9a810b4d0aed874c8613a389ac7c44731` |
| Epoch 0 budget / claimed / root | 0 / 0 / zero |
| `rewardToken()` | matches token `0x240C…95bB` |

**Delta vs recheck #1 (block 11,861,943):** Pool balance remains **0 MTRN**. `latestEpoch` remains **1**. No new reward funds. Absolute planning caps stay **0 / 0**. Bounty stays **CLOSED**.

Explorer block: https://sepolia.etherscan.io/block/11862230
