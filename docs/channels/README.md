# Update channels

The production `stable.json` feed is deliberately absent while the repository
is in `bootstrap_locked` state.

Do not add a placeholder, empty, test-signed, or intentionally invalid
`stable.json`. Moheng clients must treat the missing production feed as a
fail-closed condition. The file may be created only through the approved
activation and publication process in [`RELEASE-POLICY.md`](../../RELEASE-POLICY.md).
