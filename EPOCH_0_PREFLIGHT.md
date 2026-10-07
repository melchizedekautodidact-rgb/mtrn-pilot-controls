# Epoch 0 Preflight

**Status:** Controls package hashed, OpenTimestamps calendars stamped, and on GitHub. Public tally seed published. Publisher dry-run pack and ops readiness board added. Claim pool pre-fund is **0 MTRN**; multisig **unverified**. Bounty stays closed.

## Package integrity

| Item | Value |
|------|-------|
| File | `MTRN_Pilot_Controls_Package.md` |
| Size | 7136 bytes |
| SHA-256 | `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051` |
| Scope | Testnet-only (Sepolia). No assumed monetary value for MTRN. |

Publish this hash (or the whole package) on a public, timestamped channel before any Epoch 0 work or root publication.

### Companion file digests (informational)

| File | SHA-256 |
|------|---------|
| `01_Acceptance_Checklist.md` | `6c0911fd722bb3dffe7f091960e5dc0634656b13642317ec2c8ece1b6b936172` |
| `02_Publisher_Procedure.md` | `efb989bd7cc4c6fb9e9cd6b3942e4734af66d4da1a641b9a01ed4dca934e1698` |
| `03_Stop_Conditions.md` | `3fc29ecb782a2562d8d000a7b2ac13ca920df595af2adfc24caebcae2a35e1d7` |
| `04_Reviewer_Declaration_Template.md` | `2704460a0eaa6347cdd16ca75d4fcb4a6ba44b827163e74346b672b80cc7019a` |
| `05_Public_Tally_Template.md` | `06797ece7b6743b341394b4887cc09c3c09328857027a05e29057e6a94fd9553` |
| `README.md` | `6cd91033ddf903a44fa619381629f4aab266bf7ba4a1068c2b5ec4825d211df6` |

## Human gates (must all pass before opening the 33-datapoint bounty)

Single board: `OPS_READINESS.md`. Master go/no-go before replacing the bounty draft with OPEN: `OPEN_GATE_CHECKLIST.md` (do not mark OPEN while pool=0 or multisig UNVERIFIED). Do not check multisig or caps until humans complete those procedures.

- [x] Controls Package hash submitted to public OpenTimestamps calendars
- [x] Controls Package published on public GitHub: https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls (commit `b5e7bff`) (2026-10-07T07:05:15Z). See `TIMESTAMP_RECORD.md` and `MTRN_Pilot_Controls_Package.md.ots`. Note: timestamps.org DNS currently refuses queries; OTS calendars remain the public timestamp channel.
- [ ] Publisher key is multi-party (min 2-of-3). **UNVERIFIED** as of 2026-10-07 snapshot. Single-key = stop. See verification procedure in `PUBLISHER_KEY_MULTISIG.md`.
- [ ] Epoch budget published (≤ 5% of **claim-pool** pre-fund): **0 MTRN** at snapshot (pool empty; cannot open). Fund per `CLAIM_POOL_FUNDING_CHECKLIST.md`, then republish `EPOCH_0_CAPS.md`.
- [ ] Single-beneficiary cap published (≤ 15% of epoch budget): **0 MTRN** at snapshot
- [ ] Publisher dry-run completed (`PUBLISHER_DRY_RUN.md`) — dummy multi-party approval of a dummy digest; **NO ROOT** / never call `publishEpoch`
- [x] Acceptance checklist published publicly (`01_Acceptance_Checklist.md` in this public repo)
- [x] Public tally page/file ready (`PUBLIC_TALLY.md`)

## Suggested Epoch 0 numbers (fill absolute values once balance is known)

| Control | Rule | Absolute (fill in) |
|---------|------|--------------------|
| Pre-funded balance (claim pool) | Active WorkEpochClaims | **0 MTRN** (block 11861528) |
| Treasury balance | Not pool allocation | 1,000,000,000 MTRN |
| Planning epoch budget | ≤ 5% of claim-pool pre-fund | **0 MTRN** |
| Single beneficiary | ≤ 15% of epoch budget | **0 MTRN** |
| On-chain latestEpoch | Next publishable = 2 | 1 (1/1 claimed) |
| Max leaves | Exactly 33 | 33 (closed) |

## Still forbidden until gates pass

- Publishing any Merkle root
- Opening claims
- Advertising the bounty as paid work with real-world value

## Next after gates

1. Open bounty under the published checklist.
2. For each accepted leaf: assemble bundle → hash → publish hash → wait for timestamp → then include in root.
3. Multi-party sign-off before every root.
4. Halt on any trigger in `03_Stop_Conditions.md`.

## Gate workfiles (this repo)

| Gate | File |
|------|------|
| Multi-party publisher | `PUBLISHER_KEY_MULTISIG.md` |
| Claim pool funding (human) | `CLAIM_POOL_FUNDING_CHECKLIST.md` |
| Epoch 0 absolute caps | `EPOCH_0_CAPS.md` |
| Publisher dry-run (NO ROOT) | `PUBLISHER_DRY_RUN.md` |
| Ops readiness board | `OPS_READINESS.md` |
| OPEN gate checklist | `OPEN_GATE_CHECKLIST.md` |
| Public tally (live seed) | `PUBLIC_TALLY.md` |
| Bounty text (still closed) | `BOUNTY_ANNOUNCEMENT_DRAFT.md` |
| Sepolia snapshot | `CHAIN_SNAPSHOT_2026-10-07.md` |
