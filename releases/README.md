# Release Artifacts

Actual xHydra Unlock release binaries are published through this repository's
[GitHub Releases](https://github.com/TahaHydra/XHydra-unlock-release/releases), not
committed directly to the git history.

Each published Windows release provides:

- a versioned MSI installer;
- release notes;
- a SHA-256 checksum file; and
- the matching SHA-256 value in the release documentation.

The current public Windows release is **1.2.0**:

- `xHydraUnlock-1.2.0.msi`
- `xHydraUnlock-1.2.0.sha256.txt`

Published SHA-256:

```text
58AE30E6FE170ABB1B5C2F23D91CC255FEE2EF090D231B9AB78A7B0C4B6D8901  xHydraUnlock-1.2.0.msi
```

The MSI is already a complete Windows installer package and is therefore not wrapped
in an additional ZIP archive.

## Integrity and signing

The checksum covers the exact MSI linked from the release. If an artifact ever needs to
be replaced during release preparation, the release notes and checksum must be updated
together so the published binary remains unambiguous.

Starting with 1.2.0, the Windows MSI and the xHydra Unlock programs it installs are
**Authenticode-signed** with a code-signing certificate issued to **Taha Laachari** by
Certum (Asseco Data Systems S.A.), with an RFC 3161 timestamp. Windows shows the
publisher as *Taha Laachari*. Because the certificate is new, SmartScreen may still show
a warning until it has built reputation.

Releases 1.1.1 and earlier were not signed.

The SHA-256 checksum lets users verify that their downloaded file matches the artifact
published here. The signature additionally identifies the publisher.

Only official GitHub Release attachments and links from
[https://xhydra.fr](https://xhydra.fr) should be treated as xHydra Unlock distribution
sources.
