# Notes for apsd-complexity

- Source: Python PEP 616, [`removeprefix()` and `removesuffix()`](https://github.com/python/peps/blob/main/peps/pep-0616.rst).
- Weak examples: the PEP catalogs standard-library call sites that manually combine `startswith`, slicing, and `replace`, including `find_recursionlimit.py`, `deccheck.py`, `cookiejar.py`, and `test_i18n.py`.
- Better examples: the same PEP shows the simpler replacements with `removeprefix()` and `removesuffix()`, which reduce hidden edge cases and repeated call-site knowledge.
- Eval text:
  - `complexity-negative-manual-prefix-removal` is a direct quotation of the `deccheck.py` current example from the PEP.
  - `complexity-positive-removeprefix` is a direct quotation of the `Arguably further improved` form from the same example.
- APSD interpretation: inferred. The PEP frames the change as readability and correctness; this skill reads the repeated hand-rolled variants as cognitive load and obscurity.
