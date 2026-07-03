# velodex-data

Benchmark and test fixtures for [velodex](https://github.com/tox-dev/velodex), kept out of the
main repo's history so large wheels do not bloat it.

- `*.json` / `*.html` — real PyPI simple pages (PEP 691 / PEP 503), captured from pypi.org.
- `*.metadata` — real PEP 658 core-metadata documents.
- `wheels/*.whl` — real wheels, served offline by the benchmark's mock upstream with their real
  digests so velodex verifies and caches them exactly as it would against pypi.org.

velodex consumes this repo as a git submodule at `crates/velodex-bench/benches/fixtures`.
