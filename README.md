![xHydra Unlock — Your phone is the key. Local only, with no cloud account or telemetry.](assets/xhydra-unlock-banner.png)

# xHydra Unlock Releases

This is the official public binary-release repository for **xHydra Unlock**. It is the
authoritative location for published Windows binaries, release notes, and SHA-256
checksums.

The xHydra Unlock source code is currently private. This repository intentionally
contains release information and distribution artifacts only; it does not contain the
private product source.

## About xHydra Unlock

xHydra Unlock is a Windows 10 and Windows 11 companion application that lets you approve
a Windows unlock from an iPhone or Android phone. It is local-network only by default;
an existing pairing can optionally use a trusted private VPN when the option is enabled
independently on both the PC and that phone.

Its security model includes:

- local-first operation with no cloud relay;
- strict LAN-only behavior by default, with explicit two-sided private VPN opt-in;
- no xHydra cloud account;
- no telemetry;
- biometric approval required for every unlock;
- hardware-protected signing keys on supported phones;
- TLS public-key pinning to identify the paired PC;
- fresh signed challenges and replay protection; and
- a Windows credential that remains encrypted locally on the PC and is never stored on
  the phone.

## Official links

- Website: [xhydra.fr](https://xhydra.fr)
- Product page: [xHydra Unlock](https://xhydra.fr/products/xhydra-unlock)
- Feedback: [Report a problem or suggest a feature](https://github.com/TahaHydra/XHydra-unlock-release/issues/new/choose)

## Beta feedback

Android is being tested in a closed Google Play beta. Testers can use this
repository's public issues to report real problems and suggest improvements.
Include app versions, reproduction steps, and expected versus actual behavior.
Never attach passwords, pairing QR codes, private keys, purchase tokens, credential
blobs, or unredacted logs. For vulnerabilities, follow [SECURITY.md](SECURITY.md).

The next Windows and Android companion release is in development, including guided
setup and separately authorized PC controls. These features are not part of the
Windows 1.0.0 download below; release notes will identify when they become available.

## Releases

### xHydra Unlock 1.0.0

- [Download the Windows MSI](https://github.com/TahaHydra/XHydra-unlock-release/releases/download/v1.0.0/xHydraUnlock-1.0.0.msi)
- [Read the release notes](https://github.com/TahaHydra/XHydra-unlock-release/releases/tag/v1.0.0)
- [Download the SHA-256 checksum file](https://github.com/TahaHydra/XHydra-unlock-release/releases/download/v1.0.0/xHydraUnlock-1.0.0.sha256.txt)

The MSI is the complete Windows installer, so it is distributed directly rather than
wrapped in a ZIP archive. Its published SHA-256 covers the exact MSI that users
download:

```text
7C313356B61EE9BC24183CB0BFDD056DBC530E3F5672CBC97D464104C49B60E0  xHydraUnlock-1.0.0.msi
```

The 1.0.0 package was refreshed on 16 July 2026 before the mobile-store rollout to
include the final Windows dashboard polish and explicit, default-off private VPN
unlock controls. The checksum above identifies the current published package exactly.

On Windows, verify a downloaded copy with:

```powershell
Get-FileHash .\xHydraUnlock-1.0.0.msi -Algorithm SHA256
```

No public binary has been added to this repository's git history. See
[`releases/README.md`](releases/README.md) for the release-artifact policy.
