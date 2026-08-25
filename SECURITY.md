# Security Policy

## Scope

Security reports may cover the public update metadata, published release
assets, GitHub Pages deployment, signature or hash verification, downgrade or
equivocation resistance, and release-process integrity.

The application source code is not hosted in this repository.

## Reporting a vulnerability

Use this repository's **Security** tab and GitHub private vulnerability
reporting when it is available. Include:

- the affected URL, release, or metadata field;
- steps to reproduce;
- the expected and observed behavior;
- the security impact;
- any suggested mitigation.

Do not publish exploit details, credentials, private keys, access tokens, or
sensitive user data in an issue or discussion. If private vulnerability
reporting is temporarily unavailable, open a non-sensitive issue requesting a
private reporting channel, without including vulnerability details.

## Release authenticity

No file is an official Moheng installer merely because it appears in this
repository. An official release must satisfy every gate in
[`RELEASE-POLICY.md`](RELEASE-POLICY.md). During `bootstrap_locked`, no
production update manifest or installer is authorized.
