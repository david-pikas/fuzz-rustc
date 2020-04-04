# Fuzz Rustc

This repo contains configuration for fuzz-testing the Rust compiler using [libfuzzer-sys](https://github.com/rust-fuzz/libfuzzer-sys),
taking inspiration from [cargo-fuzz](https://github.com/rust-fuzz/cargo-fuzz) and [fuzz-targets](https://github.com/rust-fuzz/targets).

Because [rustc](https://github.com/rust-lang/rust) is a bootstrapping compiler, its build process has several stages
and involves juggling many flags, attributes, and environment variables. These complications create some difficulties for
cleanly setting up fuzz testing. We work around those difficulties with some
[light modifications to rustc](https://github.com/dwrensha/rust/tree/fuzz) and some additional configuration.


## Running


```sh
./run-fuzzer.sh
```

You may add some example inputs in the `./seeds/` directory.

New interesting test cases are automatically written to the `./corpus/` directory as they are found.

## Bugs found

[#62524](https://github.com/rust-lang/rust/issues/62524)
[#62546](https://github.com/rust-lang/rust/issues/62546)
[#62554](https://github.com/rust-lang/rust/issues/62554)
[#62863](https://github.com/rust-lang/rust/issues/62863)
[#62881](https://github.com/rust-lang/rust/issues/62881)
[#62894](https://github.com/rust-lang/rust/issues/62894)
[#62895](https://github.com/rust-lang/rust/issues/62895)
[#62913](https://github.com/rust-lang/rust/issues/62913)
[#62973](https://github.com/rust-lang/rust/issues/62973)
[#63116](https://github.com/rust-lang/rust/issues/63116)
[#63135](https://github.com/rust-lang/rust/issues/63135)
[#66473](https://github.com/rust-lang/rust/issues/66473)
[#68629](https://github.com/rust-lang/rust/issues/68629)
[#68730](https://github.com/rust-lang/rust/issues/68730)
[#68890](https://github.com/rust-lang/rust/issues/68890)
[#69130](https://github.com/rust-lang/rust/issues/69130)
[#69310](https://github.com/rust-lang/rust/issues/69310)
[#69378](https://github.com/rust-lang/rust/issues/69378)
[#69396](https://github.com/rust-lang/rust/issues/69396)
[#69401](https://github.com/rust-lang/rust/issues/69401)
[#69600](https://github.com/rust-lang/rust/issues/69600)
[#69602](https://github.com/rust-lang/rust/issues/69602)
[#70549](https://github.com/rust-lang/rust/issues/70549)
[#70552](https://github.com/rust-lang/rust/issues/70552)
[#70594](https://github.com/rust-lang/rust/issues/70594)
[#70608](https://github.com/rust-lang/rust/issues/70608)
[#70677](https://github.com/rust-lang/rust/issues/70677)
[#70724](https://github.com/rust-lang/rust/issues/70724)
[#70736](https://github.com/rust-lang/rust/issues/70736)
[#70763](https://github.com/rust-lang/rust/issues/70763)

## TODO

Generalize this setup to also work other fuzzing engines, like AFL and Honggfuzz.

## License

All files in this repository are licensed [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
