# audio.cpp speech server builds for Koharu

`audiocpp_server` with the Fish Audio Drama 3 port (`fish_drama3`) from
[JarodMica/audio.cpp](https://github.com/JarodMica/audio.cpp/tree/drama-3-native).
`koharu-runtime` downloads them on first use, like `koharu-rs/llama`.

| Asset | Platform |
| --- | --- |
| `x86_64-pc-windows-msvc-cuda.tar.gz` | Windows x64, CUDA |
| `x86_64-unknown-linux-gnu-cuda.tar.gz` | Linux x64, CUDA (glibc 2.39+) |

Archives hold the executable and licenses at the root. CUDA 13 libraries are
not bundled; Koharu installs them from NVIDIA wheels and puts them on the
server's library path.

## Release

1. Push this repository as `karrot0/audio.cpp`.
2. Run the **Release** workflow; it publishes `RELEASE_TAG`.
3. Keep `AUDIOCPP_REF`/`RELEASE_TAG` here and `RELEASE`/`REPOSITORY` in
   `crates/koharu-runtime/src/runtime/packages/audiocpp.rs` in sync.

## Licenses

audio.cpp: Apache-2.0. ggml: MIT. Both ship in every archive. Drama 3 weights
are not included (Fish Audio Community License).
