# Security policy

This policy covers every Externalize Labs repository that has no SECURITY.md of
its own.

Report vulnerabilities privately through the **Security → Report a
vulnerability** tab of the affected repository, never in a public issue. We aim
to acknowledge reports within three days.

The most serious class of bug is a proof that verifies but describes something
the trust set did not externalize. See the
[trust model](https://github.com/Externalize-Labs/externalize/blob/main/docs/trust-model.md).
`exnode` is untrusted by design: a bug there matters when it lets a bundle
verify that shouldn't, or stops honest bundles from being built.
