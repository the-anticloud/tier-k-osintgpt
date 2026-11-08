# L5 Narrow / L2 General Classification — K_OSINTGPT
**Platform:** Anticloud | **Tier:** TIER_6_SECURITY_EVAL | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
K_OSINTGPT uses PAX 27B to assist with authorized OSINT tasks on Anticloud infrastructure: identifying publicly exposed services, misconfigured ports, and data leakage indicators. Narrow scope: Anticloud infrastructure OSINT — not general surveillance tool.

## L2 General
L2 General: K_OSINTGPT assists authorized security teams across all Anticloud deployment tiers in understanding their external exposure footprint.

## PAX 27B Integration
PAX 27B synthesizes OSINT findings into structured reports: given raw scan data, PAX identifies actionable intelligence and prioritizes remediation by risk level.

## AIOSS Audit Chain
Every OSINT query (target hash + data sources hash + findings hash + risk classification + report hash) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
NIST SP 800-53 (intelligence gathering controls). Authorized OSINT use only.
