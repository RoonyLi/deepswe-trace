# Publication redaction policy

The public files are derived copies. The original evidence remains in the local evaluation workspace.

Known local credentials and configured endpoints are replaced. Recognizable private-key blocks, common token formats, private network addresses, local user paths and detected cloud identifiers are also masked. Redaction can remove test fixtures that resemble secrets. Each evidence archive contains a manifest with the original file hash, published file hash, redaction categories and counts. Original hashes let the owner compare local source files; they do not disclose original content.

The standard `trajectory.json` is a sanitized copy. The archive contains the same sanitized trajectory and additional available files. Some source JSON or JSONL files were already invalid or incomplete; their source validity is recorded in the archive manifest rather than silently repaired. A missing or empty observation is not inferred to be a successful command.

Automated detection cannot prove that every possible secret or sensitive detail was found. Review the publication package before pushing it to a public repository. Historical DSH records do not include complete upstream HTTP messages for all calls. Redaction and missing records limit exact replay.
