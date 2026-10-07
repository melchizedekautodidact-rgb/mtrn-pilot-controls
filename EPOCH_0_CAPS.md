# Epoch 0 hard caps (to publish)

**Status:** DRAFT numbers until pre-funded balance is filled and this file is committed as the published caps.  
**Rules from Controls Package v1.0:** Epoch 0 budget ≤ 5% of pre-funded balance; single beneficiary ≤ 15% of epoch budget; max leaves = 33.

## Absolute caps (fill balance, then compute)

| Control | Rule | Absolute |
|---------|------|----------|
| Pre-funded balance | On-chain / treasury reading | _____ MTRN |
| Epoch 0 total budget | ≤ 5% of pre-funded | _____ MTRN |
| Single-beneficiary cap | ≤ 15% of Epoch 0 budget | _____ MTRN |
| Maximum leaves | Exactly 33 | 33 |

### Worked example (replace with real balance)

If pre-funded balance = **B** MTRN:

- Epoch 0 budget ≤ `0.05 × B`
- Single beneficiary ≤ `0.15 × (Epoch 0 budget)` ≤ `0.0075 × B`

## Public tally seed (Epoch 0)

Copy into the live tally once caps are published:

```
Epoch | Published Root | Total Committed | Remaining Balance | % of Pre-fund Used | Notes
------|----------------|-----------------|-------------------|--------------------|------
0     | (none yet)     | 0 MTRN          | B MTRN           | 0 %                | Caps published; bounty not open
```

## Still closed

Do not open the 33-datapoint bounty until this file has real absolute numbers **and** `PUBLISHER_KEY_MULTISIG.md` is confirmed.
