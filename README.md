## FP32 baseline (300 rows, Tesla T4)

| Condition | WER | CER |
|---|---|---|
| English | 0.004 | 0.004 |
| Hindi | 0.229 | 0.096 |
| Hinglish (mixed script) | 0.382 | 0.213 |
| Hinglish (romanized) | 0.595 | 0.198 |

All pairwise differences significant: EN→HI p=1.1e-17, 
HI→MIX p=1.9e-03, MIX→ROM p=1.9e-12.

Sentences with at least one error: EN 2/50, HI 47/50, 
MIX 95/100, ROM 100/100.

CMI showed no correlation with baseline WER 
(HING_MIX r=0.156, p=0.12; HING_ROM r=0.030, p=0.77). 
The trend observed in the 6-sentence pilot did not 
survive at n=100.

## Status
- [x] Pipeline, scoring, test set
- [x] Pilot: language tag selection
- [x] FP32 baseline
- [ ] FP16
- [ ] INT8
- [ ] INT4
