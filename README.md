<div align="center">

## TheLitis

**Physics-informed machine learning for geophysical inverse problems**

LLM systems constrained by deterministic guarantees

<sub>Python · C++ · Rust · TypeScript</sub>

**[PIMSR](#pimsr) · [Kairos](#kairos) · [Closed work](#closed-work) · [Contact](#contact)**

</div>

---

## PIMSR

*Neural inversion of magnetotelluric and gravity data, evaluated against the two
most-used production MT inversion codes on real USArray stations.*

> [!IMPORTANT]
> Wins **all five** Yellowstone profiles against both ModEM NLCG and
> Occam2DMT v3.0, at roughly **four orders of magnitude** less compute —
> milliseconds per profile against 5–210 seconds.

Shift-invariant 2D-forward data misfit, `section_nrms_2d`, lower is better:

<div align="center">

| Profile | ModEM NLCG | Occam2DMT v3.0 | PIMSR U-Net |
| :--- | :---: | :---: | :---: |
| G | 5.32 | 3.92 | **3.59** |
| H-YS | 5.90 | 4.68 | **4.10** |
| I | 10.98 | 9.26 | **5.62** |
| J | 6.28 | 6.40 | **3.49** |
| K | 6.99 | 6.03 | **4.69** |
| **mean** | 7.09 | 6.06 | **4.30** |

</div>

<details>
<summary><b>Setup and reproducibility</b></summary>

<br>

Trained on simulated geology, then evaluated on 27 real USArray/EMTF stations in
the Yellowstone region (42.5–45.5°N, 108.5–113°W) — no field data in training.

Both baselines were compiled from official sources and driven by scripts inside
the benchmark repository, so the comparison is reproducible end to end.
Methodology changes and negative results are recorded in the report, including a
misfit metric that was retired once it was shown to be an artifact.

</details>

<details>
<summary><b>Repositories</b></summary>

<br>

| Repository | Role |
| :--- | :--- |
| [pimsr-geogen](https://github.com/TheLitis/pimsr-geogen) | stochastic geology model generator |
| [pimsr-forward](https://github.com/TheLitis/pimsr-forward) | MT and gravity forward modeling, sensor and noise simulation, dataset builder |
| [pimsr-inversion](https://github.com/TheLitis/pimsr-inversion) | multi-task neural inversion with uncertainty estimates |
| [pimsr-benchmarks](https://github.com/TheLitis/pimsr-benchmarks) | comparison against Occam2DMT, ModEM and SimPEG, plus the full report |

</details>

---

## Kairos

*Architecture, specification and implementation of a seven-layer trading system
I lead across thirteen repositories in the
[Kairos-cryptoAI](https://github.com/Kairos-cryptoAI) organisation.*

The design question is how much authority a language model can be given in a
system where mistakes are irreversible.

> [!IMPORTANT]
> The answer is enforced structurally rather than by prompt: **the model never
> touches the exchange and never sees a raw number stream.** It receives compact
> pre-validated JSON, every critical action passes deterministic risk filters,
> and a separate engine executes.

<div align="center">

| # | Layer | Control |
| :---: | :--- | :--- |
| 1A | [quant-scouts](https://github.com/Kairos-cryptoAI/kairos-quant-scouts) · order book, funding, OI, RSI/MACD | pure math |
| 1B | [text-scouts](https://github.com/Kairos-cryptoAI/kairos-text-scouts) · news/X with local ML pre-filter | LLM, low |
| 2 | [router](https://github.com/Kairos-cryptoAI/kairos-router) · state machine with hysteresis, picks effort | deterministic |
| 3 | [aggregator](https://github.com/Kairos-cryptoAI/kairos-aggregator) · fuses quant and sentiment | LLM, medium/high |
| 4 | [macro-strategist](https://github.com/Kairos-cryptoAI/kairos-macro-strategist) · allocation, shock-triggered | LLM, extra high |
| 5 | [risk-manager](https://github.com/Kairos-cryptoAI/kairos-risk-manager) · leverage and drawdown limits, breaker | deterministic |
| 6 | [execution-engine](https://github.com/Kairos-cryptoAI/kairos-execution-engine) · atomic orders, EIP-712, CCXT | deterministic |

</div>

On failure the system degrades into a local protective mode instead of stopping.

<details>
<summary><b>Cost control and supporting work</b></summary>

<br>

Cost is a first-class constraint: the router stays cheap by default and
escalates to expensive models only when signals conflict, with token accounting
in the [LLM gateway](https://github.com/Kairos-cryptoAI/kairos-llm).

| Repository | Role |
| :--- | :--- |
| [kairos](https://github.com/Kairos-cryptoAI/kairos) | umbrella specification and ADRs |
| [kairos-core](https://github.com/Kairos-cryptoAI/kairos-core) | shared contracts and message bus |
| [kairos-persistence](https://github.com/Kairos-cryptoAI/kairos-persistence) | TimescaleDB storage with audit trail |
| [kairos-backtest](https://github.com/Kairos-cryptoAI/kairos-backtest) | walk-forward and counterfactual experiment matrices |
| [kairos-deploy](https://github.com/Kairos-cryptoAI/kairos-deploy) | deployment and monitoring |

</details>

---

## Closed work

*Kept public as a record of a hypothesis that did not survive testing.*

**[structured-latent-hypothesis](https://github.com/TheLitis/structured-latent-hypothesis)**
started from a three-point geometric observation and asked whether the resulting
mixed-difference structure could serve as a machine learning principle. The
global claim is closed as unsupported: strict affine spacing did not hold, the
latent prior did not generalise, and commutator routing lost to simpler
support-validation baselines. The work has since narrowed to support-calibrated
adaptive routing under context shift.

<details>
<summary><b>Other repositories</b></summary>

<br>

- **[Training-Dashboard-Demo](https://github.com/TheLitis/Training-Dashboard-Demo)**
  — reproducible CIFAR-10 pipeline, config to report, with a baseline/improved ablation
- **[ProtoSwitch](https://github.com/TheLitis/ProtoSwitch)**
  — terminal-first proxy watcher and rotator for Telegram Desktop, in Rust
- **[asm-atoi-exit-code](https://github.com/TheLitis/asm-atoi-exit-code)**
  — x86-64 Linux assembly, written while learning the instruction set directly

</details>

---

<div align="center">

## Contact

[Telegram](https://t.me/Lindortis) · [Discord](https://discordapp.com/users/the_litis)

</div>
