<p align="center">
  <img src="browseML.png" width="220" alt="browseML">
</p>

<h3 align="center">bankML in your browser — verified, with a receipt on every answer</h3>

**browseML** is [bankML](https://github.com/cryptoAGI/bankml)'s own engine, compiled to WebAssembly and run on the
visitor's CPU. There's nothing to install and no account to make, and no server writes the answers: the page only
serves files.

- **Verified before it speaks.** The engine checks the model the way `bankml serve` does: the GGUF guard first, then
  the sha256 of the whole file against its pin. It won't answer from a file that fails either check.
- **A receipt on every answer.** The engine returns `bankml serve`'s own receipt, and the page recomputes the
  answer's sha256 and shows ✓ or ✗ under it.
- **Exact before fast.** On llama-server b11192's recorded conversations, every text, finish reason and token count
  is identical. That holds on one thread, on Web Workers, and with relaxed SIMD wherever relaxed SIMD is exact.

## What works today

| | |
|---|---|
| model | Bonsai-1.7B Q1_0 (248 MB, prism-ml, Apache-2.0), downloaded once and kept in the browser's cache |
| engine memory | 317 MB once open (measured) |
| threads | on every core the browser reports (up to 8) when the page is cross-origin isolated; otherwise one |
| download | 16 MB pieces, each retried from where a dropped connection cut it |
| browsers | Chrome, Edge, Brave and Firefox on desktop, and phones. Safari runs on one thread |

## Repositories

| repository | what it is |
|---|---|
| [browseML](https://github.com/browseML/browseML) | the engine for the browser, the runtime (`web/`), the landing page, the tests, and the model (Git LFS). Its first public experiments are mapped in [HISTORY.md](https://github.com/browseML/browseML/blob/main/HISTORY.md) |

## Try it

These Hugging Face Spaces run browseML today:

- [PYTHAI/browseML](https://huggingface.co/spaces/PYTHAI/browseML): the landing page
- [PYTHAI/bankml](https://huggingface.co/spaces/PYTHAI/bankml): the full bankML Space, where browseML first appeared (2026-10-09)
- [PYTHAI/bankML-UIF](https://huggingface.co/spaces/PYTHAI/bankML-UIF): bankML behind the ultimate input field

The full list is the [Hugging Face index](https://deltaverse.pythai.net/hfindex).

## Lineage

browseML grew out of [bankML](https://github.com/cryptoAGI/bankml), a zero-dependency Rust runtime for 1-bit and
ternary models, bit-exact against llama.cpp b11192. It was a surprise on bankML's road to 0.5.0, the hardware
milestone: the visitor's browser became an unplanned piece of hardware to run on.

By Professor Codephreak and Gregory L. Magnusson ([cryptoAGI](https://github.com/cryptoAGI)). `MIT OR Apache-2.0`.
Created using Bonsai by Prism ML.
