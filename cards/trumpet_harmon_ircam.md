# trumpet_harmon_ircam

Trumpet with harmon mute playing-technique classifier, 14 classes.

File: [`trumpet_harmon_ircam.ts`](https://huggingface.co/nbrochec/ipt_models/resolve/main/trumpet_harmon_ircam.ts)

```
ipt~ trumpet_harmon_ircam.ts
pipo~ ipt @ipt.model trumpet_harmon_ircam.ts
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
| Forward pass | 2.0 ms (Apple Silicon, CPU, 1 thread) |
| Exported with | TorchScript, loads with torch 2.4.1 |
| Size | 2.6 MB |
| SHA-256 | `0e9083715dc1596f5c16e987c3c63afdc2c11f731c5c8f807268bb8d52fe630d` |

## Classes

Index as output by `ipt~` (left outlet) and column order in `pipo.ipt`.

| Index | Class |
|---|---|
| 0 | `double-sound` |
| 1 | `glissando` |
| 2 | `legato` |
| 3 | `multiphonics` |
| 4 | `noise` |
| 5 | `ordinario` |
| 6 | `ordinario-forte` |
| 7 | `palm-mouthpiece` |
| 8 | `percussive-valves` |
| 9 | `slap-marcato` |
| 10 | `slap-tongue-ram` |
| 11 | `squeaky-noise` |
| 12 | `staccato` |
| 13 | `trill` |

## Notes

+ Same architecture as [`trumpet_ircam`](trumpet_ircam.md); `ordinario-forte` replaces `brassy`.

## Training

Dataset: T-IPT (not publicly available yet)
<!-- TODO: ipt_recognition commit / config used -->
<!-- TODO: evaluation metrics (accuracy, macro F1, ...) -->
