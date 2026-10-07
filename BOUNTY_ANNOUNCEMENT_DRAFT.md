# DRAFT — MTRN testnet bounty announcement (NOT OPEN)

**Status: CLOSED.** This is a draft for review. Do not solicit work or publish roots until Epoch 0 gates in `EPOCH_0_PREFLIGHT.md` are all green.

## Headline (when opened)

Testnet-only bounty: source-check **33 d-block cohesive-energy datapoints** for the MTRN WorkEpochClaims pilot on **Sepolia**.

## What this is

- Token: MTRN on Sepolia, fixed supply 1,000,000,000, no further minting assumed for this pilot.
- Rewards pay only from a **pre-funded** WorkEpochClaims balance.
- An off-chain publisher verifies receipts, evidence, uniqueness, deadlines, human acceptance, and budget. The contract does **not** judge work quality or signatures.

## What this is not

- **Not** a promise of real-world money. Absent an external paying sponsor, rewards are **testnet MTRN only** with **no assumed monetary value**.
- **Not** open until the controls package hash, multi-party publisher control, and Epoch 0 caps are published.

## Acceptance (summary)

Full checklist: `01_Acceptance_Checklist.md`. Every datapoint needs citation + DOI/URL, exact table/page location, exact value + unit, uncertainty (or explicit not-reported), and **two independent parallel reviewers** with signed declarations.

## Caps (placeholders — replace from `EPOCH_0_CAPS.md`)

- Epoch 0 budget: **TBD** MTRN (≤ 5% of pre-funded balance)
- Single beneficiary: **TBD** MTRN (≤ 15% of Epoch 0 budget)
- Leaves: exactly **33**

## Evidence / process

1. Assemble evidence bundle (worker + 2 reviewer declarations + sources + checklist).
2. Publisher publishes evidence-bundle hash publicly **before** including any leaf in a Merkle root.
3. Multi-party sign-off before every root.
4. Claims open only after root publication.
5. Automatic stop conditions: `03_Stop_Conditions.md`.

## Controls package

- Repo: https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls
- Master SHA-256: `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`
- OpenTimestamps proof: `MTRN_Pilot_Controls_Package.md.ots`

## How to watch for OPEN

When gates clear, this draft will be replaced by an OPEN notice with absolute caps, deadline, and submission channel. Until then, treat any “open bounty” claim as invalid.
