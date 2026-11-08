# HF_Leaderboard_Lab_Results

**Project:** `K_OSINTGPT`  
**Tier:** `TIER_6_SECURITY_EVAL`  
**Slug:** `soxoj/maigret`  
**Commit:** `b6642744988e`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **42.25 ms** |
| Min latency | 38.76 ms |
| Max latency | 48.48 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **35** |
| Tokenization latency | 1.0 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5855 |
| Classification latency | 65.99 ms |
| Status | **PASS** |

**Input text tokenized:**
```
K_OSINTGPT (soxoj/maigret) — 189 files, 21418 source lines, licence MIT, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'k', '_', 'os', '##int', '##gp', '##t', '(', 'sox', '##oj', '/', 'mai', '##gre', '##t', ')', '—', '189', 'files', ',', '214']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_