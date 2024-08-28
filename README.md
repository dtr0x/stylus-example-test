Following command:
```
cargo build --release --target wasm32-unknown-unknown
```
fails with:
```
error[E0152]: found duplicate lang item `panic_impl`
  --> /home/dylan/.cargo/git/checkouts/rust-contracts-stylus-7b6f4dfe793ef8eb/2df1878/contracts/src/lib.rs:59:1
   |
59 | / fn panic(_info: &core::panic::PanicInfo) -> ! {
60 | |     loop {}
61 | | }
   | |_^
   |
   = note: the lang item is first defined in crate `std` (which `ruint` depends on)
   = note: first definition in `std` loaded from /home/dylan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/wasm32-unknown-unknown/lib/libstd-196a6c26eeea7aec.rlib
   = note: second definition in the local crate (`openzeppelin_stylus`)

For more information about this error, try `rustc --explain E0152`.
error: could not compile `openzeppelin-stylus` (lib) due to 1 previous error

```
