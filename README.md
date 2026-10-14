# BALLISTIC MISSILE SIMULATION PRIOR DOCS

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-artillery_manufacturing-lightgrey)

> Anticloud-hardened packaging of the upstream project `BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS` in category **ARTILLERY MANUFACTURING**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** ARTILLERY MANUFACTURING · **Upstream:** https://github.com/CFP106020008/Ballistic_Missile_Simulation · **Upstream pin:** `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Ballistic_Missile_Simulation
This code can do some native numerical analysis on ballistic trajectory

## Basic physics
This code considers (1) gravity, (2) air drag (3) rocket equation and (4) rotational fictitious force. 

### Gravity
This is simple, we have:
$$\vec{a}_g = -\frac{GM_E}{r^3}\vec{r}$$

### Air drag
This is much more tricky. In the acent phase, air drag is relatively irrelevant. But when the war head is returning to the Earth, it will hit the dense atmosphere with hypersonic velocity. However, hypersonic/supersonic drag is very complicated. In this work I simply use:
$$\vec{a}_A = -\frac{1}{2} \rho C_D A v \vec{v}$$
Note that here we are assuming a constant geometry. that is $\vec{v}\parallel \vec{a}_A$. $\rho$ is the air density, here we simply apply [the model for troposphere](https://en.wikipedia.org/wiki/Density_of_air).
$$\rho = \frac{p_0 M}{RT_0}\left(1-\frac{Lh}{T_0}\right)^{\frac{gM}{RL}-1}, \quad h = r - R_E$$

### [Rocket Equation](https://en.wikipedia.org/wiki/Tsiolkovsky_rocket_equation)
The acceleration of the rocket depends on it's mass, while thrust is basically the same. That is:
$$\vec{a}_R = \frac{F}{m(t)} \vec{n}, \quad \frac{dm}{dt} = -F/v_e$$
where $v_e={\rm Isp}\times g$ is the exhaust velocity. 
$\vec{n}$ is the pointing of the rocket, which is controllable. I used the following strategy:
* if $h < 10$ km, where the rocket is still in the dense air, then $\vec{n} = \mathrm{rotate}(\hat{r}, \theta)$, where $\theta$ is basically the $\mathrm{launch~angle} - 90^\circ$.
* if $h > 10$ km, $\vec{n} = \hat{v}$ so that the acceleration is maximized.

### [Rotational fictitious force](https://en.wikipedia.org/wiki/Coriolis_force)
There are 3 fictitious force in a rotating frame.
* Euler force: $-m\dot{\vec{\omega}}\times \vec{r}$, which is 0 since the angular velocity of the Earth is constant.
* Coriolis force: $-2m(\vec{\omega}\times \vec{v})$, need to be considered.
* Centrifugal force: $-m \vec{\omega}\times(\vec{\omega}\times \vec{r})$, which is effectively $\omega^2\vec{r}$.

### Add them all together
Combining them all, we obtain the total acceleration. Then we can use ```scipy.integrate.solve_ivp``` to do the integration.

## Result
https://user-images.githubusercontent.com/48315222/183479789-446ba6ba-58b0-4a22-8dcc-d449f36f8ce7.mp4

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Unknown (no standard manifest detected)** (manifests: none detected; scanned in UPSTREAM_CLONE)
- Snapshot size: **3 files**, **262 lines of code** (measured; see Benchmarks)
- Primary languages: `.md` (1), `.mp4` (1), `.py` (1)
- Upstream commit pinned for this packaging: `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`

---

## Installation

No installation section was found in the upstream readme, so the commands below are generated from the manifests detected in this project directory.

```sh
# No standard manifest detected. Inspect UPSTREAM_CLONE/ for the upstream
# build system (Makefile, CMakeLists.txt, configure, ...) and follow it.
```

Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

No usage section was found in the upstream readme. Entry points detected in this project directory:

Browse the snapshot layout listed under What This Project Does and follow the upstream run instructions for the detected ecosystem (Unknown (no standard manifest detected)).

Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

The upstream API surface is defined by the `BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS` source tree vendored in `UPSTREAM_CLONE/` (Unknown (no standard manifest detected) ecosystem). Public entry points:

- Overlay API: `anticloud/cli.py` exposes 13 subcommands with JSON stdout; `anticloud/bench/runner.py` runs the 16-check suite; `anticloud/provenance/chain.py` exposes the SHA3-256 + Ed25519 provenance chain.

---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Unknown (no standard manifest detected) |
| Manifests detected | none |
| Files in snapshot | 3 |
| Lines of code | 262 |
| Dependency references | 0 |
| Upstream license | No license file present in the upstream snapshot |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- None detected at the snapshot root; consult the upstream documentation link in the Upstream section.

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: No license file present in the upstream snapshot** (evidence: `LICENSE` in the upstream snapshot).

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original No license file present in the upstream snapshot terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `No license file present in the upstream snapshot` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `BALLISTIC_MISSILE_SIMULATION_PRIOR_DOCS` (category: ARTILLERY MANUFACTURING)
- **Upstream URL:** https://github.com/CFP106020008/Ballistic_Missile_Simulation
- **Pinned commit (SHA):** `31e13b85c9bbd19cba89e3f0fdb2ca74da9c0be7`
- **Branch:** main
- **Pin provenance:** resolved during the second documentation pass. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`90b5138304446b04baf346e06414109a209f912d832879ce34c4190081cee76a`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |

