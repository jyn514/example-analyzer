# example-analyzer

## Setup

```bash
git clone https://github.com/willcrichton/rust
cd rust
./x.py --stage 1 build
export CUSTOM_RUSTDOC=$(pwd)/build/x86_64-apple-darwin/stage1/bin/rustdoc
cd ..
git clone https://github.com/willcrichton/example-analyzer
cd example_analyzer
rustup toolchain install nightly
rustup override set nightly
cargo build
```

## Exapmle

```bash
cd doctest
../target/debug/example-analyzer
cargo clean && cargo doc -vv
# copy the command within Running `...` and:
# 1. replace rustdoc with $CUSTOM_RUSTDOC
# 2. add the flag "--call-locations .call_locations.json" to the end
# 3. run the command
open target/doc/doctest/index.html
```