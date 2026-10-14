# Students — BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS

**Project:** BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** https://github.com/CFP106020008/Ballistic_Missile_Simulation  
**Pinned commit:** `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `0efa99f4c434bffcc576ceab813ba5d7375c0fd39a965ba27d8f599a0b416ce8`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `0efa99f4c434bffcc576ceab813ba5d7375c0fd39a965ba27d8f599a0b416ce8`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
