# Changelog

## [Unreleased]

No additional changes documented.

## [1.2.0] - 2026-10-16

Windows companion update.

### Added

- The MSI and the Windows programs it installs (service, sign-in tile, app) are now
  **Authenticode-signed** by Taha Laachari (Certum certificate), with an RFC 3161
  timestamp.
- Home shows network problems above the status cards: a Public network, a Public VPN
  adapter, or private VPN access turned on with no trusted network. **Make private…** is
  offered once, in the warning.
- An optional, advisory "likely company-managed" hint for the phone apps (Active Directory
  or Microsoft Entra join, Domain network, managed policy). It contains no domain, tenant,
  company or user identifiers.

### Changed

- One **Allow access over private VPN** setting replaces the separate VPN permissions for
  unlock and PC controls. Existing settings carry over without turning off an access that
  was on, and settings managed by your organization are respected.
- Private VPN access recognises the private address ranges used by common VPNs, including
  Tailscale (100.64.0.0/10). Public addresses and Public Windows networks stay blocked.
- The installer no longer forces a restart. The app starts right after installation, and
  starting it again shows the running window instead of a second tray icon.

### Fixed

- **Sleep** now works on Modern Standby PCs.
- Paired phones learn the PC's addresses while on the local network, so they can find it
  over a private VPN later.

This Windows release does not include Android or iOS changes.

### Distribution

- Windows MSI: `xHydraUnlock-1.2.0.msi` (58,310,656 bytes).
- SHA-256:
  `58AE30E6FE170ABB1B5C2F23D91CC255FEE2EF090D231B9AB78A7B0C4B6D8901`.
- Signed: `CN=Taha Laachari`, issued by Certum Code Signing 2021 CA.

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
