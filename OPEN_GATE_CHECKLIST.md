# OPEN gate checklist — go / no-go

**Master checklist** before replacing `BOUNTY_ANNOUNCEMENT_DRAFT.md` with an **OPEN** notice.

**Hard rule:** Do **not** mark OPEN while claim pool = **0 MTRN** or multisig is **UNVERIFIED**. Both must be cleared with evidence in their source files first.

**Current facts (2026-10-07):**

| Fact | Value |
|------|-------|
| Bounty | **CLOSED** |
| Claim pool | **0 MTRN** (recheck block 11,861,943; see `CHAIN_SNAPSHOT_RECHECK_2026-10-07.md`) |
| Multisig | **UNVERIFIED** |
| Token | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |
| Package SHA-256 | `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051` |

Docs only. No on-chain txs from this pack. Testnet MTRN has **no assumed monetary value**. No invented signers.

## Already done

- [x] Controls Package hashed — `MTRN_Pilot_Controls_Package.sha256` / SHA-256 above (`EPOCH_0_PREFLIGHT.md`, `TIMESTAMP_RECORD.md`)
- [x] OpenTimestamps calendar receipts submitted — `MTRN_Pilot_Controls_Package.md.ots` + companion `stamp_*.ots` (`TIMESTAMP_RECORD.md`)
- [x] OTS upgrade (alice-path) to Bitcoin block **970307** — finney still pending (`TIMESTAMP_RECORD.md`)
- [x] Public GitHub publish — https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls (`TIMESTAMP_RECORD.md`)
- [x] Acceptance checklist published — `01_Acceptance_Checklist.md`
- [x] Public tally seed ready — `PUBLIC_TALLY.md` (bounty still CLOSED; pool 0)

## Required gates (all must be checked before OPEN)

- [ ] **Fund claim pool** — complete `CLAIM_POOL_FUNDING_CHECKLIST.md` (post-fund evidence table filled; pool balance **> 0**). Stop if still 0.
- [ ] **Republish absolute caps** — update `EPOCH_0_CAPS.md` from the **non-zero** pool balance (budget ≤ 5% of pool; beneficiary ≤ 15% of budget). Caps must not remain 0/0.
- [ ] **Verify multisig** — complete `PUBLISHER_KEY_MULTISIG.md` verification record; change status from **UNVERIFIED**. Do not invent signers. Single-key = stop (`03_Stop_Conditions.md`).
- [ ] **Complete publisher dry-run** — finish `PUBLISHER_DRY_RUN.md` (≥2 of 3 labeled A/B/C approve a *dummy* digest; public note; **NO ROOT** / never call `publishEpoch`).
- [ ] **Preflight all-green** — every required human gate in `EPOCH_0_PREFLIGHT.md` and the ops board `OPS_READINESS.md` is checked (pool funded, caps republished, multisig verified, dry-run done).
- [ ] **Tally reflects funded state** — update `PUBLIC_TALLY.md` remaining/pre-fund from post-fund evidence (still no new commitments until OPEN).
- [ ] **Only then:** replace `BOUNTY_ANNOUNCEMENT_DRAFT.md` with an OPEN notice (absolute caps, deadline, submission channel). Until every box above is checked, bounty stays **CLOSED**.

## Explicit no-go

| Condition | Action |
|-----------|--------|
| Pool balance still **0 MTRN** (`CLAIM_POOL_FUNDING_CHECKLIST.md` / `EPOCH_0_CAPS.md` / `CHAIN_SNAPSHOT_2026-10-07.md`) | **NO-GO** — do not OPEN |
| Multisig still **UNVERIFIED** (`PUBLISHER_KEY_MULTISIG.md`) | **NO-GO** — do not OPEN |
| Dry-run incomplete (`PUBLISHER_DRY_RUN.md`) | **NO-GO** — do not OPEN |
| Caps still 0/0 after “funding” claim (`EPOCH_0_CAPS.md`) | **NO-GO** — do not OPEN |
| Preflight / ops board incomplete (`EPOCH_0_PREFLIGHT.md`, `OPS_READINESS.md`) | **NO-GO** — do not OPEN |

## Optional (does not unblock OPEN by itself)

- [x] OpenTimestamps Bitcoin anchor (alice-path proofs) — `BitcoinBlockHeaderAttestation(970307)` in `TIMESTAMP_RECORD.md` / upgraded `.ots`
- [ ] timestamps.org reachable and stamp recorded — see `TIMESTAMP_RECORD.md` (DNS still fails; optional; finney calendar still pending)

## Still forbidden until OPEN gates pass

- Publishing any Merkle root / calling `publishEpoch`
- Opening claims
- Advertising the bounty as paid work with real-world value
- Treating treasury balance as claim-pool pre-fund

## Related

| Role | File |
|------|------|
| Funding | `CLAIM_POOL_FUNDING_CHECKLIST.md` |
| Multisig | `PUBLISHER_KEY_MULTISIG.md` |
| Dry-run | `PUBLISHER_DRY_RUN.md` |
| Caps | `EPOCH_0_CAPS.md` |
| Preflight | `EPOCH_0_PREFLIGHT.md` |
| Ops board | `OPS_READINESS.md` |
| Tally | `PUBLIC_TALLY.md` |
| Bounty draft (CLOSED) | `BOUNTY_ANNOUNCEMENT_DRAFT.md` |
| Timestamp / OTS | `TIMESTAMP_RECORD.md` |
| Snapshot | `CHAIN_SNAPSHOT_2026-10-07.md` |
| Recheck | `CHAIN_SNAPSHOT_RECHECK_2026-10-07.md` |
