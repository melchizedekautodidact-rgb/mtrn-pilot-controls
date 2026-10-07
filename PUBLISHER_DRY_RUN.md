# Publisher dry-run (NO ROOT)

**Status:** Rehearsal only. **DRY-RUN / NO ROOT.**  
**Purpose:** Produce a *dummy* multi-party approval and a *dummy* evidence-bundle hash **without** publishing a Merkle root, opening claims, or calling any on-chain publisher function.

**Scope:** Documentation and off-chain process rehearsal. Sepolia testnet only if humans inspect state; this pack does **not** authorize txs. Testnet MTRN has **no assumed monetary value**.

**Hard stop:** Never call `publishEpoch`, never submit a Merkle root on Sepolia, and never open claims during this dry-run.

Aligns with `02_Publisher_Procedure.md` and `01_Acceptance_Checklist.md`, but every publishable/on-chain step is replaced by a labeled dummy.

## Preconditions (read-only)

Confirm current facts (do not change them in this dry-run):

| Fact | Expected |
|------|----------|
| Claim pool balance | **0 MTRN** (until funded separately) |
| Multisig | **UNVERIFIED** (verification is a separate gate) |
| On-chain `latestEpoch` | **1** (next publishable index after funding = **2**) |
| Bounty | **CLOSED** |
| Package SHA-256 | `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051` |
| Token | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` |
| Pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |

Addresses and snapshot: `CHAIN_SNAPSHOT_2026-10-07.md`. Caps remain 0 until funding: `EPOCH_0_CAPS.md`.

## What this dry-run produces

1. A **dummy evidence-bundle digest** (hash of a clearly labeled dummy payload — not a real leaf).
2. A **dummy multi-party approval** of that digest by ≥2 of 3 labeled signers A/B/C (or equivalent).
3. A **public note** of the dry-run in this repo (commit) or a linked public commit/URL.

It does **not** produce: a published Merkle root, an opened claim window, funded pool movement, or an OPEN bounty.

## Rehearsal steps (DRY-RUN / NO ROOT)

Mark each step as dry-run. Do not invent real signer keys or paste secrets.

### A. Dummy leaf / evidence rehearsal (checklist-aligned)

Mirror `01_Acceptance_Checklist.md` with placeholders only:

- [ ] **DRY-RUN** Assemble a dummy evidence bundle file (e.g. `dry_run_dummy_bundle.md`) containing:
  - Label: `DRY-RUN / NOT A REAL DATAPOINT / NO ROOT`
  - Fake citation fields clearly marked placeholder (no claim of real peer-reviewed acceptance)
  - Dummy worker + two dummy reviewer declaration stubs (labels only; no forged identities as real reviewers)
  - Checklist items marked N/A for dry-run
- [ ] **DRY-RUN** Canonicalize that file (stable encoding) and compute a digest (SHA-256 or keccak256 of the canonical bytes — record which).
- [ ] **DRY-RUN** Record the digest in the table below as `dummy_evidence_bundle_hash`.
- [ ] **STOP** Do **not** treat this hash as a publishable leaf. Do **not** add it to any Merkle tree that will be submitted on-chain.

### B. Dummy publisher procedure (procedure-aligned)

Mirror `02_Publisher_Procedure.md` with explicit NO ROOT:

- [ ] **DRY-RUN** Skip real Pre-Epoch 0 funding/caps publication for this rehearsal (those remain separate human gates).
- [ ] **DRY-RUN** “Publish the hash publicly” → publish the **dummy** digest in a public note (this file’s record table + a repo commit, or linked commit). Wait is optional for dry-run; do not include in a real root.
- [ ] **DRY-RUN** Multi-party sign-off of the **dummy digest only** (next section).
- [ ] **FORBIDDEN** Before any Merkle root checks from the live procedure are **not** executed for a real root here. Do not update live tally as if a root published.
- [ ] **FORBIDDEN** After-root steps (claims may open) — **never** during dry-run.

### C. Dummy multi-party approval (≥2 of 3)

Signers are **labels A/B/C only**. Do not invent or paste private keys, seed phrases, or recovery material.

- [ ] Assign or confirm dry-run labels A/B/C for this rehearsal (may match eventual multisig labels once verified; if multisig still UNVERIFIED, use temporary dry-run labels and say so).
- [ ] Each participating signer records approval of the **same** `dummy_evidence_bundle_hash` (offline note, signed message over the digest string, or equivalent — human custody tooling outside this agent).
- [ ] Collect ≥ **2 of 3** approvals. Record who approved (label only), method, and UTC time in the table below.
- [ ] Confirm no single label alone is treated as sufficient for a **real** root (this dry-run only proves the approval workflow).

### D. Public note

- [ ] Commit an update to this file (or a linked commit) recording the dummy digest + approval tally.
- [ ] Leave bounty **CLOSED**. Do not replace `BOUNTY_ANNOUNCEMENT_DRAFT.md` with OPEN.

## Explicit stop list (never during dry-run)

- Call `publishEpoch` or any equivalent publish/submit-root function on Sepolia
- Submit or broadcast a Merkle root / epoch publication tx
- Open claims or advertise the bounty as OPEN
- Move tokens / fund the pool as part of this dry-run (funding is `CLAIM_POOL_FUNDING_CHECKLIST.md`, separate)
- Paste private keys, mnemonics, or recovery material into the repo
- Invent fake real-world signer identities presented as verified multisig owners

## Success criteria

Dry-run **passes** when all of the following are true:

1. A dummy evidence-bundle digest is recorded and clearly labeled **DRY-RUN / NO ROOT**.
2. ≥ **2 of 3** (or equivalent) labeled signers A/B/C have recorded approval of that **same** dummy digest.
3. A public note of the dry-run exists in this repo or a linked public commit/URL.
4. No Merkle root was published and no claims were opened as part of the rehearsal.

## Record (fill when humans complete the dry-run)

| Field | Value |
|-------|-------|
| Dry-run ID / date (UTC) | — |
| Dummy bundle file | — |
| Digest algorithm | — |
| `dummy_evidence_bundle_hash` | — |
| Signer A approval (yes/no + method) | — |
| Signer B approval (yes/no + method) | — |
| Signer C approval (yes/no + method) | — |
| Approvals counted | — / 3 |
| Public note URL or commit | — |
| On-chain root published? | **must remain NO** |
| Claims opened? | **must remain NO** |
| Bounty status | **CLOSED** |
| Confirmed by | — |

## Related

- Live procedure: `02_Publisher_Procedure.md`
- Acceptance checklist: `01_Acceptance_Checklist.md`
- Multisig gate: `PUBLISHER_KEY_MULTISIG.md`
- Ops board: `OPS_READINESS.md`
- Preflight: `EPOCH_0_PREFLIGHT.md`
- Stop conditions: `03_Stop_Conditions.md`
