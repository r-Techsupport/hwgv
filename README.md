# HWGV
HWGV, or hwinfo-online is a viewer for .csv log files generated by [HWiNFO](https://www.hwinfo.com/).

All parsing is done client side, by a Rust parser compiled to WASM (located in `src/scripts/parser`).

## Building
To build HWGV, you need to have the Rust toolchain installed (<https://rustup.rs/>), and `wasm-pack` installed.

To install wasm-pack (after installing the Rust toolchain):
```
cargo install wasm-pack
```

After this, you'll need to compile the parser located in `src/scripts/parser`, after compilation, a `src/scripts/parser/pkg` directory will be created.

To compile the parser:
```
wasm-pack build --target web
```

Optionally, you may run `./build.sh` which will build the parser and copy essential files to `./target`. 

HWGV will still function if you open `src/index.html`, the build script simply omits nonessential files (rust source files, documentation).

