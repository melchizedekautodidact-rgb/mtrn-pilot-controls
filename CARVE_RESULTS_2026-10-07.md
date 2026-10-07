# CARVE rounded wave reporting check — 2026-10-07

Six fresh CARVE CPU jobs completed **24 cases and 720 steps**. All **156 frozen interface checks** passed. A separate artifact/source verifier passed **636 checks with zero failures**. This result checks the captured model's diagnostics and reporting rules; it does not establish physical accuracy.

## Measured diagnostics

Both repetitions produced the same rounded treatment readouts at body/gust time 0.5000000000000007 seconds. Each job used a fresh zero-wind control and treatment, 30 steps per case, repeated twice. Weather was clear, rain was zero, the calendar was fixed at 1791392400000 milliseconds, and captured controls, initial baselines and clocks matched across the six jobs. Requested fractional wind values were verified in the actuator traces.

| Requested mean (m/s) | Rounded mean (m/s) | Rounded gust (m/s) | Rounded wave parameter (m) |
|---:|---:|---:|---:|
| 0.599 | 0.60 | 0.80 | 0.0000 |
| 0.600 | 0.60 | 0.81 | 0.0000 |
| 0.601 | 0.60 | 0.81 | 0.0000 |
| 0.664 | 0.66 | 0.89 | 0.0000 |
| 0.665 | 0.67 | 0.89 | 0.0001 |
| 0.670 | 0.67 | 0.90 | 0.0001 |

The requested **0.664/0.665 m/s** pair brackets a **rounded reporting change** from 0 to 0.0001 m. The exact mathematical or physical onset was not measured. Raw mean wind and raw wave values were not retained; source-derived predictions remain separate from observations. Mean and wave fields alias at 0.599/0.600/0.601 m/s, while gust fields can differ.

Repetitions use the same authored noise and are not independent statistical samples. WebGL and animation frames were suppressed; the visual wave clock stayed at zero. Rendered waves, physical accuracy, and full-state determinism remain unverified. The frozen source and runner were unchanged; the active original source was untouched. These were direct local broker jobs, not compact Flipper proposal imports or model-authenticated requests.

## Model review and runtime

Grok and Flipper reviewed the supplied measurements through supervised browser exchanges. Their returned JSON is included in [the public summary](CARVE_WAVE_ONSET_2026-10-07.json). Neither independently executed or authenticated the measurements. Grok's page exposed no model version; Flipper reported Haiku 4.5 in its UI. Grok received one request. Flipper received two requests, including one formatting correction after its single-line input removed table line breaks; only the corrected exchange supports completion.

A local bounded CPU executor completed these jobs. Automatic provider connections, continuous autopilot, and a hosted runtime have not been established. A private cloud backup is storage, not a running service.

## Gate status

**Bounty CLOSED. Publisher control UNVERIFIED. Recorded human approvals 0/3.** Model reviews do not count as publisher approvals or independent human reviewers. This batch added no funding evidence, signing, chain operations, or scientific acceptance. It did not recheck live chain state.

The next gate steps remain: fund the active Sepolia claim pool and verify the resulting balance; republish absolute caps from that non-zero balance; establish real 2-of-3/MPC control of publisher `0xc10Fe9EAa90A64d59968a7b79Eb09e0AbA3891D9`; complete the human publisher dry-run; then open only after [OPEN_GATE_CHECKLIST.md](OPEN_GATE_CHECKLIST.md) is entirely green. Treasury balance and AI agreement cannot clear those gates. See [STATUS.md](STATUS.md), [CLAIM_POOL_FUNDING_CHECKLIST.md](CLAIM_POOL_FUNDING_CHECKLIST.md), [PUBLISHER_KEY_MULTISIG.md](PUBLISHER_KEY_MULTISIG.md) and [PUBLISHER_DRY_RUN.md](PUBLISHER_DRY_RUN.md).

## Artifact bindings and evidence limits

Public summary: [CARVE_WAVE_ONSET_2026-10-07.json](CARVE_WAVE_ONSET_2026-10-07.json); raw UTF-8 SHA-256 `6a9e68975393f2c828e77af32143c2ef8e20b6d4ff97c2ef2699d7f877fd9a89`.

The following SHA-256 values bind privately retained raw artifacts. Those artifacts, the full source, and UI captures are not published in this update. These hashes are identifiers, not independently reproducible public execution proof or authenticated provider signatures.

| Private artifact binding | Raw SHA-256 |
|---|---|
| frozenSourceSHA256 | `a3113cb416b225bb267bf9a95f5e69bd603ae996651c500183cccbf8044c04c4` |
| predeclaredPlanRawSHA256 | `e21b17b5b6c636831b8e7d27c8e8589cf2536817c0d802b5d628be6e01f7dfcd` |
| validationRawSHA256 | `2b135b3544c662b978731afaed89933445182d209c6732d5c9c75d4d2388d906` |
| completionRawSHA256 | `24ace8378b96e2529151857a3e4cb791f5dee9eecc7404bd63f96111c2326483` |
| safeFeedbackRawSHA256 | `4e109cce4033f6cf0341ad128fada7508b2af77c683883d53ae223db50eddd64` |
| jobIndexRawSHA256 | `856e5e4f06bbe1bfeb3b65f00583a591426b1ec605ab2faf6b154b8aed421f70` |

This update leaves the original controls package and its timestamped bytes unchanged. Testnet MTRN has no assumed monetary value.
