# eguitar_ircam

Electric guitar playing-technique classifier, 14 classes.

File: [`eguitar_ircam.ts`](https://huggingface.co/nbrochec/ipt_models/resolve/main/eguitar_ircam.ts)

```
ipt~ eguitar_ircam.ts
pipo~ ipt @ipt.model eguitar_ircam.ts
```

## Specifications

| | |
|---|---|
| Sample rate (`get_sr`) | 8000 Hz |
| Segment length (`get_seglen`) | 7168 samples (896 ms, latency floor) |
| Classes | 14 |
| Parameters | 3,360,398 |
| Architecture | `v2` |
| Front-end | one log-mel spectrogram: n_fft 2048, hop 512, 128 mel bands, f_min 150 Hz (window of 256 ms at 8 kHz, spectrum up to 4 kHz) |
| Output | logits `(batch, 14)`, batched forward supported |
| Forward pass | 3.7 ms (Apple Silicon, CPU, 1 thread) |
| Exported with | TorchScript, loads with torch 2.4.1 |
| Size | 14.1 MB |
| SHA-256 | `93cfb7a1e6440b57530e464609e038381dc5d1286eb9504cc0d74c894e9c5d1b` |

## Classes

Index as output by `ipt~` (left outlet) and column order in `pipo.ipt`.

| Index | Class |
|---|---|
| 0 | `behind-nut` |
| 1 | `bend` |
| 2 | `bottleneck` |
| 3 | `glissando` |
| 4 | `legato` |
| 5 | `muted` |
| 6 | `palmstrike` |
| 7 | `scratch` |
| 8 | `snap-pizz` |
| 9 | `staccato` |
| 10 | `sustained` |
| 11 | `tremolo` |
| 12 | `trill` |
| 13 | `vibrato` |

## Notes

+ Runs at 8 kHz with a 896 ms segment: noticeably slower to react than the 44.1 kHz models.
+ PyTorch warns once about `padding='same'` with an even kernel; harmless.

## Training

Dataset: EG-IPT, [EG-IPT Dataset](https://doi.org/10.5281/zenodo.15205644) (Zenodo), described in [Fiorini et al., NIME 2025](https://hal.science/hal-05061680)
<!-- TODO: ipt_recognition commit / config used -->
<!-- TODO: evaluation metrics (accuracy, macro F1, ...) -->
