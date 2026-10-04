# Release Artifacts

Actual xHydra Unlock release binaries are published through this repository's
[GitHub Releases](https://github.com/TahaHydra/XHydra-unlock-release/releases), not
committed directly to the git history.

Each published Windows release provides:

- a versioned MSI installer;
- release notes;
- a SHA-256 checksum file; and
- the matching SHA-256 value in the release documentation.

The current public Windows release is **1.1.1**:

- `xHydraUnlock-1.1.1.msi`
- `xHydraUnlock-1.1.1.sha256.txt`

Published SHA-256:

```text
9F21EF037BCB6FEE7B4532F71B8A130F297BDAED5CCDF8661808A810E7FAA953  xHydraUnlock-1.1.1.msi
```

The MSI is already a complete Windows installer package and is therefore not wrapped
in an additional ZIP archive.

## Integrity and signing

The checksum covers the exact MSI linked from the release. If an artifact ever needs to
be replaced during release preparation, the release notes and checksum must be updated
together so the published binary remains unambiguous.

The 1.1.1 Windows artifact is currently **not signed with a publicly trusted
Authenticode certificate**. Windows SmartScreen may therefore display an **Unknown
publisher** warning.

SHA-256 verifies integrity only; it is not publisher authentication. The checksum
allows users to verify that their downloaded file matches the artifact published here,
but a checksum does not substitute for publicly trusted Authenticode signing.

Only official GitHub Release attachments and links from
[https://xhydra.fr](https://xhydra.fr) should be treated as xHydra Unlock distribution
sources.
