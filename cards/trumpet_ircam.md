# trumpet_ircam

Trumpet playing-technique classifier, 14 classes.

File: [`trumpet_ircam.ts`](https://huggingface.co/nbrochec/ipt_models/resolve/main/trumpet_ircam.ts)

```
ipt~ trumpet_ircam.ts
pipo~ ipt @ipt.model trumpet_ircam.ts
```

## Specifications

| | |
|---|---|
| Sample rate (`get_sr`) | 44100 Hz |
| Segment length (`get_seglen`) | 14700 samples (333 ms, latency floor) |
| Classes | 14 |
| Parameters | 405,114 |
| Architecture | `BaseNetCfg` |
| Front-end | three log-mel spectrograms: n_fft 512 / 1024 / 2048, hop 512, 128 mel bands, f_min 20 Hz |
| Output | logits `(batch, 14)`, batched forward supported |
| Forward pass | 1.9 ms (Apple Silicon, CPU, 1 thread) |
| Exported with | TorchScript, loads with torch 2.4.1 |
| Size | 2.6 MB |
| SHA-256 | `8fcbbd4932ef75de776f8a1e15b9f79a4c927d2fb80dd2928e94fc3576d410a0` |

## Classes

Index as output by `ipt~` (left outlet) and column order in `pipo.ipt`.

| Index | Class |
|---|---|
| 0 | `brassy` |
| 1 | `double-sound` |
| 2 | `glissando` |
| 3 | `legato` |
| 4 | `multiphonics` |
| 5 | `noise` |
| 6 | `ordinario` |
| 7 | `palm-mouthpiece` |
| 8 | `percussive-valves` |
| 9 | `slap-marcato` |
| 10 | `slap-tongue-ram` |
| 11 | `squeaky-noise` |
| 12 | `staccato` |
| 13 | `trill` |

## Notes

+ Same architecture as [`trumpet_harmon_ircam`](trumpet_harmon_ircam.md); `brassy` is replaced there by `ordinario-forte`.

## Training

Dataset: T-IPT (not publicly available yet)
<!-- TODO: ipt_recognition commit / config used -->
<!-- TODO: evaluation metrics (accuracy, macro F1, ...) -->
