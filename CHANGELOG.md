# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [v1.0.1] - 2025-11-04

### Added

- Self-test workflow (`.github/workflows/citation-sync.yml`) to automatically test the action on this repository
- Documentation for moving tags and tag trigger patterns in README

### Changed

- **Improved tag trigger pattern** to prevent double-triggering when pushing both version tags and moving tags
  - Updated from `'v*'` to `'v[0-9]+.[0-9]+.[0-9]+*'` (excludes moving tags like v1, v2)
  - This prevents race conditions when pushing both specific tags (v1.0.0) and moving tags (v1) together
- Updated all examples to use `actions/checkout@v5` instead of `v4`

### Fixed

- Prevented potential race conditions from multiple workflow runs when pushing multiple tags simultaneously

## [v1.0.0] - 2025-11-03

### Added

- Initial release of Citation Sync Action
- Automatic CITATION.cff version and date synchronization with Git tags
- Support for two update modes: 'increment' and 'match'
- Configurable version tag prefix and format
- Support for pre-release versions (e.g., v1.0.0-beta.1)
- Auto-detection of default branch
- CITATION.cff validation with rollback on errors
- Field uniqueness validation (version and date-released)
- Comprehensive error messages with actionable suggestions
- GitHub Actions annotations for errors, warnings, and notices

### Documentation

- Comprehensive README with usage examples
- Detailed OVERVIEW of action purpose and process
- Complete TODO/implementation plan
- Contributing guidelines
- Code of Conduct
- Security policy
- MIT License

[v1.0.1]: https://github.com/Adamtaranto/citation-sync-action/compare/v1.0.0...v1.0.1
[v1.0.0]: https://github.com/Adamtaranto/citation-sync-action/releases/tag/v1.0.0
