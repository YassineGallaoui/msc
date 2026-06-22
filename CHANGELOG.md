# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0]

### Added

- **Fluid typography utilities** — new `fs-fluid-*` display classes (`fs-fluid-sm`,
  `fs-fluid-md`, `fs-fluid-lg`, `fs-fluid-xl`, `fs-fluid-2xl`) that scale smoothly
  with the viewport via `clamp()` with true linear viewport interpolation between a
  min and max size. Intended for hero/display headings where the fixed `fs-*` scale
  is too rigid.
- `--fs-fluid-min-vw` / `--fs-fluid-max-vw` CSS custom properties (defaults `20`/`96`,
  i.e. 320px–1536px at the 16px base) to override the interpolation breakpoints at
  runtime without recompiling.

### Notes

- No breaking changes — the existing fixed `fs-*` scale and all other utilities are
  unchanged. `--font-size-base` remains the `rem` reference.

## [1.1.0]

- Previous release.
