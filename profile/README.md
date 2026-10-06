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
Soroban contract event.

| Repository | Language | What it does |
|---|---|---|
| [externalize](https://github.com/Externalize-Labs/externalize) | Rust | Verifier library (native and WASM) and `externalize` CLI |
| [externalize-node](https://github.com/Externalize-Labs/externalize-node) | Go | `exnode`: builds and serves proof bundles from archives and RPC |

Verified on mainnet: every ledger of checkpoint 64791359 is certified by 30
tier-1 validator signatures, and contract calls are proven down to the exact
return value and events.

We take part in the [Stellar Wave](https://www.drips.network/wave/stellar)
program. Look for issues labeled by complexity in each repository.
