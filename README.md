# xHydra Unlock Releases

This is the official public binary-release repository for **xHydra Unlock**. It is the
authoritative location for published Windows binaries, release notes, and SHA-256
checksums.

The xHydra Unlock source code is currently private. This repository intentionally
contains release information and distribution artifacts only; it does not contain the
private product source.

## About xHydra Unlock

xHydra Unlock is a Windows 10 and Windows 11 companion application that lets you approve
a Windows unlock from an iPhone or Android phone over the local network.

Its security model includes:

- LAN-only operation with no cloud relay;
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

## Releases

When a version is ready for public distribution, its official Windows binary, release
notes, and SHA-256 checksum are published through this repository's GitHub Releases.
Verify the published checksum before installing a downloaded binary.

No public binary has been added to this repository's git history. See
[`releases/README.md`](releases/README.md) for the release-artifact policy.
