# Security Policy

## Supported versions

The current public Windows release is **xHydra Unlock 1.2.0**.

Security fixes are expected to target the current release line. If you are running an
older Windows companion, reproduce the issue on the latest public version when it is
safe to do so.

## Reporting a security issue

Please do **not** post a security issue publicly when doing so could expose an active
vulnerability, working exploit, sensitive data, or information that could put users at
risk.

A dedicated official security contact is being configured. Until it is published, use
the [official xHydra website](https://xhydra.fr) to find current official contact
information. Do not send vulnerability details to an email address or social account
that is not confirmed through an official xHydra channel.

When reporting an issue privately, include only what is needed to reproduce and assess
it:

- the affected xHydra Unlock version;
- the Windows version/build and mobile platform/version when relevant;
- a concise description of the security impact;
- reproducible steps or a minimal proof of concept; and
- relevant logs with credentials, identifiers, keys, tokens, and personal information
  removed.

Do not include Windows passwords, private signing keys, pairing secrets, credential
blobs, purchase tokens, or other secrets in a report.

## Security design summary

The current product is designed around a local-first trust model:

- the core unlock path does not use an xHydra cloud relay;
- pairing is local-network based;
- private VPN operation is opt-in rather than enabled by default;
- Public Windows network profiles are blocked;
- the paired PC is authenticated using pinned TLS identity;
- phone requests use signed, fresh challenges with replay protection;
- privileged phone actions require OS-level device authentication;
- Windows service / Credential Provider IPC is restricted and identity-checked;
- Windows-session targeting is validated before credential delivery; and
- the Windows credential is encrypted locally on the PC and is not stored on the phone.

These properties describe the intended current design; they are not a substitute for
responsible vulnerability reporting if you find a way to bypass them.

## Release integrity

Official Windows release artifacts and SHA-256 checksums are published through this
repository's [GitHub Releases](https://github.com/TahaHydra/XHydra-unlock-release/releases).

For **xHydra Unlock 1.2.0**:

```text
58AE30E6FE170ABB1B5C2F23D91CC255FEE2EF090D231B9AB78A7B0C4B6D8901  xHydraUnlock-1.2.0.msi
```

Verify a downloaded installer with:

```powershell
Get-FileHash .\xHydraUnlock-1.2.0.msi -Algorithm SHA256
```

### Authenticode status

Starting with 1.2.0, the Windows MSI and the xHydra Unlock programs it installs are
**Authenticode-signed** with a code-signing certificate issued to **Taha Laachari** by
Certum (Asseco Data Systems S.A.), with an RFC 3161 timestamp. You can check it in the
MSI's **Properties › Digital Signatures**, or with:

```powershell
Get-AuthenticodeSignature .\xHydraUnlock-1.2.0.msi
```

The status must be **Valid** and the signer `CN=Taha Laachari`. Because the certificate
is new, Windows SmartScreen may still show a warning until it has built reputation.

Releases 1.1.1 and earlier were not signed; for those, the SHA-256 checksum is the only
integrity check.

Only download xHydra Unlock from the official xHydra website or this repository's
GitHub Releases.
