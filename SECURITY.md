# Security Policy

## Reporting a security issue

Please do not post a security issue publicly when doing so could expose an active
vulnerability, working exploit, sensitive data, or information that would put users at
risk.

A dedicated official security contact is being configured. Until it is published, use
the [official xHydra website](https://xhydra.fr) to find current official contact
information. Do not send vulnerability details to an email address or social account
that is not confirmed through an official xHydra channel.

When reporting an issue privately, include only the information needed to reproduce and
assess it:

- the affected xHydra Unlock version and Windows version;
- a concise description of the impact;
- reproducible steps or a minimal proof of concept; and
- relevant logs with credentials, identifiers, keys, tokens, and personal information
  removed.

Do not include Windows passwords, private signing keys, pairing secrets, credential
blobs, or other secrets in a report.

## Release integrity

Official Windows release artifacts and their SHA-256 checksums are published through
this repository's GitHub Releases. Verify the checksum supplied with a release before
installing its binary.
