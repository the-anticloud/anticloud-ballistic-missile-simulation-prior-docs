# Build and Test

**Project:** `BALLISTIC_MISSILE_SIMULATION`
**Upstream:** https://github.com/CFP106020008/Ballistic_Missile_Simulation
**License:** MIT

## Quick Start

```bash
git clone https://github.com/CFP106020008/Ballistic_Missile_Simulation
cd Ballistic_Missile_Simulation
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local ballistics modeling and tolerancing — air-gapped
2. AIOSS tamper-evident manufacturing log for every part (ITAR/EAR traceability)
3. AES-256 encryption for all design files and production records
4. Single-binary MES deployment on hardened manufacturing floor hardware
5. Zero-cloud: no design data leaves the secure facility
6. Offline quality control inference using local vision model
7. GPU/CPU equalizer: simulation runs on workstation GPU or CPU server
8. Open CLI replacing proprietary MES interfaces

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
