---
name: rust-dependency-analysis
description: Analyse a Rust crate's dependencies, generating documentation and viewing available features.
---

# Rust dependency info

Use this to find information about a Rust crate, such as the available features:

```sh
cargo info [spec]
```

e.g.

```sh
cargo info serde@1.0.0
```

# Rust dependency docs

Use this to inspect the API docs for Rust dependencies:

```sh
cargo doc
```

`cargo doc` builds documentation for the selected local package and its dependencies, and writes the output under `target/doc`.

If the crate's API depends on features, generate docs with the same feature selection the project uses, for example:

```sh
cargo doc --features serde
cargo doc --all-features
cargo doc --no-default-features
```

For workspaces, narrow or widen scope as needed:

```sh
cargo doc -p my_crate
cargo doc --workspace
```

## View the generated docs

The generated HTML lives in `target/doc` by default.

- Open `target/doc/<crate_name>/index.html` to view a specific crate.
- Open `target/doc/index.html` when Cargo generated a workspace landing page.
