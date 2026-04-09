# Constraint Branch Selection

## Colab demos

### 1. Constraint narrowing (degeneracy → branches)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/thinkthoughts/constraint-branch-selection/blob/main/notebooks/01_branch_selection_demo.ipynb)

Toy model: adding constraints reduces parameter space but leaves multiple branches.

### 2. Stable-but-wrong vs true branch
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/thinkthoughts/constraint-branch-selection/blob/main/notebooks/02_false_branch_vs_true.ipynb)

Toy model: optimization can converge stably to the wrong branch until an orthogonal constraint is added.

### 3. Observability threshold
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/thinkthoughts/constraint-branch-selection/blob/main/notebooks/03_observability_threshold_V2.ipynb)

Toy model: how increasing constraint strength (precision) collapses degeneracy into a unique solution.

Minimal Colab demo of constraint-based branch selection:
fit ≠ identifiability

A minimal repository for studying a common structure in inverse problems:

- one observable → many valid solutions  
- added constraints → reduced parameter space  
- multiple branches may still survive  
- identifiability requires sufficient independent constraints  

---

## Core idea

Fitting a signal is not the same as identifying the correct model.

A solution can:
- **fit data**  
- **remain stable under optimization**  
- **satisfy several constraints**

and still be **non-unique**.

This repo focuses on the transition:

> **fit → constraint consistency → identifiability**

---

## Definitions

- **Fit**  
  A model reproduces an observed signal.

- **Constraint consistency**  
  A model satisfies multiple independent conditions  
  (e.g., relic density, indirect detection, direct detection, astrophysical bounds).

- **Branch (solution class)**  
  A connected region of parameter space consistent with constraints.

- **Identifiability**  
  A single branch is selected as the unique solution.

---

## Motivation

Many modern problems share this structure:

- particle physics (dark matter models)  
- cosmology (degenerate parameter inference)  
- machine learning (multiple minima / equivalent solutions)  
- holography (bulk reconstruction degeneracy)  

In each case:

> constraints narrow possibilities,  
> but do not necessarily resolve them.

---

## Example (arXiv:2604.05016)

A recent dark matter analysis:

- Galactic halo γ-ray excess  
- minimal electroweak doublet DM (~400–800 GeV)  
- consistent with multiple constraints  

Result:

- parameter space is **narrowed**  
- but **degeneracy remains**  
- solution is **not uniquely identified**

This makes it a clean case of:

> **constraint-based branch selection without full identifiability**

---

## Repository structure

```
constraint-branch-selection/
├── README.md
├── notebooks/
│   └── 01_branch_selection_demo.ipynb
├── src/
│   ├── toy_model.py
│   ├── constraints.py
│   ├── scan.py
│   └── plots.py
├── notes/
│   └── arxiv-2604.05016.md
└── results/
```

---

## Planned components

- **Toy models**  
  Simple multi-parameter systems with controllable degeneracy

- **Constraint stacking**  
  Sequential addition of independent constraints

- **Phase diagrams**  
  Visualization of surviving branches

- **Branch selection demos**  
  Cases where:
  - multiple branches survive  
  - a new constraint eliminates all but one  

---

## Key question

What combination of constraints is sufficient to turn:

> a set of viable solutions  
into  
> a uniquely identifiable solution?

---

## Guiding principle

> **constraint structure > raw fit**

---

## Reference

- arXiv:2604.05016  
- sdg5.app/main.pdf

---

## Notation (optional framing)

45° 📐  
signal > noise  

Constraint acts as a **selection gate** over solution space.
