# ipt_models

Pretrained playing-technique recognition models for [ipt~](https://github.com/DYCI2/ipt_tilde), `pipo.ipt` and any host built on [libipt](https://github.com/nbrochec/libipt).

Models are TorchScript (`.ts`) files trained and exported with [ipt_recognition](https://github.com/nbrochec/ipt_recognition).

## 🎼 Models

| Model | Instrument | Classes | Sample rate | Latency floor | Card |
|---|---|---|---|---|---|
| [`eguitar_ircam.ts`](models/eguitar_ircam.ts) | Electric guitar | 14 | 8 kHz | 896 ms | [card](cards/eguitar_ircam.md) |
| [`flute_ircam.ts`](models/flute_ircam.ts) | Flute | 11 | 44.1 kHz | 333 ms | [card](cards/flute_ircam.md) |
| [`trumpet_ircam.ts`](models/trumpet_ircam.ts) | Trumpet | 14 | 44.1 kHz | 333 ms | [card](cards/trumpet_ircam.md) |
| [`trumpet_harmon_ircam.ts`](models/trumpet_harmon_ircam.ts) | Trumpet, harmon mute | 14 | 44.1 kHz | 333 ms | [card](cards/trumpet_harmon_ircam.md) |

Each card lists the classes in output order, the model's specifications and its SHA-256.

## 🚀 Usage

Put the `.ts` file in Max's search path (or give an absolute path), then:

```
ipt~ flute_ircam.ts
pipo~ ipt @ipt.model flute_ircam.ts
```

The host audio is resampled to the model's sample rate by libipt, so any Max sample rate works.

## 💾 Download

Download a model from its card or from the table above. To clone the whole repository, install [Git LFS](https://git-lfs.com) first: the `.ts` files are stored with it, and a clone without it only contains small pointer files.

## 📁 Layout

```
models/   TorchScript models (.ts)
cards/    one Markdown card per model
```

## ➕ Adding a model

A model must be a TorchScript module whose `forward` takes `(batch, 1, segment_length)` float32 raw audio and returns logits `(batch, num_classes)`, and which exports `get_sr()`, `get_seglen()` and `get_classnames()`. Export it with torch 2.4.1, the version libipt links against.

Name it `<instrument>[_<variant>]_<source>.ts`, add its card in `cards/` and a row to the table above.

## 📜 License

<!-- TODO -->

## 📇 Contact

Please write to `nicolas.brochec[at]ircam.fr` for any questions.
