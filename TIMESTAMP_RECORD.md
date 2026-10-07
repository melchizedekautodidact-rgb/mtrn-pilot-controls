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


## OTS upgrade attempt (2026-10-07T09:14:25Z)

**ots CLI:** installed in local venv (`opentimestamps-client` v0.7.2 via `python3 -m venv`).

**Repair note:** Existing `.ots` files were **Timestamp bodies only** (missing `DetachedTimestampFile` magic header; OpenTimestamps proof file prefix). They deserialized correctly as `Timestamp` for digest `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051` once wrapped with `OpSHA256` + DetachedTimestampFile header (no attestation content invented). After repair, `ots upgrade` was run.

| Proof file | Calendar / path | After upgrade |
|------------|-----------------|---------------|
| `MTRN_Pilot_Controls_Package.md.ots` | alice.btc.calendar.opentimestamps.org | **Bitcoin-anchored** — `BitcoinBlockHeaderAttestation(970307)`; merkle root `a97d0823e10d29c6992ec8f896f942d4c69e5a16388d405641253f6867091b0e`; tx `3bacccc16f0dbc1bc94570fb749f4abe9ee1d64b35f41779848a60871fb65c7d` |
| `stamp_alice_btc_calendar_opentimestamps_org.ots` | alice (same path) | **Bitcoin-anchored** — same attestation height **970307** |
| `stamp_a_pool_opentimestamps_org.ots` | content attested via alice calendar (filename historical) | **Bitcoin-anchored** — height **970307** |
| `stamp_finney_calendar_eternitywall_com.ots` | finney.calendar.eternitywall.com | Still **pending** Bitcoin confirmation (`Calendar … Pending confirmation in Bitcoin blockchain`) |

**`ots verify`:** local Bitcoin node not available in this environment (no `~/.bitcoin` cookie); upgrade path already embeds the Bitcoin block-header attestation for the alice-family proofs.

**timestamps.org recheck (same UTC):** DNS still fails (`gaierror` / temporary failure in name resolution for `timestamps.org` and `ots.timestamps.org`). Leave timestamps.org optional; OpenTimestamps calendars remain the public timestamp channel. Alice-path proofs are now Bitcoin-anchored; finney path remains pending.

## OTS verify + Finney upgrade retry (2026-10-07T09:25:07Z)

**ots CLI:** `/workspace/.venv-ots` (`opentimestamps-client` v0.7.2).

### `ots verify` (Bitcoin-anchored proofs)

All three proofs were verified against target file `MTRN_Pilot_Controls_Package.md` (`-f`). File hash matched expected digest `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`.

| Proof file | `ots verify` result |
|------------|---------------------|
| `MTRN_Pilot_Controls_Package.md.ots` | Digest OK; **exit 1** — no local Bitcoin node (`~/.bitcoin/.cookie` missing; `bitcoin.conf` absent). Attestation present per `ots info`: `BitcoinBlockHeaderAttestation(970307)`, merkle root `a97d0823e10d29c6992ec8f896f942d4c69e5a16388d405641253f6867091b0e`, tx `3bacccc16f0dbc1bc94570fb749f4abe9ee1d64b35f41779848a60871fb65c7d`. |
| `stamp_alice_btc_calendar_opentimestamps_org.ots` | Same: digest OK; exit 1 (no Bitcoin node); same height **970307** / same merkle root / same tx. |
| `stamp_a_pool_opentimestamps_org.ots` | Same: digest OK; exit 1 (no Bitcoin node); same height **970307** / same merkle root / same tx. |

**Representative verify stderr (all three):**
```
Could not connect to Bitcoin node: Cookie file unusable ([Errno 2] No such file or directory: '/home/box/.bitcoin/.cookie') and rpcpassword not specified in the configuration file: '/home/box/.bitcoin/bitcoin.conf'
```

**Independent block-header cross-check (Blockstream API, not a substitute for local-node `ots verify`):** Bitcoin block height **970307** hash `00000000000000000001a7945b5a2467dbcc69e2d95d7f8086f889fdd0d715b8`; reported merkle root **matches** `a97d0823e10d29c6992ec8f896f942d4c69e5a16388d405641253f6867091b0e`; tx `3bacccc1…5c7d` confirmed in that block (`block_time` 1791357890).

### Finney calendar upgrade

```
ots upgrade stamp_finney_calendar_eternitywall_com.ots
→ Calendar https://finney.calendar.eternitywall.com: Pending confirmation in Bitcoin blockchain
→ Failed! Timestamp not complete
```

**Status:** still **pending** (calendar receipt only; not Bitcoin-anchored). Proof file unchanged (291 bytes).

### timestamps.org

`getent hosts timestamps.org` / `ots.timestamps.org`: no A/AAAA (still down / unresolved). Leave optional; OpenTimestamps calendars remain the public timestamp channel.

## Finney OTS upgrade retry (2026-10-07T09:49:16Z)

**ots CLI:** `/workspace/.venv-ots` (`opentimestamps-client` v0.7.2).

```
ots upgrade stamp_finney_calendar_eternitywall_com.ots
→ Calendar https://finney.calendar.eternitywall.com: Pending confirmation in Bitcoin blockchain
→ Failed! Timestamp not complete
```

**Status:** still **pending** (calendar receipt / `PendingAttestation` only; **not** Bitcoin-anchored). Proof file unchanged (291 bytes). Digest still `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`.

Alice-path proofs remain Bitcoin-anchored at height **970307** (tx `3bacccc1…5c7d`). timestamps.org optional; DNS not rechecked in this pass.

## Finney OTS upgrade retry (2026-10-07T10:14:11Z)

**ots CLI:** `/workspace/.venv-ots` (`opentimestamps-client` v0.7.2).

```
ots upgrade stamp_finney_calendar_eternitywall_com.ots
→ Calendar https://finney.calendar.eternitywall.com: Pending confirmation in Bitcoin blockchain
→ Failed! Timestamp not complete
```

**Status:** still **pending** (`PendingAttestation` only; **not** Bitcoin-anchored). Proof file unchanged (291 bytes). Digest still `fb980fcf83b4fa368435f19876fb84b6ea7388d3559bbec2781070cf27d5e051`.

Alice-path proofs remain Bitcoin-anchored at height **970307** (tx `3bacccc1…5c7d`).
