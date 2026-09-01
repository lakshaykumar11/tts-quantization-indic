# Quantization and Multilingual TTS

Measuring how post-training weight quantization degrades TTS 
quality differently across English, Hindi, and code-mixed 
(Hinglish) speech.

## Setup
- TTS: XTTS-v2 (coqui-tts fork)
- ASR: Whisper large-v3
- Hardware: Tesla T4 (Colab)

## Test set
200 sentences: 50 EN, 50 HI (parallel translations), 
100 Hinglish in both mixed-script and romanized form.
CMI computed per sentence; three mixing levels (mean 11 / 24 / 41).

## Status
- [x] Pipeline + scoring
- [x] Test set built and validated
- [x] Pilot: language tag selection
- [ ] FP32 baseline (300 rows)
- [ ] Quantized runs (FP16 / INT8 / INT4)

## Notes
Whisper transcribes to Devanagari regardless of input script, 
so romanized references need script-neutral comparison. Naive WER 
reports total failure on intelligible output.
