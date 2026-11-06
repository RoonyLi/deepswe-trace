# DeepSWE agent traces

This repository preserves sanitized traces and evaluation evidence from DeepSWE experiments. It covers mini-swe-agent, DSH-minimal, Codex and OpenCode. A run is not the same as a unique task. Some runs are retries, diagnostics or interventions. Do not combine their scores without checking `selection` and experiment metadata.

## Contents

- `index.json`: one entry per collected run, with agent, task, reward, selection labels and SHA-256 digests.
- `runs/`: one directory per experiment, task, agent and trial. Each directory has a standard `trajectory.json`, an evidence bundle, metadata and a short README.
- `first10-links.json`: paths for the historical ten-task comparison.
- `evidence.tar.gz`: sanitized copies of available original records. The archive includes per-file original and published SHA-256 hashes, plus redaction categories and counts.

## Scope and limitations

The mini 113-task campaign contains 110 tasks with valid binary rewards, two model runs without a final verifier reward, and one task blocked before model execution. A missing reward is not a zero. Historical DSH captures do not include the complete provider HTTP request and raw response for every call. Separate raw request-capture directories exist locally for some later runs but are not in the standard bundles. A recorded tool result can already have been truncated. Some input, output, path, cloud identifier or address text is replaced to protect credentials and operational details. Original evidence is retained locally and is not included without redaction.

The traces can support step-by-step review. They do not by themselves establish causal effects, identical environments, a model weight revision, or reproducibility of every server response. Historical result selection and experiment interventions are recorded per run; do not compare unlike runs as a controlled experiment.

## Attribution and licensing

Task statements and command outputs may quote upstream projects. Their original licenses and attribution continue to apply. This repository does not assert ownership of upstream code or grant rights beyond the applicable source licenses.

## Browse runs and coverage

- [Human-readable run index](INDEX.md)
- [Selected mini 113-task coverage](mini-113-coverage.json)
- [Redaction policy](REDACTION.md)
- `campaign_group` and `source_relative_job` retain the experiment grouping. A group name is provenance, not proof that runs are directly comparable.
- [Known limitations and verifier caveats](KNOWN_LIMITATIONS.md)

## Trace completeness

[Trace quality inventory](trace-quality.json) records tool-call and observation counts, timestamp coverage, native logs and local request-capture availability. A recorded observation is not proof of execution success; an empty result can have several causes. Raw request-capture directories are separate from the standard evidence bundles. See the publication scope in `KNOWN_LIMITATIONS.md`.

[Local raw request-capture inventory](request-captures-local-inventory.json) records which runs have separate request snapshots and their size. It does not contain the snapshots.
