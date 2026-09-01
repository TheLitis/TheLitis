<div align="center">

# TheLitis

### Research-focused developer working across ML systems, GPU computing and scientific machine learning

I build and test systems where **correctness, measurement and reproducibility matter** — from CUDA memory runtimes and inverse problems to agentic architectures and developer tools.

**Current interests:** GPU memory systems · scientific ML · model evaluation · agentic systems · systems programming

<sub>Python · C++20 · Rust · TypeScript · CUDA · PyTorch</sub>

[Research](#selected-research) · [Engineering](#engineering-work) · [Research approach](#research-approach) · [Contact](#contact)

</div>

---

## Selected research

### xVRAM — software-managed tiered CUDA memory

**[xVRAM](https://github.com/TheLitis/xVRAM)** is an experimental runtime for workloads whose total data exceeds physical GPU memory while their active working set can still fit in VRAM.

The project treats system RAM as a backing tier and physical VRAM as a bounded write-back residency tier. Current work includes:

- stable CUDA virtual addresses through CUDA VMM;
- event-safe residency and eviction;
- bounded pinned staging pools and asynchronous transfers;
- WDDM-aware live memory budgeting;
- cost-aware cache policy;
- a versioned C ABI;
- library-aware tiled GEMM with cuBLAS/cuBLASLt;
- deterministic correctness checks and machine-readable benchmark reports.

The goal is not to pretend that RAM is as fast as VRAM, but to investigate when explicit residency, reuse and scheduling can make otherwise out-of-memory workloads executable.

**C++20 · CUDA Driver API · CUDA VMM · cuBLAS/cuBLASLt · CMake**

---

### PIMSR — scientific ML for geophysical inversion

PIMSR is a multi-repository research project on neural inversion of magnetotelluric and gravity observations.

| Repository | Role |
| --- | --- |
| [pimsr-geogen](https://github.com/TheLitis/pimsr-geogen) | stochastic geological model generation |
| [pimsr-forward](https://github.com/TheLitis/pimsr-forward) | forward modelling, sensors, noise and dataset generation |
| [pimsr-inversion](https://github.com/TheLitis/pimsr-inversion) | multi-task neural inversion and uncertainty estimation |
| [pimsr-benchmarks](https://github.com/TheLitis/pimsr-benchmarks) | reproducible comparisons against classical and research methods |

A large part of the project is now about **benchmark validity itself**: separating diagnostic results from publishable claims, pinning implementations and datasets, preventing unequal observation budgets, and rejecting comparisons when the protocol is not strong enough.

Earlier Yellowstone headline numbers are retained only as legacy provenance and are **not used as evidence of current superiority**. The current benchmark work is deliberately fail-closed until the physical-geometry and equal-budget protocol is satisfied.

**PyTorch · inverse problems · scientific computing · uncertainty · reproducible benchmarking**

---

### Structured latent hypothesis — testing and closing a failed claim

**[structured-latent-hypothesis](https://github.com/TheLitis/structured-latent-hypothesis)** began with a geometric hypothesis about mixed-difference structure in latent representations.

The original global claim did not survive stronger baselines. Instead of preserving it, the repository documents why it failed and narrows the active question to:

> **support-calibrated adaptive routing under context shift**

The current work asks whether a small target-domain support set can safely choose between structured transfer, fallback adaptation and escalation — and only treats the mechanism as useful if it beats simpler policies under the same calibration and holdout protocol.

This project is intentionally kept public as a record of the research process, including negative results and a change of direction.

---

### Kairos — constrained agentic architecture

I lead the architecture and implementation of **Kairos**, a multi-repository trading-system project in the [Kairos-cryptoAI](https://github.com/Kairos-cryptoAI) organisation.

The research/engineering question is how much authority an LLM should receive in a system where mistakes can have irreversible consequences.

The architecture therefore separates:

**quantitative signals → routing → aggregation → strategy → deterministic risk control → execution**

Language models operate on compact validated representations, while leverage limits, drawdown protection, circuit breakers and order execution remain deterministic and outside the model's direct control.

The project also explores model-routing cost, backtesting, persistence, auditability and graceful degradation under API failure.

---

## Engineering work

### ProtoSwitch

**[ProtoSwitch](https://github.com/TheLitis/ProtoSwitch)** is a Rust-based proxy watcher and rotator for Telegram Desktop with managed settings integration, TUI/tray interfaces, deterministic end-to-end tests, CI packaging and portable Windows/Linux/macOS builds.

### Training Dashboard Demo

**[Training-Dashboard-Demo](https://github.com/TheLitis/Training-Dashboard-Demo)** is a reproducible PyTorch/CIFAR-10 pipeline built around the full experiment chain:

`config → train → evaluate → metrics → artifacts → report`

It includes baseline/improved runs, checkpoints, plots, reports and automated tests.

### Lower-level and exploratory work

Other repositories include work with:

- x86-64 Linux assembly;
- PySpark and data processing;
- Telegram and Discord bots;
- React/Electron applications;
- networking utilities;
- ML experiments and evaluation tooling;
- game-development prototypes.

---

## Research approach

I use GitHub not only as a code portfolio, but as a **research log**.

A few principles I try to follow:

- **A claim should be falsifiable.** If stronger evidence disproves it, the repository should say so.
- **Benchmarks are part of the research.** A faster number is meaningless if the comparison is not controlled.
- **Negative results are useful results.** Failed hypotheses should remain documented when they explain what was learned.
- **Systems constraints matter.** Memory hierarchy, latency, API failure, numerical behavior and deployment cost are part of the problem, not implementation details to ignore.
- **Reproducibility beats presentation.** I prefer explicit protocols, machine-readable artifacts and deterministic tests over impressive but hard-to-verify demos.

---

## Technical stack

**Languages**  
Python · C++ · Rust · TypeScript/JavaScript · SQL · x86-64 Assembly

**ML / Compute**  
PyTorch · CUDA · cuBLAS/cuBLASLt · NumPy · OpenCV · PySpark

**Systems / Infrastructure**  
CMake · Docker · GitHub Actions · PostgreSQL · SQLite · Windows · Linux

---

<div align="center">

## Contact

[Telegram](https://t.me/Lindortis) · [Discord](https://discordapp.com/users/the_litis)

</div>
