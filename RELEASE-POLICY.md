# Moheng Update Release Policy

This repository is a public, binary-only distribution surface. The private
Moheng source repository, build credentials, user data, and signing private
keys are out of scope and must never be copied here.

## Channel states

### `bootstrap_locked`

- `docs/channels/stable.json` must not exist.
- No installer is approved for client delivery.
- `docs/status.json` is informational only and is not a client feed.
- GitHub Pages may publish the status page, but clients must fail closed when
  the production feed is absent.

### Activated

Activation requires an explicit release approval after all of these controls
are in place:

1. The desktop client pins the approved production verification trust root.
2. Production signing private keys are held outside this repository and are
   never exposed to GitHub Actions logs or artifacts.
3. The application and installer are Authenticode-signed and timestamped
   before their final digest is calculated.
4. The signed update manifest binds an immutable version, installer URL,
   byte length, SHA-256 digest, and release sequence.
5. A clean-machine Windows installation and rollback/recovery procedure has
   been verified.
6. Negative tests confirm fail-closed behavior for invalid signatures,
   downgrade attempts, unexpected redirects, wrong hashes, and malformed
   metadata.

## Publication order

For an approved release:

1. Build and test from the reviewed private-source revision.
2. Authenticode-sign and timestamp the application and installer.
3. Verify the signatures on a clean Windows environment.
4. Calculate the final byte length and SHA-256 digest.
5. Create and sign the final update manifest offline.
6. Upload a new, versioned installer asset without overwriting an existing
   asset.
7. Independently verify the downloaded public asset against the signed
   manifest.
8. Publish the signed channel manifest and probe the public endpoint.

Published versioned assets and versioned manifest snapshots are append-only. A
release is never repaired in place; corrections use a new version and release
sequence. The fixed `channels/stable.json` path is the signed channel pointer:
it may only be replaced atomically after its new signed contents and monotonic
sequence have passed every release gate.

## Prohibited content and actions

- source code from the private Moheng repository;
- OKX credentials, user data, tokens, passwords, or private keys;
- unsigned or unapproved executables presented as official releases;
- placeholder, empty, or intentionally invalid production manifests;
- overwriting a published installer or signed manifest;
- signing production metadata in GitHub-hosted automation.
