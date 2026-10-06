# Contributing

This guide applies to every Externalize Labs repository without its own. The
projects take part in the [Stellar Wave](https://www.drips.network/wave/stellar)
program; Wave issues are labeled with their complexity.

## Repositories and their checks

| Repository | Language | Before you push |
|---|---|---|
| [externalize](https://github.com/Externalize-Labs/externalize) | Rust 1.88+ | `cargo fmt --all`, `cargo clippy --workspace --all-targets -- -D warnings`, `cargo test --workspace` |
| [externalize-node](https://github.com/Externalize-Labs/externalize-node) | Go 1.25+ | `gofmt -l .`, `go vet ./...`, `go test -race ./...`, `golangci-lint run` |

`rust-toolchain.toml` and `go.mod` pin the toolchains. CI runs the same checks
on Linux, macOS and Windows, plus cargo-deny or govulncheck, the MSRV, the WASM
build (which verifies the mainnet fixture from Node), and a Docker build.

## Ground rules

- **Get assigned first.** Comment on the issue and wait for assignment.
- **One issue, one PR.** Link it with `Closes #N`.
- **Tests come with the change.** A verification change needs a test that would
  have failed without it, ideally against the mainnet fixtures.
- **Fail closed.** When in doubt, reject. A verifier that accepts too much is
  worse than none.
- **No panics in library code.** In Rust, `unwrap`, `expect`, `panic!` and
  unchecked indexing are denied by lint; return an `Error`. In Go, return
  errors wrapped with `%w`.
- **`exnode` stays untrusted.** It builds bundles; it never decides whether
  they are valid. Validity lives in `externalize-core` only.
- **Keep the tree clean.** Don't commit notes, summaries, PR drafts or backup
  files. CI rejects the common ones.

## Fixtures

`externalize/crates/externalize-core/tests/fixtures/mainnet` holds real
public-network data: one archive checkpoint's headers and SCP messages, one
ledger's results and transaction set, and two transactions' meta from RPC.
`bundle-64791359.json` is generated from them:

```sh
UPDATE_FIXTURES=1 cargo test -p externalize-core --test mainnet
```

`exnode` must build that bundle byte for byte, so if you change the bundle
format, copy the regenerated file to `externalize-node/testdata` in the same
change. CI in both repositories checks they agree.

## Commit messages

[Conventional Commits](https://www.conventionalcommits.org): `feat(core): …`,
`fix(archive): …`, `docs: …`, `test: …`.
