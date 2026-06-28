# Notes for apsd-design-process

- Source: Python PEP 616, [`removeprefix()` and `removesuffix()`](https://github.com/python/peps/blob/main/peps/pep-0616.rst).
- Strong example: the PEP includes a `Rejected Ideas` section that explicitly compares materially different interface shapes, including expanding `lstrip` and `rstrip`, repeatedly removing prefixes, and raising an exception when no prefix is found.
- Weak contrast: a source-model paraphrase of the same proposal with those alternative designs omitted is a good example of first-idea lock-in.
- Eval text:
  - `design-process-negative-no-alternatives` is a source-model paraphrase of a `removeprefix`-style proposal that refuses to compare alternatives.
  - `design-process-positive-rejected-ideas` is a source-model paraphrase of the actual PEP process.
- APSD interpretation: inferred. The skill maps the PEP's explicit alternative analysis to Ousterhout's `design it twice` guidance.
