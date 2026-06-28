# Notes for apsd-comments

- Source: Go standard library, [`bufio.Scanner`](https://github.com/golang/go/blob/master/src/bufio/scan.go).
- Strong example: the top-level `Scanner` and `SplitFunc` comments explain the abstraction boundary, token contract, and when callers should switch to `bufio.Reader`.
- Weak example: field comments such as `token []byte // Last token returned by split.` are real comments from the same file, but they mostly restate what the identifier and type already say.
- Eval text:
  - `comments-negative-repeats-code` uses a direct quotation of the weak `token` field comment.
  - `comments-positive-boundary-comment` uses a source-model paraphrase of the `Scanner` boundary note that tells callers when `Scanner` stops being the right abstraction.
- APSD interpretation: inferred. The Go project does not cite Ousterhout here; the skill treats the contrast as a real example of high-value interface comments versus low-value repeated-code comments.
