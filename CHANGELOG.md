# Changelog

## [Unreleased]

No additional changes documented.

## [1.1.1] - 2026-10-04

Windows companion fixes and pairing improvements:

- Fixed Windows pairing persistence consistency: a failed persistence write no longer changes the live trusted-device state.
- Made pairing QR nonce consumption atomic, preventing concurrent reuse of one pairing nonce.
- Added “Don't have the mobile app? Get xHydra Unlock” to the Windows pairing UI, linking to [xHydra Unlock](https://xhydra.fr/products/xhydra-unlock).
- Bumped the Windows version to 1.1.1.

This Windows release does not include Android or iOS changes.

### Distribution

- Windows MSI: `xHydraUnlock-1.1.1.msi`.
- SHA-256:
  `9F21EF037BCB6FEE7B4532F71B8A130F297BDAED5CCDF8661808A810E7FAA953`.
- The installer is still not signed with a publicly trusted Authenticode certificate.
  SHA-256 verifies integrity only; it is not publisher authentication.

## [1.1.0] - 2026-10-01

Major Windows companion and mobile-experience update.

### Added

- Phone controls for **Lock, Sleep, Restart, and Shut down**.
- Wake-on-LAN support.
- Redesigned Windows companion interface.
- Improved pairing and paired-PC management.
- OS device-authentication fallback when biometrics are unavailable.
- Separate VPN permissions for unlock and PC controls.
- Help, feedback, share, and review entry points in the mobile apps.

### Security and reliability

- Hardened Windows service / Credential Provider IPC boundaries.
- Added stronger local service/client identity checks.
- Tightened Windows session targeting before credential delivery.
- Hardened local application-data directory handling.
- Added challenge/resource bounds and connection limits.
- Added slow-client protections.
- Bounded audit-log growth.
- Reduced unauthenticated exposure of Wake-on-LAN metadata.
- Sanitized security-relevant logging.
- Updated TLS dependencies and release-pipeline checks.

### Distribution

- Published Windows MSI: `xHydraUnlock-1.1.0.msi`.
- SHA-256:
  `8A0CE4752466B618D9F49005163157B3ECD6D81D10FC9066ADEE265067BDC886`.
- The Windows installer is currently not signed with a publicly trusted Authenticode
  certificate; Windows SmartScreen may show an Unknown publisher warning.

## [1.0.0] - 2026-07-16

Initial public Windows companion release.

The package was refreshed before the mobile-store rollout with:

- final Windows dashboard and uninstall discoverability polish;
- an explicit **Allow unlock over VPN** setting, disabled by default;
- service-enforced RFC1918/IPv6 ULA source restrictions;
- dedicated Private/Domain Windows Firewall rules that exist only while VPN unlock is
  enabled; and
- backward-compatible VPN capability reporting for the iPhone and Android apps.
