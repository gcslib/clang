# gcslib/clang

libclang, pinned, for tools that parse C with it, such as bindgen.

A GCSL library for pekit, Peios's build tool. Import it as
`github.com/gcslib/clang`.

## Usage

In a build file:

```text
import "github.com/gcslib/clang"
import "github.com/gcslib/rust"

def build app() {
    let vendor = rust.vendored(file("src/Cargo.lock"))
    = rust.cargo_build(dir("src"), vendor, bins = ["app"], libclang = [clang.libclang_18()])
}
```

Register the rust library's toolchains in `workspace.gcsl`, as its README
shows.

## What it provides

- `libclang_18()`: libclang 18.1.1 from the `libclang` wheel on PyPI,
  pinned by its SHA-256: a directory holding `libclang.so`.

The comment at the top of `clang.gcsl` documents each in full.

## Status

gcslib is new, and its libraries' APIs can still change. Pin the commit you
build with: `pekit lock` does so in `pekit.lock`.

## Licence

MIT. See [LICENSE](LICENSE).
