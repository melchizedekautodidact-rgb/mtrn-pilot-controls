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

## Record (fill when confirmed)

| Field | Value |
|-------|-------|
| Scheme | Unverified (draft: min 2-of-3) |
| Signers (labels only, not secrets) | A/B/C unassigned |
| Confirmed date (UTC) | — |
| Public evidence URL | https://sepolia.etherscan.io/address/0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059#readContract |
| Confirmed by | Balance/accounting only (Codex + PublicNode + Automata 1RPC). Custody/threshold unconfirmed. |

Do not paste private keys, seed phrases, or recovery material into this repo.
