Here is a **complete, GitHub-style README** tailored to your repository, explicitly covering both **gromit (atomistic)** and **martinate (coarse-grained)**, with a structure that is clear for users, reviewers, and collaborators.

***

# GROMIT & MARTINATE

**Automated workflows for atomistic and coarse-grained molecular dynamics simulations**

***

## Overview

This repository provides two complementary workflows for setting up and running molecular dynamics (MD) simulations using **GROMACS**:

* **gromit** – automated pipeline for **atomistic simulations**
* **martinate** – automated pipeline for **coarse-grained simulations** using the **MARTINI force field**

Both tools implement standardized simulation protocols that guide the user through all stages of MD setup and execution, enabling **reproducible and comparable simulations across systems**. [\[github.com\]](https://github.com/marrink-lab/gromit)

***

## Motivation

MD simulations involve a complex but well-defined sequence of steps:

* structure preparation
* topology generation
* system building (solvent, ions, box)
* energy minimization
* equilibration
* production simulation

Despite this complexity, these steps follow **established best practices**.  
GROMIT and MARTINATE provide **automation and consistency**, reducing manual intervention and minimizing user-dependent variability.

***

## Workflows

### 1. gromit (atomistic MD)

`gromit` is a shell-based workflow that automates a full atomistic MD simulation pipeline.

Typical stages include:

1. Topology generation from input structure
2. Definition of simulation box and boundary conditions
3. Vacuum energy minimization
4. Solvation and ion addition
5. Energy minimization in solvent
6. Position-restrained equilibration (NVT)
7. Pressure equilibration (NPT)
8. Preproduction equilibration
9. Production MD simulation [\[github.com\]](https://github.com/marrink-lab/gromit/blob/master/gromit.sh)

The workflow can be run end-to-end or partially, enabling flexible use in different contexts.

***

### 2. martinate (coarse-grained MD)

`martinate` extends the same philosophy to **coarse-grained simulations** based on the **MARTINI force field**:

* automates conversion and setup of CG systems
* integrates with MARTINI-compatible tools and force fields
* supports efficient simulation of larger systems and longer timescales

Coarse-graining reduces system complexity by grouping atoms into effective beads, enabling simulations at larger spatial and temporal scales than atomistic MD.

***

## Key Features

* ✅ End-to-end automation of MD workflows
* ✅ Standardized and reproducible protocols
* ✅ Consistent treatment across multiple systems
* ✅ Modular execution (run selected steps only)
* ✅ Support for both atomistic and coarse-grained simulations
* ✅ Designed for comparative studies (e.g. mutations, variants, ligand effects)

***

## Typical Use Cases

* Comparative protein dynamics (e.g. mutation effects, drug resistance)
* Large-scale simulation campaigns
* Multiscale simulations (atomistic ↔ coarse-grained)
* Integration of MD with experimental data
* Educational and training workflows

***

## Requirements

* **GROMACS** (tested with commonly used versions; newer versions recommended)
* Standard Unix/Linux shell environment
* Optional: external tools depending on workflow (e.g. MARTINI ecosystem for CG simulations)

***

## Installation

Clone the repository:

```bash
git clone https://github.com/Tsjerk/gromit.git
cd gromit
```

Ensure that:

* GROMACS is available in your `PATH`
* required environment variables are set (see script headers if needed)

***

## Basic Usage

Run an atomistic workflow:

```bash
./gromit.sh -f input.pdb
```

Run a coarse-grained workflow:

```bash
./martinate.sh -f input.pdb
```

Run only part of the workflow:

```bash
./gromit.sh -f input.pdb -step EMVACUUM -stop NPT
```

(Actual options may vary; see script headers for full usage details.)

***

## Philosophy

GROMIT and MARTINATE follow a simple principle:

> **Make best-practice MD workflows reproducible, consistent, and accessible without hiding the underlying physics.**

The scripts are:

* explicit (transparent command-level execution)
* flexible (modifiable pipelines)
* educational (structured and documented)

***

## Citation

If you use this workflow, please cite:

> Wassenaar, T.A.  
> *GROMIT: A reproducible MD simulation workflow*  
> Zenodo. <https://doi.org/10.5281/zenodo.20446756>

***

## Status and Development

* Actively used in research workflows
* Designed to accompany both **application studies** and **methodological developments**
* Further methodological details and extensions will be described in associated publications

***

## License

This project is licensed under the terms included in the repository (see `LICENSE`).

***

## Acknowledgements

Developed by  
**Tsjerk A. Wassenaar**  
University of Groningen

Built around the GROMACS simulation engine and the MARTINI coarse-grained framework.
