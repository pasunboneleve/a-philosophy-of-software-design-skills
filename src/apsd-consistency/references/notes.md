# Notes for apsd-consistency

- Source: CPython threading documentation, [`threading`](https://github.com/python/cpython/blob/main/Doc/library/threading.rst).
- Weak examples: the deprecated aliases `activeCount`, `currentThread`, and `isSet` preserve older conventions inside a module whose current API uses `active_count`, `current_thread`, and `is_set`.
- Better examples: the snake_case forms align with modern Python naming conventions and let the module present one primary pattern.
- Eval text:
  - `consistency-negative-mixed-threading-names` is a source-model paraphrase of the mixed alias surface documented in `threading.rst`.
  - `consistency-positive-snake-case-primary` is a source-model paraphrase of the documented primary spellings.
- APSD interpretation: inferred. CPython documents the aliases mainly for compatibility; this skill uses them as a concrete example of why one concept should have one main convention.
