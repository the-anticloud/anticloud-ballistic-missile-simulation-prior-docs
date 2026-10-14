# Educators — BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS

**Project:** BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** https://github.com/CFP106020008/Ballistic_Missile_Simulation  
**Pinned commit:** `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `0efa99f4c434bffcc576ceab813ba5d7375c0fd39a965ba27d8f599a0b416ce8`  
**Date:** October 2026

## Teaching with BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `0efa99f4c434bffcc576ceab813ba5d7375c0fd39a965ba27d8f599a0b416ce8` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
