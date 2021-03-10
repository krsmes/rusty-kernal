

[Origin](https://os.phil-opp.com/freestanding-rust-binary/)

In addition to installing rust...
``` 
rustup override set nightly
rustup component add rust-src
cargo install bootimage
rustup component add llvm-tools-preview
brew install qemu
```

Depends on bootloader

Panic aborts configured in Cargo.toml described [here](https://os.phil-opp.com/freestanding-rust-binary/#disabling-unwinding):
```
[profile.dev]
panic = "abort"

[profile.release]
panic = "abort"
```

x86_64-krsos.json is a custom target definiton, key attribute being "os: none".

This target is defined as the default in `.cargo/config.toml`
```
[build]
target = "x86_64-krsos.json"
```

Also in `.cargo/config.toml` is an interesting key described [here](https://os.phil-opp.com/minimal-rust-kernel/#memory-related-intrinsics): 
```
build-std-features = ["compiler-builtins-mem"]
```
