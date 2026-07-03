# velodex-data

Real fixtures for [velodex](https://github.com/tox-dev/velodex) — benchmark and test data kept out
of the main repo's history so large artifacts do not bloat it. velodex consumes this repo as a git
submodule at `crates/velodex-bench/benches/fixtures`.

## Layout

- `pages/` — real PyPI simple index pages captured from pypi.org: PEP 691 JSON (`*.json`) and PEP
  503 HTML (`*.html`).
- `metadata/` — real PEP 658 core-metadata documents (`*.metadata`).
- `wheels/` — real wheel artifacts (`*.whl`), served offline by the benchmark's mock upstream with
  their real digests so velodex verifies and caches them exactly as against pypi.org.

## Adding data

Drop the file in the matching directory (create a new top-level directory for a new kind of
fixture), commit, push, then bump the submodule pointer in velodex. Capture pages with
`curl -H 'Accept: application/vnd.pypi.simple.v1+json' https://pypi.org/simple/<project>/`.
