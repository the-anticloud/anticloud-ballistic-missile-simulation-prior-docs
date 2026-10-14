# Ethics — BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS

**Project:** BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** https://github.com/CFP106020008/Ballistic_Missile_Simulation  
**Pinned commit:** `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `0efa99f4c434bffcc576ceab813ba5d7375c0fd39a965ba27d8f599a0b416ce8`  
**Date:** October 2026

## Position

BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
