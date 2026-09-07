## FP16 vs FP32 (paired, n=300)

| Condition | FP32 WER | FP16 WER | Δ | p |
|---|---|---|---|---|
| English | 0.004 | 0.009 | +0.005 | 0.18 |
| Hindi | 0.229 | 0.242 | +0.013 | 0.47 |
| Hinglish (mixed) | 0.382 | 0.360 | −0.022 | 0.13 |
| Hinglish (romanized) | 0.595 | 0.591 | −0.003 | 0.88 |

No significant quality change in any condition (Wilcoxon 
signed-rank). FP16 does not disproportionately affect Indic 
or code-mixed speech.

### Speed

| | RTF | Synthesis time |
|---|---|---|
| FP32 | 4.60 | ~24 s |
| FP16 | 0.62 | ~3.3 s |

7.5x speedup, uniform across all four conditions. FP16 crosses 
the real-time threshold (RTF < 1); FP32 does not.

FP16 uses autocast (fp32 weights, fp16 compute) — pure .half() 
fails on XTTS-v2 due to internally-constructed fp32 tensors.

## Status
- [x] FP32 baseline
- [x] FP16
- [ ] INT8
- [ ] INT4
