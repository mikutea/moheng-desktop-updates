# Moheng Desktop Updates

Official public distribution surface for Moheng Windows updates. The Moheng
application source code is maintained in a separate **private** repository.

## Current state: `bootstrap_locked`

The update channel has not been activated. There is currently:

- no production `stable.json` client feed;
- no approved Windows installer;
- no production signing public key published here.

[`docs/status.json`](docs/status.json) is a human-readable publication-status
document only. It is deliberately **not** an update manifest and must not be
consumed by Moheng clients.

When the channel is activated, signed metadata will be published through
GitHub Pages and approved, immutable installers through GitHub Releases. The
activation and release gates are documented in
[`RELEASE-POLICY.md`](RELEASE-POLICY.md).

This repository must never contain Moheng source code, OKX credentials, user
data, API tokens, Ed25519 private keys, Authenticode private keys, or other
secrets.

---

这里是墨衡 Windows 更新的官方公开发布面；应用源码仍保存在独立的私有仓库中。
当前状态为 `bootstrap_locked`，正式更新源和安装包均未发布。
