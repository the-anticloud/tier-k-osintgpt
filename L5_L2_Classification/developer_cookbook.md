# Developer Cookbook — K_OSINTGPT
**Stack:** Python 3.11, PAX 27B, whois, shodan-free (local scan), AIOSS_FORMAT
**Domain:** OSINT-GPT: open-source intelligence gathering assistant powered by PAX 27B

## Authorized OSINT scan
```python
from k_osintgpt import OSINTAssistant

osint = OSINTAssistant(
    pax_model="./pax-27b-q4.gguf",
    scope=["192.168.1.0/24"],  # internal authorized scope only
    aioss_chain="./osint.aioss"
)

report = osint.gather_and_analyze(
    target="192.168.1.100",
    sources=["whois", "port_scan", "service_banner"]
)
print(f"Open ports: {report.open_ports}")
print(f"Risk level: {report.overall_risk}")
print(f"PAX analysis: {report.pax_summary}")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
