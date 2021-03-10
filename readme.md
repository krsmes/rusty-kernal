

[Origin](https://os.phil-opp.com/freestanding-rust-binary/)

In addtion to installing rust...
``` 
rustup override set nightly
rustup component add rust-src
cargo install bootimage
rustup component add llvm-tools-preview
brew install qemu
```