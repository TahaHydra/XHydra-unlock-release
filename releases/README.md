# Release Artifacts

Actual xHydra Unlock release binaries are published through this repository's
[GitHub Releases](https://github.com/TahaHydra/XHydra-unlock-release/releases), not
committed directly to the git history.

Each published release identifies its version and provides release notes and SHA-256
checksums alongside its official Windows artifacts. The current Windows companion is
published as an MSI, which is already a complete installer package and is not wrapped
in a second ZIP archive. The checksum always covers the exact file linked for download.
When an artifact is refreshed during release preparation, its release notes and
checksum are updated together so the current binary remains unambiguous.
