# Notes for apsd-naming

- Source: CPython threading documentation, [`threading`](https://github.com/python/cpython/blob/main/Doc/library/threading.rst).
- Weak examples: compatibility aliases such as `currentThread` and `isSet` keep older spellings alive even though the clearer, convention-preserving names are `current_thread` and `is_set`.
- Strong examples: `current_thread` says what object is returned, and `is_set` uses predicate form for a boolean query.
- Eval text:
  - `naming-negative-camelcase-threading-aliases` is a source-model paraphrase of the deprecated alias surface.
  - `naming-positive-threading-predicates` is a source-model paraphrase of the current primary names.
- APSD interpretation: inferred. The docs present the aliases for migration, while the skill uses the pair to illustrate obvious, expectation-preserving naming.
