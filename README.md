# Guillem Barea

### Research Engineer · Scientific ML for physics simulation

I build and test machine-learning surrogates for expensive physics simulations, and I generate the multi-TB simulation data they are checked against. PhD (cum laude) in data-driven fluid mechanics from [UPC BarcelonaTech](https://www.upc.edu/en); I currently lead the technical work of an ERC-funded Proof of Concept with a team of seven.

What I care about: knowing **where a model holds up and where it breaks** (held-out operating conditions, physical constraints, documented negative results), and shipping that as tested, reproducible code other people can run.

**Open to** Applied Scientist, Research Scientist and Scientific ML Engineer roles where physics meets ML (simulation surrogates, engineering design, energy, aerospace, climate). Based in Barcelona, open to hybrid or remote.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-guillem--barea-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guillem-barea)
[![Email](https://img.shields.io/badge/Email-contact-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:guillembarea.s@gmail.com)
[![Data](https://img.shields.io/badge/Open_data-DNS_database-4A90D9?style=flat&logo=figshare&logoColor=white)](https://doi.org/10.25452/figshare.plus.29787812.v1)

---

## Featured work

### [METIS](https://github.com/gbareas/METIS): ML engine for high-fidelity simulation data

[![CI](https://github.com/gbareas/METIS/actions/workflows/ci.yml/badge.svg)](https://github.com/gbareas/METIS/actions/workflows/ci.yml)

A tested Python framework that turns multi-GB direct numerical simulation output of supercritical-CO₂ flow into validated physics features, reproducible ML experiments and reports, with a small agent that decides when a fast neural-operator surrogate can be trusted and when to fall back to the full simulation.

<a href="https://github.com/gbareas/METIS"><img src="https://raw.githubusercontent.com/gbareas/METIS/main/docs/summary.png" alt="METIS: regime recovery from physics features (left) and out-of-distribution routing between surrogate and DNS (right)" width="760"></a>

- Validated HDF5 ingestion, leakage-safe preprocessing, cached feature datasets and MLflow tracking behind one `metis` CLI.
- Out-of-distribution routing: the surrogate is trusted only inside its validated envelope; an LLM explains the decision but never makes it.
- Honest results: a frozen regression benchmark, plus two documented negative results where autoencoders did not beat linear PCA/POD.
- ~250 tests, CI on every push, and a one-command Docker demo that needs no data, GPU or API key.

`Python` · `PyTorch` · `scikit-learn` · `MLflow` · `HDF5` · `Docker` · `GitHub Actions`

### [braindance](https://github.com/gbareas/braindance): publication-ready figures, checked against their data

<a href="https://github.com/gbareas/braindance"><img src="https://raw.githubusercontent.com/gbareas/braindance/main/docs/banner.jpg" alt="braindance banner" width="760"></a>

A house style for scientific figures (LaTeX text, journal column widths, colourblind-safe colours, vector PDF) plus measured checks that compare what is drawn with the data file it came from. Works as a Python package and as a Claude Code plugin with a skill and a reviewer agent.

`Python` · `matplotlib` · `pytest` · `Claude Code plugin`

### [ripperdoc](https://github.com/gbareas/ripperdoc): a research-supervisor agent for Claude Code

<a href="https://github.com/gbareas/ripperdoc"><img src="https://raw.githubusercontent.com/gbareas/ripperdoc/main/docs/banner.jpg" alt="ripperdoc banner" width="760"></a>

Questions results and experiment designs before anyone trusts them. It traces each key number to the code line and equation that produce it, recomputes in a read-only sandbox when needed, and returns an accept / revise / reject verdict with a schema-validated review. It never edits the work it reviews.

- Two-reviewer ensemble on different models; blocking issues are merged as a union, never averaged.
- Guard hook and sandbox: writes only to its review folder, runs code with the filesystem read-only and no network.
- An eval suite of 10 small research results (7 with a planted flaw, 3 clean) measures what it catches and checks it never reruns expensive pipelines without permission.

`Claude Code agent` · `Python` · `JSON Schema` · `bubblewrap sandbox`

### More open source

| Project | What it does |
|---|---|
| [RHEA_to_POD](https://github.com/gbareas/RHEA_to_POD) | Proper Orthogonal Decomposition (PCA/SVD) of large simulation datasets: spatial modes, energies and temporal coefficients. |
| [RHEA_to_SPOD](https://github.com/gbareas/RHEA_to_SPOD) | Spectral POD (Welch + frequency-domain decomposition) to separate coherent structures by frequency. |
| [HP_thermodynamics_tools](https://github.com/gbareas/HP_thermodynamics_tools) | Thermodynamic post-processing for high-pressure simulations, e.g. reconstructing a consistent pressure field from an equation of state. |

---

## Research

- **PhD in three years** at UPC BarcelonaTech on data-driven analysis of high-pressure transcritical turbulence.
- **3 first-author Q1 papers** (Physical Review Fluids, Physics of Fluids) and 3 co-authored.
- **Multi-TB simulation campaigns** on GPU and Barcelona Supercomputing Center infrastructure; ported an in-house C++ solver to GPUs (OpenACC, CUDA).
- **Open data:** the [Minimal Flow Unit Database of High-Pressure Transcritical Fluid Turbulence](https://doi.org/10.25452/figshare.plus.29787812.v1), included in the BLASTNet ecosystem.
- **Now:** benchmarking neural-operator architectures (FNO, WNO, DeepONet, U-Net) as surrogates for near-critical flows.

---

## Toolbox

**ML and modelling:** PyTorch · scikit-learn · MLflow · neural operators · autoencoders · PCA/POD/SPOD · time-series · OOD evaluation

**Scientific computing:** Python · NumPy · SciPy · pandas · HDF5 · C++ · MPI · OpenACC/CUDA · HPC clusters

**Engineering:** Linux · Git · Docker · GitHub Actions · pytest · Bash · Claude Code (skills, agents, plugins)
