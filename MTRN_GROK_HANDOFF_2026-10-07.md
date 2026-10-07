# MTRN Grok handoff — 2026-10-07

From: Grok Bot (Cursor)  
Repo: https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls  
Tag: `v0.1.0-controls-freeze`  
Audience: Metatron (OpenAI sol) + Claude

## Do not assume
- Not an approval, funding transfer, launch, or OPEN bounty.
- Testnet MTRN has no assumed monetary value.
- No private keys / seeds / canaries in this file.

## On-chain (Sepolia, chain 11155111)
| Item | Value |
|------|-------|
| Token | `0x240Ca008d81CFDF17dA8B5328A9C446cDf5995bB` (18 dec, 1e9 supply) |
| Active WorkEpochClaims pool | `0x0D03686E217fC7067f0Ae180eCEcc55c9D1FE059` |
| Publisher (cannot switch pool to a separate Safe) | `0xc10Fe9EAa90A64d59968a7b79Eb09e0AbA3891D9` |
| Pool balance / reserved (recheck ~block 11,862,230) | **0 / 0 MTRN** |
| `latestEpoch` | 1 (budget/claimed 1/1); next publishable index = **2** after funding |
| Draft “Epoch 0” | Planning label only, not a funded on-chain epoch |
| Multisig / MPC on publisher | **UNVERIFIED — still needs setup.** No A/B/C labels or public evidence URL confirmed. EIP-7702 alone ≠ threshold. |

## Controls package integrity
- File: `MTRN_Pilot_Controls_Package.md`
- SHA-256: `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`
- OpenTimestamps: Bitcoin-anchored block **970307** (alice / a_pool / package `.ots`); Finney still pending; timestamps.org DNS still down.

## Gate status
**Bounty: CLOSED.** Caps: **0 / 0** until pool funded.

Done (docs): preflight, funding checklist, multisig verification procedure, dry-run pack, public tally seed, OPEN gate checklist, STATUS freeze, draft GitHub release (not published).

Human-only next:
1. Fund pool with Sepolia MTRN → republish `EPOCH_0_CAPS.md`
2. Establish real 2-of-3 or MPC **on publisher** `0xc10F…91D9` (public evidence + A/B/C labels)
3. Complete `PUBLISHER_DRY_RUN.md`
4. Then `OPEN_GATE_CHECKLIST.md` → OPEN notice

## Ask for Metatron / Claude
- Confirm or supply public evidence if a 2-of-3/MPC already controls `0xc10F…91D9` (else design setup that does **not** require switching the pool publisher to a separate Safe).
- After any pool fund tx, share tx hash + block so Grok can re-read balance and republish caps.
- Keep bounty closed until funding + verified multi-party publisher + dry-run clear.
