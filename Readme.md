# zstd

[![Build Status](https://travis-ci.org/Gyscos/zstd-rs.svg?branch=master)](https://travis-ci.org/Gyscos/zstd-rs)
[![crates.io](http://meritbadge.herokuapp.com/zstd)](https://crates.io/crates/zstd)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)

This library is a rust binding for the [zstd compression library][zstd].

# [Documentation][doc]

## Add to `cargo.toml`

### Using [cargo-edit][cargo-edit]

```bash
$ cargo add zstd
```

### Manually

```toml
# Cargo.toml

[dependencies]
zstd = "0.1"
```

## Usage

```rust
extern crate zstd;

use std::io;

fn main() {
	// Uncompress input and print the result.
	let mut decoder = zstd::Decoder::new(io::stdin()).unwrap();
	io::copy(&mut decoder, &mut io::stdout()).unwrap();
}
```

# TODO

* Benchmarks, optimizations, ...
* Train dictionary

# Disclaimer

This implementation is largely inspired by bozaro's [lz4-rs][lz4].

[zstd]: https://github.com/Cyan4973/zstd
[lz4]: https://github.com/bozaro/lz4-rs
[cargo-edit]: https://github.com/killercup/cargo-edit#cargo-add
[doc]: https://gyscos.github.io/zstd-rs/zstd/index.html
