# Contributing

`npa-std` is certificate-first. Changes are accepted by source-free package
verification, not by parser, elaborator, tactic, automation, command status, or
release metadata.

Before opening a pull request, run:

```sh
npa package check --root . --json
npa package build-certs --root . --check --json
npa package verify-certs --root . --checker reference --json
npa package check-hashes --root . --json
npa package axiom-report --root . --check --json
npa package index --root . --check --json
```

If `generated/publish-plan.json` changes, also run:

```sh
npa package publish-plan --root . --check --json
```

Do not add custom axioms, `sorry`-style placeholders, registry lookup, latest
version resolution, hidden package caches, plugin loading, or network package
fetching as part of proof acceptance.

For this initial release, keep the public module set limited to:

```text
Std.Logic.Eq
Std.Nat.Basic
```
