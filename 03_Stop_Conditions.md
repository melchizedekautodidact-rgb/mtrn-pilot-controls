# Automatic Stop / Abort Triggers

Pilot **halts immediately** (no further roots, no further funding) on any of:

1. Independent audit finds > 1 falsified / non-reproducible / materially incorrect source among the 33.
2. Publisher key used from unexpected address or after unexplained delay > 72 h.
3. Two reviewers on same datapoint share undeclared affiliation or funding line.
4. Any beneficiary claims > 15 % of an epoch budget.
5. Published commitments would overdraw contract balance.
6. Evidence of collusion, fabricated evidence, or epoch-number reuse.
7. Loss of multi-party control (reversion to single-key operation).

**Execution of halt:** simply refuse to publish further roots and do not send additional tokens. No on-chain admin rights required.
