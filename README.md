# local-ai-models

Model weights and the **canonical model registry** for the `local-ai-engine` app.

`model_registry.json` in this repo is what the app fetches at startup (it keeps a
cached copy and falls back to the copy bundled at build time). To add, change or remove
a model for every installed app: edit that file here and push. No app rebuild.

- Set `capabilitiesVerified` to true only after a model has run on a real device.
- `sizeBytes` and `sha256` must match the file exactly; the app verifies both after
  download. `sha256sum <file>` gives the hash.
- Files can live as Release assets here (`gh release upload models-v1 <file>`) or, if
  the upstream repo is not gated, point `url` straight at Hugging Face.

Weights are published as GitHub Release assets so the app can download them directly —
no Hugging Face login, no file paths.

These are **unmodified** `.litertlm` conversions published by Google's
[litert-community](https://huggingface.co/litert-community) on Hugging Face, re-hosted
here because those repositories are gated behind a licence click-through that an app
cannot perform on the user's behalf.

| Release asset | Source | Size (bytes) | SHA-256 |
|---|---|---|---|
| `gemma3-270m-it-q8.litertlm` | `litert-community/gemma-3-270m-it` | 304005120 | see release notes |

Gemma models are provided under and subject to the **Gemma Terms of Use** at
<https://ai.google.dev/gemma/terms>. See `GEMMA_TERMS.md`.
