# Getting help

- **Using the verifier or a bundle failed?** Run `externalize verify --json`
  and open a bug in [externalize](https://github.com/Externalize-Labs/externalize/issues)
  with the output and, if you can, the bundle.
- **`exnode` could not build a bundle?** Open a bug in
  [externalize-node](https://github.com/Externalize-Labs/externalize-node/issues)
  with the ledger, the transaction hash and the archive you used.
- **What exactly is proven, and what you still trust:** read the
  [trust model](https://github.com/Externalize-Labs/externalize/blob/main/docs/trust-model.md)
  first; it answers most "why does this verify?" questions.
- **Wire format for another language:** the
  [bundle format](https://github.com/Externalize-Labs/externalize/blob/main/docs/bundle-format.md).
- **A proof that verifies but shouldn't** is a security issue: report it
  privately as described in [SECURITY.md](SECURITY.md).
