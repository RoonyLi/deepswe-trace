# Known limitations

## 113-task mini-swe-agent campaign

The selected historical campaign has 110 tasks with valid recorded binary rewards. Two model runs have traces and patches but no final verifier reward because verification timed out. One task was blocked before model execution. The unscored and blocked tasks must not be counted as zero. See `mini-113-coverage.json`.

## Runs are not interchangeable

The repository includes the historical first-ten selection, other harnesses, retry runs and intervention or control runs. A run count is not a task count. Use the selection labels, experiment and campaign group before comparing results. An observed score difference does not by itself establish the effect of one harness strategy.

## Historical trace capture

The standard trajectories record available agent actions and observations. Historical DSH records do not contain complete outgoing model request bodies and raw provider responses for every step. Tool output may already be truncated before it is recorded. ArkType DSH step 338 has an observation record with empty content; its execution result is unknown. A model completion status, a git commit, an extracted patch and a passing verifier are separate facts.

## Historical Vulture verifier IDs

One first-ten DSH Vulture result records four P2P test IDs as missing. The original XML contains passed tests for the corresponding parameters under different generated IDs. This is consistent with inserting three keys at the start of the parameterized defaults and with the verifier's exact ID matching. The historical score remains unchanged. Thirteen F2P tests still failed; the ID issue does not make the run a pass.

## Redaction and access

Public files are sanitized copies. The local originals and their hashes are retained separately. The archive manifests record redaction counts and source/publication hashes. A redacted value cannot be reconstructed from the public copy. Automatic scanning reduces but cannot eliminate disclosure risk. Review the package before publication.

The artifacts may contain excerpts from third-party software. The respective upstream licenses and attribution apply. This repository does not grant rights it does not own.

## Automated completeness check

The 267 standard trajectories contain 74,914 tool calls and 74,979 observation records. A basic call-ID check found 22 calls without a matching observation ID in the same step; 8 observation records have empty content. Extra observation records and positional association mean these counts are not a proof that a particular command failed or did not execute. They are review flags. The per-run counts are in `trace-quality.json`.

There are 87 runs with separate raw request-capture directories in the local workspace. Those capture directories are not included in the standard evidence bundles. `requests.jsonl` contains request metrics, not necessarily full request or response bodies. The inclusion status is explicit in the per-run quality record.
