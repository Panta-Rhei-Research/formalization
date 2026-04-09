<p align="center">
  <strong>Panta Rhei — Formalization</strong><br>
  <em>Frozen Lean 4 Verification of the Panta Rhei Book Series</em>
</p>

<p align="center">
  <a href="https://lean-lang.org"><img src="https://img.shields.io/badge/Lean_4-v4.28.0--rc1-blue" alt="Lean 4"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0-green.svg" alt="License"></a>
  <a href="https://panta-rhei.site"><img src="https://img.shields.io/badge/Panta_Rhei-2nd_Edition-8B4513" alt="Panta Rhei"></a>
</p>

---

This repository contains the **frozen, author-maintained Lean 4 formalization** accompanying the 7-book *Panta Rhei* series (2nd Edition, 2026) by Thorsten Fuchs and Anna-Sophie Fuchs.

**This is a verification archive, not a development workspace.** The code here corresponds exactly to the formalization referenced in the published books. It does not accept pull requests or community contributions.

For the **actively developed, contributor-facing** TauLib package, see: [**github.com/Panta-Rhei-Framework/taulib**](https://github.com/Panta-Rhei-Framework/taulib)

---

## Purpose

When the books say *"formalized in Lean 4 with zero sorry"*, this is the code they reference. Every `#check`, every `#eval`, every theorem cited in the manuscripts compiles against this exact codebase.

The repository serves one purpose: **independent verification**. Clone it, run `lake build`, and confirm that every claim in the books is machine-checked.

---

## At a Glance

| Metric | Value |
|--------|------:|
| Source files | 450 |
| Lines of Lean 4 | 125,771 |
| Theorems & lemmas | 4,332 |
| Definitions | 3,542 |
| Computations (`#eval`) | 3,721 |
| Axioms | 4 (3 conjectural, 1 structural) |
| Sorry | 3 (methodological, Book VII only) |
| Books I&ndash;VI sorry | **0** |

---

## Quick Start

```bash
# Install Lean 4 via elan
curl https://raw.githubusercontent.com/leanprover/elan/master/elan-init.sh -sSf | sh

# Clone and build
git clone https://github.com/Panta-Rhei-Framework/formalization.git
cd formalization
lake build
```

The first build downloads Mathlib (for tactics only) and compiles ~1,261 lake jobs.

---

## Seven Books, One Codebase

| Book | Title | Subtitle | Modules |
|:----:|-------|----------|--------:|
| I | Categorical Foundations | *How Mathematics Is Earned* | 94 |
| II | Categorical Holomorphy | *Finite Readouts of Infinity* | 65 |
| III | Categorical Spectrum | *Where Physics Lives* | 70 |
| IV | Categorical Microcosm | *The Self-Describing Universe* | 89 |
| V | Categorical Macrocosm | *The Biography of the Universe* | 80 |
| VI | Categorical Life | *Life as Self-Decoding Distinctions* | 30 |
| VII | Categorical Metaphysics | *The Final Self-Enrichment* | 7 |

Plus **8 guided tours** and **7 hinge-tour companions** mapping the 49 structural load-bearing points to their formalizations.

---

## Guided Tours

Interactive step-through tours for verifying key claims:

| Tour | What You'll Verify |
|------|--------------------|
| `Tour/VerifyItYourself.lean` | 5 most surprising claims, verified live |
| `Tour/Foundations.lean` | 5 generators, 7 axioms, rigidity |
| `Tour/CentralTheorem.lean` | O(τ³) ≅ A_spec(L) |
| `Tour/Physics.lean` | 9 electroweak predictions |
| `Tour/OneConstant.lean` | Full constants ledger from ι_τ |
| `Tour/MillenniumProblems.lean` | GRH, BSD, Poincaré |
| `Tour/LifeFromPhysics.lean` | Life sectors, genetic code, neural arch |
| `Tour/MindAndEthics.lean` | CI formalization, consciousness, free will |

### Hinge-Tour Companions

Each maps 5–8 structural hinges from the companion whitepapers to their Lean formalization:

| Companion | Hinges | Key Verification |
|-----------|:------:|------------------|
| `Tour/GuidedTour/BookI.lean` | 7 | Axioms, Hyperfactorization, Topos |
| `Tour/GuidedTour/BookII.lean` | 7 | Central Theorem, Categoricity |
| `Tour/GuidedTour/BookIII.lean` | 6 | Canonical Ladder, Bridge Axiom |
| `Tour/GuidedTour/BookIV.lean` | 7 | α = (121/225)ι_τ⁴, mass ratio |
| `Tour/GuidedTour/BookV.lean` | 8 | CMB pipeline, r = ι_τ⁴, no dark matter |
| `Tour/GuidedTour/BookVI.lean` | 7 | Distinction + SelfDesc, Crossing-Limit |
| `Tour/GuidedTour/BookVII.lean` | 7 | CI fixed point, No Forced Stance |

---

## Transparency

### 4 Axioms (all documented)

| Axiom | Location | Type | Finite Check |
|-------|----------|:----:|:------------:|
| `bridge_functor_exists` | BookIII/Bridge | Conjectural | `bridge_functor_check` |
| `grand_grh_adelic` | BookIII/Doors | Conjectural | `grand_grh_finite_check` |
| `spectral_correspondence_O3` | BookIII/Doors | Conjectural | `spectral_correspondence_finite` |
| `central_theorem_physical` | BookIV/Arena | Structural | Proof in Book II |

### 3 Sorry (all methodological)

| Sorry | Location | Why |
|-------|----------|-----|
| `no_forced_stance` | BookVII/Final | Self-referential boundary |
| `omega_point_theorem` | BookVII/Logos | Non-diagrammatic content |
| `science_faith_boundary` | BookVII/Logos | Commitment register content |

No other sorry exists in the entire codebase. Books I–VI are complete.

---

## Relationship to TauLib

| | This repo (`formalization`) | [`taulib`](https://github.com/Panta-Rhei-Framework/taulib) |
|---|---|---|
| **Purpose** | Frozen verification of published books | Active community development |
| **Contributions** | Not accepted (author-maintained) | Welcome (open PRs) |
| **Changes** | Only errata fixes by authors | Ongoing evolution |
| **Versioning** | Tagged at book publication | Semver, active |

---

## Citation

```bibtex
@software{taulib2026,
  author    = {Fuchs, Thorsten and Fuchs, Anna-Sophie},
  title     = {{TauLib}: Mechanized Formalization of Category $\tau$},
  year      = {2026},
  version   = {1.0.0},
  url       = {https://github.com/Panta-Rhei-Framework/formalization},
  note      = {450 modules, 125,771 lines of Lean 4, 4,332 theorems},
  license   = {Apache-2.0}
}
```

---

## Links

- **Books**: [panta-rhei.site](https://panta-rhei.site)
- **Active development**: [github.com/Panta-Rhei-Framework/taulib](https://github.com/Panta-Rhei-Framework/taulib)
- **Contact**: contact@panta-rhei.site

---

*The code is the proof. The proof is the code.*

*Clone it. Build it. Verify it yourself.*
