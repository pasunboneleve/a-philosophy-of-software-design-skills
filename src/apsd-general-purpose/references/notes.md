# Notes for apsd-general-purpose

- Source: Python PEP 616, [`removeprefix()` and `removesuffix()`](https://github.com/python/peps/blob/main/peps/pep-0616.rst).
- Strong example: the accepted API adds two small methods that cover a recurring adjacent use case without forcing every caller to spell out slicing or regular expressions.
- Weak examples:
  - overspecific: the standard-library call sites listed in the PEP each hand-roll their own prefix or suffix removal.
  - overgeneral: the `Rejected Ideas` section explains why expanding `lstrip` and `rstrip` into tuple-accepting, repeatedly applied prefix removers would be more consistent on paper but worse for the ordinary case.
- Eval text:
  - `general-purpose-negative-hand-rolled-prefix` is a direct quotation of the `find_recursionlimit.py` current example.
  - `general-purpose-negative-overgeneralized-lstrip` is a source-model paraphrase of the rejected iterable-based `lstrip(('foo',))` API.
- APSD interpretation: inferred. The PEP argues from readability and discoverability; the skill treats the accepted design as the generality sweet spot.
