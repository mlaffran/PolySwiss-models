# PolySwiss models

Language packages the PolySwiss app downloads on first use. The files are attached to the release
[`models-v1`](https://github.com/mlaffran/PolySwiss-models/releases/tag/models-v1); nothing is stored in the repository
itself.

Each file is named `<package>__<path>`, with `/` in the path written as `__`.

| Package | What it is | Source | Licence |
|---|---|---|---|
| `en-suggest` | English word suggestions: SmolLM2-135M, 4-bit ONNX with a scoring head; tokenizer; lexicon | [HuggingFaceTB/SmolLM2-135M](https://huggingface.co/HuggingFaceTB/SmolLM2-135M); lexicon from [wordfreq](https://github.com/rspeer/wordfreq) | Apache 2.0; wordfreq data CC BY-SA 4.0 |
| `it-suggest` | Italian word suggestions: Goldfish `ita_latn_1000mb`, int8 ONNX scoring head; tokenizer; lexicon | [goldfish-models/ita_latn_1000mb](https://huggingface.co/goldfish-models/ita_latn_1000mb); lexicon from wordfreq | Apache 2.0; wordfreq data CC BY-SA 4.0 |
| `vosk-en` | English dictation: `vosk-model-small-en-us-0.15` | [alphacephei.com/vosk/models](https://alphacephei.com/vosk/models) | Apache 2.0 |
| `vosk-it` | Italian dictation: `vosk-model-small-it-0.22` | [alphacephei.com/vosk/models](https://alphacephei.com/vosk/models) | Apache 2.0 |
| `dict` | Translator word lists `<xx>-en` for de, es, fr, it | English Wiktionary via [kaikki.org](https://kaikki.org), word frequencies from wordfreq | CC BY-SA 4.0 (and GFDL for Wiktionary) |

The ONNX files are conversions of the original models (export and quantization); the dictionaries are extracts of
Wiktionary glosses. Both are shared under the same licences as their sources.

`en-suggest__completion-bundle.json` and `it-suggest__manifest.json` list each package's files with size, MD5 and
SHA-256; the app checks every download against them.
