<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Externalize-Labs/.github/main/assets/logo-dark.svg">
    <img src="https://raw.githubusercontent.com/Externalize-Labs/.github/main/assets/logo.svg" alt="Externalize" height="64">
  </picture>
</p>

<p align="center"><b>Verify Stellar from the validators' own signatures.</b></p>

Wallets, indexers, bridges and payment facilitators trust whatever their RPC
tells them. Externalize replaces that trust with proof: SCP signatures from the
validators you choose, then hash commitments down to a single transaction or
Soroban contract event. Verification is offline, fail-closed, and runs in a
browser.

| Repository | Language | What it does |
|---|---|---|
| [externalize](https://github.com/Externalize-Labs/externalize) | Rust | Verifier library, `externalize` CLI, and `externalize-wasm` for browsers and Node |
| [externalize-node](https://github.com/Externalize-Labs/externalize-node) | Go | `exnode`: builds and serves proof bundles from history archives and any Stellar RPC |

**On mainnet today:** ledger 64,791,359 is certified by 30 tier-1 validator
signatures, all 10 organizations agreeing, and a Soroban contract call in it is
proven down to its exact return value and four events. The same check runs in
about 7 ms natively and from JavaScript in a 212 KB (gzipped) WASM package.

**Start here:** `externalize verify proof.json` on a bundle from `exnode`, or
drop one into the [browser example](https://github.com/Externalize-Labs/externalize/tree/main/examples/web).
What is proven, and what you still trust, is in the
[trust model](https://github.com/Externalize-Labs/externalize/blob/main/docs/trust-model.md).

**Contributing:** we take part in the
[Stellar Wave](https://www.drips.network/wave/stellar) program; issues are
labeled by complexity. Read [CONTRIBUTING](https://github.com/Externalize-Labs/.github/blob/main/CONTRIBUTING.md)
first, and report security issues privately as described in
[SECURITY](https://github.com/Externalize-Labs/.github/blob/main/SECURITY.md).
