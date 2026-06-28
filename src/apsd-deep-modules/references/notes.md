# Notes for apsd-deep-modules

- Positive source: Go standard library, [`bufio.Scanner`](https://github.com/golang/go/blob/master/src/bufio/scan.go).
- Positive reading: `Scanner` exposes a small interface (`Scan`, `Text`, `Bytes`, `Err`) while hiding buffering, tokenization, growth limits, and sentinel-error handling.
- Negative source: Rust language project commit [`abd15858a1feec5454d5a451f4ba9bdfc0fcd2f5`](https://github.com/rust-lang/rust/commit/abd15858a1feec5454d5a451f4ba9bdfc0fcd2f5), `Simplify API of solver a bit`.
- Negative reading: the pre-change `evaluate_root_goal` API forced ordinary callers to pass `GenerateProofTree` and receive an optional proof-tree payload even when they only wanted the common result, until the commit split the specialized path into `evaluate_root_goal_for_proof_tree`.
- Eval text:
  - `deep-modules-negative-proof-tree-parameter` is a source-model paraphrase of the Rust API before that commit.
  - `deep-modules-positive-hidden-scanner-state` is a source-model paraphrase of the Go `Scanner` interface and docs.
- APSD interpretation: inferred. Neither project uses Ousterhout's vocabulary explicitly.
