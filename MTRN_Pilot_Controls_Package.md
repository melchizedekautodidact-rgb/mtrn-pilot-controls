# MTRN Testnet Reward Pilot – Controls Package
**Version:** 1.0  
**Scope:** Testnet-only (Sepolia). Fixed supply 1 000 000 000 MTRN. No further minting.  
**Contract assumptions:** WorkEpochClaims has immutable token + publisher addresses; pays only from pre-funded balance; does not evaluate work quality or signatures.  
**Economic reality:** Absent an external paying sponsor, participants receive only testnet tokens with no assumed monetary value.

---

## 1. Acceptance Checklist (Candidate Bounty: 33 d-block cohesive-energy datapoints)

**Must be published publicly before any work begins.**

For each of the 33 datapoints the following must all be true:

1. **Source**  
   - Primary source is a peer-reviewed paper or authoritative handbook.  
   - Full bibliographic citation + persistent identifier (DOI or stable URL) provided.  
   - Exact table number / page / figure / equation location stated so that an independent reader can locate the value in < 60 seconds.

2. **Value**  
   - Numeric value transcribed exactly as published (including any reported significant figures).  
   - Unit stated explicitly and matches the source (or converted with conversion factor shown and justified).

3. **Uncertainty**  
   - Experimental or estimated uncertainty reported exactly as in the source, **or**  
   - Explicit statement “uncertainty not reported in source” with the page/table reference that confirms absence.

4. **Reviewers**  
   - Two reviewers who have declared (and the publisher has verified) that they:  
     - Have no shared institutional affiliation or current funding line with each other or with the worker for this bounty.  
     - Performed their reviews independently and in parallel (not sequential).  
   - Each reviewer signs a short statement confirming the three points above and that they personally inspected the source.

5. **Uniqueness & Deadlines**  
   - Worker has not previously claimed the same datapoint in any earlier epoch.  
   - All evidence submitted before the published deadline for the epoch.

6. **Human acceptance**  
   - Publisher (or designated multi-party signers) has performed a final human review and accepted the package.

Any datapoint failing any item above is rejected. No partial credit.

---

## 2. Publisher Operational Procedure

### Before first epoch
- [ ] Publish this entire Controls Package (or a hash of it) on a public, timestamped channel (e.g. GitHub commit, IPFS, or arXiv-style preprint).  
- [ ] Decide and publish the hard budget cap for Epoch 0 (recommended: ≤ 5 % of currently pre-funded balance).  
- [ ] Decide and publish the single-beneficiary cap (recommended: ≤ 15 % of the epoch budget).  
- [ ] Confirm the publisher key is controlled by a multi-party process (minimum 2-of-3 or equivalent). Single-key operation is a stop condition.

### For every accepted leaf
1. Assemble the full evidence bundle (worker submission + both reviewer statements + source PDFs or screenshots + checklist marks).  
2. Compute `keccak256` of the canonical serialization of the bundle.  
3. **Publish the hash publicly** (same channel as above) **before** including the leaf in any Merkle root.  
4. Only after the hash is public and time-stamped may the leaf be included.

### Before publishing any Merkle root
- [ ] Verify that the sum of all amounts in the epoch ≤ remaining pre-funded balance.  
- [ ] Verify that no single beneficiary exceeds the published single-beneficiary cap.  
- [ ] Update and publish the running public tally (see §4).  
- [ ] Confirm the epoch number has never been used before (immutable sequential counter).  
- [ ] Obtain the required multi-party sign-off.

### After root publication
- Claims may open.  
- Keep the public tally live until the epoch is fully claimed or formally closed.

---

## 3. Hard Caps (Epoch 0 recommendations)

| Control                        | Recommended value                  | Rationale                                      |
|--------------------------------|------------------------------------|------------------------------------------------|
| Epoch 0 total budget           | ≤ 5 % of pre-funded balance        | Limits blast radius of first process bugs      |
| Single beneficiary share       | ≤ 15 % of epoch budget             | Prevents one colluding pair from capturing pot |
| Maximum leaves per epoch       | 33 (exactly the candidate bounty)  | Keeps scope tight for first pilot              |

These numbers may be raised only after a successful independent audit of Epoch 0 and a new public announcement.

---

## 4. Public Running Tally Template

Publish (and keep updated) a simple table:

```
Epoch | Published Root | Total Committed | Remaining Balance | % of Pre-fund Used | Notes
------|----------------|-----------------|-------------------|--------------------|------
0     | 0x...          | X MTRN          | Y MTRN           | Z %                | ...
```

Update within 1 hour of any root publication or material balance change.

---

## 5. Automatic Stop / Abort Triggers

The pilot **must** halt (no further roots published, no further funding) if any of the following occur:

1. Independent post-claim audit finds > 1 falsified, non-reproducible, or materially incorrect source among the 33 datapoints.  
2. Publisher key is observed in use from an unexpected address or after an unexplained delay > 72 hours.  
3. Two reviewers for the same datapoint are later shown to share an undeclared institutional affiliation or funding line.  
4. Any single beneficiary successfully claims > 15 % of an epoch budget.  
5. Published commitments would cause the contract balance to be overdrawn.  
6. Discovery of any collusion, fabricated evidence, or reuse of an epoch number.  
7. Loss of multi-party control over the publisher key (reversion to single-key operation).

Halt is executed simply by refusing to publish further roots and by not sending additional tokens to the contract. No on-chain admin rights are required or assumed.

---

## 6. Independent Reviewer Declaration (template)

```
I, [Full Name], declare that:

- I have no current shared institutional affiliation or funding line with the worker or the other reviewer for this datapoint.
- I performed my review independently and in parallel.
- I personally inspected the cited source at the exact location given.
- The numeric value, unit, and uncertainty (or explicit “not reported”) statement are correctly transcribed.

Signature / date / contact
```

Both declarations must be included in the evidence bundle whose hash is published before the root.

---

## 7. Residual Risks Explicitly Accepted

Even with all of the above controls in place, the following residual risks remain and are accepted for this testnet pilot:

- Publisher multi-party set can still collude.  
- Sophisticated fabrication of sources that pass human review is possible.  
- Sepolia network or gas issues can delay claims.  
- Testnet MTRN has no assumed monetary value.

---

**End of Controls Package v1.0**  
This document itself should be hashed and the hash published before Epoch 0 work begins.
