# Deploy Guide — K_OSINTGPT
**Tier:** TIER_6_SECURITY_EVAL | **Stack:** Python 3.11, PAX 27B, whois, shodan-free (local scan), AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, PAX 27B, python-whois 0.9+, shodan (free tier). AUTHORIZED USE ONLY.

## Environment
CPU-only for OSINT gathering. GPU for PAX synthesis. AUTHORIZED SCOPE REQUIRED.

## AIOSS Integration
```bash
aioss init --module K_OSINTGPT --output ./k_osintgpt.aioss
aioss append --chain ./k_osintgpt.aioss --payload ./output.bin --module K_OSINTGPT
aioss verify --chain ./k_osintgpt.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="K_OSINTGPT",
    aioss_chain="./K_OSINTGPT.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./K_OSINTGPT.aioss --verbose
python -m K_OSINTGPT.tests.smoke
```
