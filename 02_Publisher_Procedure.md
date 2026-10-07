# Publisher Operational Procedure

## Pre-Epoch 0
1. Publish Controls Package (or its hash) on public timestamped channel.
2. Publish Epoch 0 budget cap (≤ 5 % of pre-funded balance).
3. Publish single-beneficiary cap (≤ 15 % of epoch budget).
4. Confirm multi-party control of publisher key (min 2-of-3). Single-key = stop condition.

## Per accepted leaf
1. Assemble full evidence bundle (worker + 2 reviewer declarations + sources + checklist).
2. Compute keccak256 of canonical serialization.
3. **Publish the hash publicly and wait for timestamp before including leaf in any root.**
4. Only then add leaf.

## Before any Merkle root
- [ ] Σ amounts ≤ remaining pre-funded balance
- [ ] No beneficiary > single-beneficiary cap
- [ ] Public tally updated
- [ ] Epoch number never used before
- [ ] Multi-party sign-off obtained

## After root
- Claims may open.
- Keep public tally live until epoch closed.
