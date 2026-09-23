# ipt_models

Pretrained playing-technique recognition models for [ipt~](https://github.com/DYCI2/ipt_tilde), `pipo.ipt` and any host built on [libipt](https://github.com/nbrochec/libipt).

Models are TorchScript (`.ts`) files trained and exported with [ipt_recognition](https://github.com/nbrochec/ipt_recognition).

## 🎼 Models

| Model | Instrument | Classes | Sample rate | Latency floor | Card |
|---|---|---|---|---|---|
| [`eguitar_ircam.ts`](https://github.com/DYCI2/ipt_models/releases/latest/download/eguitar_ircam.ts) | Electric guitar | 14 | 8 kHz | 896 ms | [card](cards/eguitar_ircam.md) |
| [`flute_ircam.ts`](https://github.com/DYCI2/ipt_models/releases/latest/download/flute_ircam.ts) | Flute | 11 | 44.1 kHz | 333 ms | [card](cards/flute_ircam.md) |
| [`trumpet_ircam.ts`](https://github.com/DYCI2/ipt_models/releases/latest/download/trumpet_ircam.ts) | Trumpet | 14 | 44.1 kHz | 333 ms | [card](cards/trumpet_ircam.md) |
| [`trumpet_harmon_ircam.ts`](https://github.com/DYCI2/ipt_models/releases/latest/download/trumpet_harmon_ircam.ts) | Trumpet, harmon mute | 14 | 44.1 kHz | 333 ms | [card](cards/trumpet_harmon_ircam.md) |

Each card lists the classes in output order, the model's specifications and its SHA-256.

## 🚀 Usage

Put the `.ts` file in Max's search path (or give an absolute path), then:

```
ipt~ flute_ircam.ts
pipo~ ipt @ipt.model flute_ircam.ts
```

The host audio is resampled to the model's sample rate by libipt, so any Max sample rate works.

## 💾 Download

Models are distributed as assets of the [Releases](https://github.com/DYCI2/ipt_models/releases). The links in the table above always point to the latest release; older versions stay available on the Releases page. Each release also ships a `SHA256SUMS` file:

```
shasum -a 256 -c SHA256SUMS
```

## 📁 Layout

```
cards/    one Markdown card per model
```

## 📜 License

This project is released under a CC-BY-NC-4.0 license.

## 📇 Contact

Please write to `nicolas.brochec[at]ircam.fr` for any questions.
