# Ops readiness board — before OPEN

**Single status board** of remaining **human** gates before replacing the bounty draft with an OPEN notice.

**Master go/no-go before OPEN:** `OPEN_GATE_CHECKLIST.md` (do not mark OPEN while pool=0 or multisig UNVERIFIED).

**Gate freeze summary:** `STATUS.md` (done vs human-only; bounty CLOSED).

**Current snapshot facts (2026-10-07):**

| Fact | Value |
|------|-------|
| Claim pool | **0 MTRN** (recheck block 11,861,943) |
| Multisig | **UNVERIFIED** |
| Bounty | **CLOSED** |
| On-chain `latestEpoch` | **1** (next publishable after funding = **2**) |
| Package SHA-256 | `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051` |
| Token | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |

Testnet MTRN has **no assumed monetary value**. Documentation only — no on-chain txs from this pack.

## Remaining human gates (all required before OPEN)

- [ ] **Fund claim pool** — complete `CLAIM_POOL_FUNDING_CHECKLIST.md`, then **republish** absolute caps in `EPOCH_0_CAPS.md` from the non-zero pool balance (budget ≤ 5% of pool; beneficiary ≤ 15% of budget).
- [ ] **Verify multisig** — complete `PUBLISHER_KEY_MULTISIG.md` (status remains **UNVERIFIED** until humans fill the verification record).
- [ ] **Complete publisher dry-run** — complete `PUBLISHER_DRY_RUN.md` (≥2 of 3 labeled A/B/C approve a *dummy* digest; public note; **NO ROOT** / never call `publishEpoch`).
- [ ] **Optional:** timestamps.org when DNS works — see `TIMESTAMP_RECORD.md` (still unresolved). Alice-path OTS proofs are **Bitcoin-anchored** (block 970307); finney still pending.
- [ ] **Only then:** replace `BOUNTY_ANNOUNCEMENT_DRAFT.md` with an OPEN notice (absolute caps, deadline, submission channel). Until then the bounty stays **CLOSED**.

## Already done (not blocking OPEN by themselves)

- [x] Controls Package hashed + OTS calendars + GitHub publish
- [x] Acceptance checklist published (`01_Acceptance_Checklist.md`)
- [x] Public tally seed (`PUBLIC_TALLY.md`)
- [x] Chain snapshot recorded (`CHAIN_SNAPSHOT_2026-10-07.md`)
- [x] Chain recheck — pool still 0 (`CHAIN_SNAPSHOT_RECHECK_2026-10-07.md`)
- [x] OTS upgrade — alice-path Bitcoin-anchored (`TIMESTAMP_RECORD.md`)

## Still forbidden until every required gate above is checked

- Publishing any Merkle root / calling `publishEpoch`
- Opening claims
- Advertising the bounty as paid work with real-world value
- Treating treasury balance as claim-pool pre-fund

## Related

- Gate freeze: `STATUS.md`
- OPEN gate checklist: `OPEN_GATE_CHECKLIST.md`
- Preflight detail: `EPOCH_0_PREFLIGHT.md`
- Dry-run pack: `PUBLISHER_DRY_RUN.md`
- Funding: `CLAIM_POOL_FUNDING_CHECKLIST.md`
- Multisig: `PUBLISHER_KEY_MULTISIG.md`
- Caps: `EPOCH_0_CAPS.md`
- Bounty draft (CLOSED): `BOUNTY_ANNOUNCEMENT_DRAFT.md`
