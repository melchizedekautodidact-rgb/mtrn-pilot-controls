# MTRN Testnet Pilot – Controls Package

This directory contains every operational recommendation from the independent review, turned into ready-to-use artifacts.

| File | Purpose |
|------|---------|
| `MTRN_Pilot_Controls_Package.md` | Master document (v1.0) – publish or hash this first |
| `01_Acceptance_Checklist.md` | Exact checklist for the 33 cohesive-energy datapoints |
| `02_Publisher_Procedure.md` | Step-by-step publisher process including public hashing |
| `03_Stop_Conditions.md` | Automatic abort triggers |
| `04_Reviewer_Declaration_Template.md` | Form each independent reviewer must sign |
| `05_Public_Tally_Template.md` | Live balance / commitment tracker template |
| `PUBLIC_TALLY.md` | Published public tally seed (gate artifact) |
| `PUBLISHER_KEY_MULTISIG.md` | Multi-party publisher confirmation + verification procedure |
| `CLAIM_POOL_FUNDING_CHECKLIST.md` | Human-only procedure to fund the active claim pool |
| `EPOCH_0_CAPS.md` | Absolute Epoch 0 budget / beneficiary caps |
| `BOUNTY_ANNOUNCEMENT_DRAFT.md` | Public bounty text (**NOT OPEN**) |
| `CHAIN_SNAPSHOT_2026-10-07.md` | Sepolia public state snapshot (pool 0 MTRN) |
| `CHAIN_SNAPSHOT_RECHECK_2026-10-07.md` | Sepolia read-only recheck (pool still 0 MTRN; block 11,861,943) |
| `EPOCH_0_PREFLIGHT.md` | Gate checklist before opening the bounty |
| `PUBLISHER_DRY_RUN.md` | Dry-run: dummy multi-party approval + dummy digest (**NO ROOT**) |
| `OPS_READINESS.md` | Single status board of remaining human gates before OPEN |
| `OPEN_GATE_CHECKLIST.md` | Master go/no-go before replacing bounty draft with OPEN |

**Next actions for the pilot team (human only):**

1. ~~Hash + OpenTimestamps + GitHub publish~~ — done. SHA-256: `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`. See `TIMESTAMP_RECORD.md` and `MTRN_Pilot_Controls_Package.md.ots`. Alice-path OTS proofs upgraded to **Bitcoin block 970307**; finney still pending. timestamps.org DNS still fails; OTS calendars remain the public timestamp channel. Sepolia pool recheck: still **0 MTRN** at block 11,861,943 (`CHAIN_SNAPSHOT_RECHECK_2026-10-07.md`).
2. **(a)** Fund the active claim pool on Sepolia per `CLAIM_POOL_FUNDING_CHECKLIST.md` (never treat treasury as pool pre-fund).
3. **(b)** Verify and fill multi-party publisher control per `PUBLISHER_KEY_MULTISIG.md` (status remains UNVERIFIED until humans complete it).
4. **(c)** Republish absolute caps in `EPOCH_0_CAPS.md` from the non-zero claim-pool balance (budget ≤ 5% of pool; beneficiary ≤ 15% of budget).
5. **(d)** Complete publisher dry-run per `PUBLISHER_DRY_RUN.md` (dummy multi-party approval of a dummy digest; **NO ROOT** / never call `publishEpoch`) **before** opening.
6. **(e)** Track remaining gates on `OPS_READINESS.md` and clear every required box on `OPEN_GATE_CHECKLIST.md` (do not mark OPEN while pool=0 or multisig UNVERIFIED). Only then open the bounty for the 33 datapoints (`BOUNTY_ANNOUNCEMENT_DRAFT.md` stays **NOT OPEN** until then).

No on-chain actions, code changes, or token movements are performed or recommended by this package. Testnet MTRN has no assumed monetary value.
