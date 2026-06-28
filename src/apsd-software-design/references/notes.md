# Notes for apsd-software-design

This skill does not introduce a new APSD principle. It routes general software-design requests through the existing APSD skills in this repository.

- Router sources:
  - complexity and general-purpose: Python PEP 616, [`removeprefix()` and `removesuffix()`](https://github.com/python/peps/blob/main/peps/pep-0616.rst)
  - deep modules: Go `bufio.Scanner` and Rust commit [`abd15858a1feec5454d5a451f4ba9bdfc0fcd2f5`](https://github.com/rust-lang/rust/commit/abd15858a1feec5454d5a451f4ba9bdfc0fcd2f5)
  - errors and naming: CPython `pathlib.rst` and `threading.rst`
- Eval text:
  - each router eval is a source-model paraphrase of one of those concrete upstream examples;
  - the prompt omits the APSD label on purpose so the router has to pick the right specialized skill from evidence.
