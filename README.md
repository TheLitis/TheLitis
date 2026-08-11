Physics-informed machine learning for geophysical inverse problems.
Python, C++, Rust, TypeScript.

---

### PIMSR — physics-informed subsurface reconstruction

Neural inversion of magnetotelluric and gravity data, trained on simulated
geology and evaluated against the two most-used production MT inversion codes
on 27 real USArray/EMTF stations in the Yellowstone region
(42.5–45.5°N, 108.5–113°W).

Shift-invariant 2D-forward data misfit (`section_nrms_2d`, lower is better):

| Profile | ModEM NLCG | Occam2DMT v3.0 | PIMSR U-Net |
| --- | --- | --- | --- |
| G | 5.32 | 3.92 | **3.59** |
| H-YS | 5.90 | 4.68 | **4.10** |
| I | 10.98 | 9.26 | **5.62** |
| J | 6.28 | 6.40 | **3.49** |
| K | 6.99 | 6.03 | **4.69** |
| mean | 7.09 | 6.06 | **4.30** |

The neural model wins on every profile against both baselines while using
roughly four orders of magnitude less compute — milliseconds per profile
against 5–210 seconds. Both baselines were compiled from official sources and
driven by scripts inside the benchmark repository, so the comparison is
reproducible end to end. Methodology changes and negative results are recorded
in the report, including a misfit metric that was retired once it was shown to
be an artifact.

| Repository | Role |
| --- | --- |
| [pimsr-geogen](https://github.com/TheLitis/pimsr-geogen) | stochastic geology model generator |
| [pimsr-forward](https://github.com/TheLitis/pimsr-forward) | MT and gravity forward modeling, sensor and noise simulation, dataset builder |
| [pimsr-inversion](https://github.com/TheLitis/pimsr-inversion) | multi-task neural inversion with uncertainty estimates |
| [pimsr-benchmarks](https://github.com/TheLitis/pimsr-benchmarks) | comparison against Occam2DMT, ModEM and SimPEG, plus the full result report |

---

### structured-latent-hypothesis

Kept as a record of a hypothesis that did not survive testing. It started from a
three-point geometric observation and asked whether the resulting
mixed-difference structure could serve as a machine learning principle. The
global claim is closed as unsupported: strict affine spacing did not hold, the
latent prior did not generalise, and commutator routing lost to simpler
support-validation baselines. The work has since narrowed to support-calibrated
adaptive routing under context shift.

[structured-latent-hypothesis](https://github.com/TheLitis/structured-latent-hypothesis)

---

### Other work

- [ProtoSwitch](https://github.com/TheLitis/ProtoSwitch) — terminal-first proxy
  watcher and rotator for Telegram Desktop, written in Rust
- [asm-atoi-exit-code](https://github.com/TheLitis/asm-atoi-exit-code) — x86-64
  Linux assembly, written while learning the instruction set directly
- Kairos — private research on historical backtesting and counterfactual
  experiment matrices for trading strategies

---

### Contact

[Telegram](https://t.me/Lindortis) · [Discord](https://discordapp.com/users/the_litis)
