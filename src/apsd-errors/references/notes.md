# Notes for apsd-errors

- Source: CPython pathlib documentation, [`Path.mkdir` and `Path.unlink`](https://github.com/python/cpython/blob/main/Doc/library/pathlib.rst).
- Strong examples: `Path.mkdir(exist_ok=True)` and `Path.unlink(missing_ok=True)` define common filesystem edge cases into the contract instead of forcing every caller to catch and ignore `FileExistsError` or `FileNotFoundError`.
- Weak contrast: caller-side `try/except FileNotFoundError` around ordinary cleanup code is a source-model paraphrase of the burden that `missing_ok` removes.
- Eval text:
  - `errors-negative-catch-and-ignore-unlink` is a source-model paraphrase of the pre-`missing_ok` caller burden.
  - `errors-positive-missing-ok` is a source-model paraphrase of the documented `missing_ok=True` contract.
- APSD interpretation: inferred. The pathlib docs motivate POSIX-like behavior; the skill interprets that as defining away avoidable exceptions.
