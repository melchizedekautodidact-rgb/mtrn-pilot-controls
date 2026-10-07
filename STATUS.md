# STATUS — gate freeze (2026-10-07)

**Bounty: CLOSED.** Documentation and read-only evidence only. No on-chain txs, no `publishEpoch`, no OPEN notice from this pack.

**Repo:** [mtrn-pilot-controls](https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls)  
**Package SHA-256:** `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`

This file freezes the agent-side gate work. Remaining OPEN blockers are **human-only**.

---

## Done (agent / public evidence)

| Item | Status / pointer |
|------|------------------|
| Controls package hashed | SHA-256 `fb980fcf…e051` — `MTRN_Pilot_Controls_Package.sha256` |
| GitHub publish | [melchizedekautodidact-rgb/mtrn-pilot-controls](https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls) `main` |
| Bitcoin-anchored OTS | Alice-path proofs: **Bitcoin block 970307** (tx `3bacccc1…5c7d`); see `TIMESTAMP_RECORD.md`. Finney calendar still pending. timestamps.org DNS still fails. |
| Acceptance checklist | `01_Acceptance_Checklist.md` |
| Public tally seed | `PUBLIC_TALLY.md` |
| Funding checklist | `CLAIM_POOL_FUNDING_CHECKLIST.md` |
| Multisig verification procedure | `PUBLISHER_KEY_MULTISIG.md` (status remains **UNVERIFIED**) |
| Publisher dry-run pack | `PUBLISHER_DRY_RUN.md` (procedure ready; **not** executed as OPEN) |
| Ops readiness board | `OPS_READINESS.md` |
| OPEN gate board | `OPEN_GATE_CHECKLIST.md` (hard-blocks OPEN while pool=0 or multisig UNVERIFIED) |
| Sepolia snapshots | `CHAIN_SNAPSHOT_2026-10-07.md` + `CHAIN_SNAPSHOT_RECHECK_2026-10-07.md` — claim pool **0 MTRN**; caps **0 / 0** |
| Epoch caps draft | `EPOCH_0_CAPS.md` (zeros until pool funded) |
| Bounty draft | `BOUNTY_ANNOUNCEMENT_DRAFT.md` — **NOT OPEN** / CLOSED |

**Network facts (latest recheck):** Ethereum Sepolia; token `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB`; active pool `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059`; pool balance **0 MTRN**; on-chain `latestEpoch` **1**; next publishable index after funding would be **2**. Draft “Epoch 0” is planning-only.

---

## Human-only (required before OPEN)

1. **Fund the claim pool** on Sepolia per `CLAIM_POOL_FUNDING_CHECKLIST.md` (never treat treasury as pool pre-fund), then **republish** absolute caps in `EPOCH_0_CAPS.md` (budget ≤ 5% of pool; beneficiary ≤ 15% of budget).
2. **Verify multisig** (minimum 2-of-3 or equivalent) per `PUBLISHER_KEY_MULTISIG.md` — fill the verification record; status stays **UNVERIFIED** until humans complete it.
3. **Complete publisher dry-run** per `PUBLISHER_DRY_RUN.md` (≥2 of 3 labeled A/B/C approve a *dummy* digest; public note; **NO ROOT** / never call `publishEpoch`).
4. **Clear** every required box on `OPEN_GATE_CHECKLIST.md` / `OPS_READINESS.md`.
5. **Only then** replace the bounty draft with an OPEN notice. Until then the bounty stays **CLOSED**.

Optional (non-blocking): timestamps.org when DNS works; Finney OTS upgrade when the calendar confirms.

---

## Still forbidden

- Calling `publishEpoch` / publishing any Merkle root
- Opening claims or advertising the bounty as OPEN
- Treating treasury balance as claim-pool pre-fund
- Any wallet tx from this documentation pack

Testnet MTRN has **no assumed monetary value**.

## CARVE diagnostics update — 2026-10-07

[CARVE_RESULTS_2026-10-07.md](CARVE_RESULTS_2026-10-07.md) records six bounded CPU jobs: 24 cases, 720 steps, 156 passing interface checks, plus 636 separate artifact/source checks. The rounded wave reporting change is bracketed by requested 0.664/0.665 m/s. Grok and Flipper reviewed supplied measurements; neither independently ran or authenticated them. Rendering and physical accuracy remain unverified.

**Bounty remains CLOSED; publisher control remains UNVERIFIED; recorded human approvals remain 0/3.** This batch did not re-read on-chain funding, change caps, add human approvals, run a publisher dry-run, or clear any OPEN gate. The existing chain snapshots above remain historical evidence at their recorded blocks. Follow the funding, real 2-of-3/MPC, dry-run and OPEN checklist sequence before any opening.
