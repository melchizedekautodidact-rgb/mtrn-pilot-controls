# Publisher key — multi-party control checklist

**Gate status:** UNCONFIRMED until every required item below is checked and recorded publicly.  
**Stop condition:** single-key operation of the publisher key (see `03_Stop_Conditions.md`).

## Required (minimum 2-of-3)

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
| Scheme | e.g. 2-of-3 Safe / multisig / offline co-sign |
| Signers (labels only, not secrets) | A: ___ B: ___ C: ___ |
| Confirmed date (UTC) | |
| Public evidence URL | |
| Confirmed by | |

Do not paste private keys, seed phrases, or recovery material into this repo.
