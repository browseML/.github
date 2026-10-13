<div align="center">

<img src="browseML.png" width="180" alt="browseML">

### Language models in your browser, on your own CPU — verified, with a receipt on every answer

</div>

<table>
<tr>
<td width="33%" valign="top">

**Nothing leaves your device**

The page serves files; your computer does the work. No install, no account, no server writing the answers.

</td>
<td width="33%" valign="top">

**Verified, with receipts**

The model is checked against its sha256 pin before it speaks; every answer carries a receipt the page checks.

</td>
<td width="33%" valign="top">

**Exact before fast**

Identical to llama.cpp's recorded answers, then made fast with threads and SIMD that cannot change them.

</td>
</tr>
</table>

### Repositories

| | |
|---|---|
| **[browseML](https://github.com/browseML/browseML)** | the product: the engine for the browser, its runtime, the page, the control panel |
| **[models](https://github.com/browseML/models)** | verified model copies — a second source beside Hugging Face — and the scripts that check them |
| **[webgpu](https://github.com/browseML/webgpu)** | exact WebGPU kernels, held bit for bit to bankML's reference, and the test that proves it on your GPU |
| **[persona](https://github.com/browseML/persona)** | who browseML is and the facts it answers from, short and checked |
| **[embeddings](https://github.com/browseML/embeddings)** | search in the browser: BM25 as bankML's Savante scores it, fusion with meaning next |

### Try it

**[PYTHAI/browseML](https://huggingface.co/spaces/PYTHAI/browseML)** · [PYTHAI/bankml](https://huggingface.co/spaces/PYTHAI/bankml) · [PYTHAI/bankML-UIF](https://huggingface.co/spaces/PYTHAI/bankML-UIF)

<sub>Built on <a href="https://github.com/cryptoAGI/bankml">bankML</a> by Professor Codephreak and Gregory L. Magnusson (<a href="https://github.com/cryptoAGI">cryptoAGI</a>) · MIT OR Apache-2.0 · Created using Bonsai by Prism ML</sub>
