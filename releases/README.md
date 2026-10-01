# Release Artifacts

Actual xHydra Unlock release binaries are published through this repository's
[GitHub Releases](https://github.com/TahaHydra/XHydra-unlock-release/releases), not
committed directly to the git history.

Each published Windows release provides:

- a versioned MSI installer;
- release notes;
- a SHA-256 checksum file; and
- the matching SHA-256 value in the release documentation.

The current public Windows release is **1.1.0**:

- `xHydraUnlock-1.1.0.msi`
- `xHydraUnlock-1.1.0.sha256.txt`

Published SHA-256:

```text
C98BDF5E4F5D7DC2EB69C8E66ED458FD815C74559920889033D122F3CEC78DE1  xHydraUnlock-1.1.0.msi
```

The MSI is already a complete Windows installer package and is therefore not wrapped
in an additional ZIP archive.

## Integrity and signing

The checksum covers the exact MSI linked from the release. If an artifact ever needs to
be replaced during release preparation, the release notes and checksum must be updated
together so the published binary remains unambiguous.

The 1.1.0 Windows artifact is currently **not signed with a publicly trusted
Authenticode certificate**. Windows SmartScreen may therefore display an **Unknown
publisher** warning.

The SHA-256 checksum allows users to verify that their downloaded file matches the
artifact published here, but a checksum does not substitute for publicly trusted
Authenticode signing.

Only official GitHub Release attachments and links from
[https://xhydra.fr](https://xhydra.fr) should be treated as xHydra Unlock distribution
sources.
