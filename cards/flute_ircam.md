# flute_ircam

Flute playing-technique classifier, 11 classes.

File: [`models/flute_ircam.ts`](../models/flute_ircam.ts)

```
ipt~ flute_ircam.ts
pipo~ ipt @ipt.model flute_ircam.ts
```

## Specifications

| | |
|---|---|
| Sample rate (`get_sr`) | 44100 Hz |
| Segment length (`get_seglen`) | 14700 samples (333 ms, latency floor) |
| Classes | 11 |
| Parameters | 72,591 |
| Architecture | `ismir_II_3stacked` |
| Front-end | three stacked log-mel spectrograms: n_fft 512 / 1024 / 2048, hop 128, 384 mel bands, f_min 120 Hz |
| Output | logits `(batch, 11)`, batched forward supported |
| Forward pass | 7.0 ms (Apple Silicon, CPU, 1 thread) |
| Exported with | TorchScript, loads with torch 2.4.1 |
| Size | 3.2 MB |
| SHA-256 | `8cf23a4675da63334e0bfca9ecc8a61e6b462a43d68bf0585f8943ebb42dbe05` |

## Classes

Index as output by `ipt~` (left outlet) and column order in `pipo.ipt`.

| Index | Class |
|---|---|
| 0 | `aeolian` |
| 1 | `flatterzunge` |
| 2 | `key-click` |
| 3 | `multiphonics` |
| 4 | `ordinario` |
| 5 | `pizzicato` |
| 6 | `play-and-sing` |
| 7 | `staccato` |
| 8 | `tongue-ram` |
| 9 | `trill` |
| 10 | `whistle-tone` |

## Training

Dataset: GFD, [GFDatabase: A Database of Flute Playing Techniques](https://doi.org/10.5281/zenodo.14712391) (Brochec & Howie, v2.1, Zenodo)
<!-- TODO: ipt_recognition commit / config used -->
<!-- TODO: evaluation metrics (accuracy, macro F1, ...) -->
