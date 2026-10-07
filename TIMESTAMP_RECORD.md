# Timestamp record — MTRN Pilot Controls Package

**Document:** `MTRN_Pilot_Controls_Package.md`  
**SHA-256:** `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`  
**Submitted (UTC):** 2026-10-07T07:05:15Z

## timestamps.org

Attempted calendar `https://ots.timestamps.org/digest`.  
**Result:** host `timestamps.org` / `ots.timestamps.org` did not resolve (no A/AAAA via system DNS, 1.1.1.1, 8.8.8.8, 9.9.9.9, or dns.google). Site fetch also failed. No proof could be saved *on* timestamps.org from this environment.

timestamps.org documents itself as an OpenTimestamps calendar wrapper (`ots stamp -c https://ots.timestamps.org`). Pending public OTS proofs were therefore submitted to the standard OpenTimestamps calendars below so the hash still has a public calendar receipt while timestamps.org is unreachable.

## OpenTimestamps calendar receipts (pending Bitcoin aggregation)

| Calendar | Proof file | Bytes |
|----------|------------|-------|
| alice.btc.calendar.opentimestamps.org | `MTRN_Pilot_Controls_Package.md.ots` (and `stamp_alice_...ots`) | 172 |
| a.pool.opentimestamps.org | `stamp_a_pool_opentimestamps_org.ots` | 207 |
| finney.calendar.eternitywall.com | `stamp_finney_calendar_eternitywall_com.ots` | 226 |

These `.ots` files are **pending** until the calendars anchor into Bitcoin. Re-upgrade later with `ots upgrade` when confirmations land.

## Verify later

```bash
sha256sum MTRN_Pilot_Controls_Package.md
# expect: fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051
ots verify MTRN_Pilot_Controls_Package.md.ots
```


## GitHub public publication

**Published (UTC):** 2026-10-07T07:17:41Z  
**Repo (public):** https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls  
**Initial commit:** `b5e7bff`  
**Canonical hash file:** `https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls/blob/main/MTRN_Pilot_Controls_Package.sha256`  
**OTS proof:** `https://github.com/melchizedekautodidact-rgb/mtrn-pilot-controls/blob/main/MTRN_Pilot_Controls_Package.md.ots`

## OTS upgrade attempt (2026-10-07T08:30:20Z)

**ots CLI:** not installed in this environment (`ots` / `opentimestamps-client` unavailable). No `ots upgrade` run on `MTRN_Pilot_Controls_Package.md.ots` or companion `stamp_*.ots`.

**Status of proofs:** remain **pending** Bitcoin aggregation (calendar receipts only). Not Bitcoin-anchored in this pass. Re-run `ots upgrade` when the CLI is available and calendars have confirmed.

**timestamps.org recheck (same UTC):** `getent hosts timestamps.org` / `ots.timestamps.org` returned no A/AAAA; `curl` to `https://timestamps.org` and `http://timestamps.org` produced no usable response (host still unreachable). Routine note: leave timestamps.org optional; OTS calendars remain the public timestamp channel.
