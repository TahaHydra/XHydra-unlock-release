# Changelog

## [Unreleased]

No published changes after 1.1.0 yet.

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
  `C98BDF5E4F5D7DC2EB69C8E66ED458FD815C74559920889033D122F3CEC78DE1`.
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
