# Publisher key — multi-party control checklist

**Gate status:** **UNVERIFIED** as of chain snapshot 2026-10-07 (block 11,861,528).  
**Stop condition:** single-key operation of the publisher key (see `03_Stop_Conditions.md`).

## Snapshot finding

- Minimum 2-of-3 (or equivalent) remains a **draft** publisher-control requirement only.
- No actual deployed threshold/configuration has been confirmed.
- Signer labels A/B/C are **unassigned/unverified**.
- Current publisher is the existing treasury wallet; no multisig signer roster is established in reviewed records.
- Current publisher code is an **EIP-7702** delegation indicator; it does **not** establish a multisig threshold.
- Public evidence (pool readContract): https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract

Details: `CHAIN_SNAPSHOT_2026-10-07.md`.

## Required (minimum 2-of-3) — still open

- [ ] Publisher role uses a multi-party process (threshold ≥ 2-of-3 or equivalent)
- [ ] At least three distinct keyholders / devices / signers identified
- [ ] No single person can publish a Merkle root alone
- [ ] Key ceremony notes retained offline (who, when, what hardware/software)
- [ ] Emergency pause procedure agreed: refuse further roots + do not fund further epochs
- [ ] Public statement of multi-party control published (commit, gist, or signed note)

## Optional hardening

- [ ] Geographic / org diversity among signers
- [ ] Hardware wallets or equivalent for signing material
- [ ] Documented rotation / replacement process for a lost signer
- [ ] Dry-run: produce a dummy multi-party approval without publishing a real root

## Verification procedure

Humans must confirm **real multi-party control** before this gate can pass. Keep status **UNVERIFIED** until the record table below is filled with evidence.

### What counts

Confirm one of the following (or an equivalent documented scheme):

1. **Safe / Gnosis Safe** (or similar) with on-chain threshold ≥ 2-of-3 for the publisher role, with distinct owners visible on a public explorer or Safe UI share link.
2. **Documented 2-of-3 (or higher)** multi-party process with named signer labels A/B/C, ceremony notes offline, and a public statement of the scheme + threshold.
3. **Equivalent** threshold control where no single party can publish a Merkle root alone, with public evidence of the configuration.

### What does NOT count

- **EIP-7702 alone** (delegation indicator on the treasury/publisher account does not establish a multisig threshold).
- **Agent quorum** or automated multi-agent agreement.
- **Enrollment-root thresholds** or other draft policy text without deployed/operated multi-party signing.
- Unfilled draft requirements in this file or the Controls Package.

### How to verify (human steps)

1. Identify the actual publisher control surface (Safe address, hardware ceremony, or documented multi-party process).
2. Confirm threshold ≥ 2-of-3 (or equivalent) and that at least three distinct signers exist.
3. Confirm no single person can publish a root alone (dry-run if needed).
4. Collect a public evidence URL (Safe UI, explorer owners page, signed public statement, or commit).
5. Fill the verification record table below with scheme, signer labels A/B/C (**no secrets**), evidence URL, and confirmed date.
6. Only then check the required boxes above and change gate status from UNVERIFIED.

## Record (fill when confirmed)

| Field | Value |
|-------|-------|
| Scheme | Unverified (draft: min 2-of-3) |
| Signers (labels only, not secrets) | A/B/C unassigned |
| Confirmed date (UTC) | — |
| Public evidence URL | https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract |
| Confirmed by | Balance/accounting only (Codex + PublicNode + Automata 1RPC). Custody/threshold unconfirmed. |

### Verification record (humans fill; keep UNVERIFIED until complete)

| Field | Value |
|-------|-------|
| Scheme (Safe / Gnosis / documented 2-of-3 / equivalent) | — |
| Signer label A | — |
| Signer label B | — |
| Signer label C | — |
| Evidence URL | — |
| Confirmed date (UTC) | — |
| Gate status | **UNVERIFIED** |

Do not paste private keys, seed phrases, or recovery material into this repo.
