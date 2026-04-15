# 🌌 EPPQ-MDMC — Non-Critical Baseline for λ Emergence

This repository implements a Metropolis–Hastings (MCMC) simulation of the PMAH dynamics within the EPPQ framework, serving as a **non-critical baseline** for the study of the emergent inertia parameter λ.

---

## 1. Purpose

This implementation is **not** intended to reproduce the full EPPQ dynamics.

Instead, it serves as a **control experiment** to demonstrate that:

> The emergence of λ is **not** a generic property of relational dynamics,  
> but specifically arises from **self-organized criticality (SOC)**.

---

## 2. Model Description

The system evolves according to a Metropolis–Hastings update rule applied to a Barabási–Albert network.

At each step, a local rewiring move is proposed and accepted with Boltzmann probability:

\[
P = \exp(-\Delta A / T)
\]

where:

- \( \Delta A = \Delta I + \lambda \Delta C \)
- \( \Delta I \): interface (degree) cost
- \( \Delta C \): historical cost
- \( T \): effective temperature

---

## 3. Key Characteristics

- No avalanche dynamics  
- No branching process  
- No reproduction number \( R_0 \)  
- No self-organized criticality  

This places the system in a **local equilibrium regime**.

---

## 4. Measured Quantities

The simulation extracts:

- Degree distribution exponent \( \beta \)
- Mean degree \( \langle d \rangle \)
- Product \( \beta \langle d \rangle \)

and compares them to the input parameter \( \lambda \).

---

## 5. Main Result

The simulation shows that:

- \( \beta \) and \( \langle d \rangle \) remain approximately constant
- No meaningful correlation between \( \lambda \) and \( \beta \langle d \rangle \) emerges
- Linear fits yield very low \( R^2 \)

**Conclusion:**

> λ does not emerge in non-critical (equilibrium-like) dynamics.

---

## 6. Interpretation

This result provides a crucial control:

> The scaling law  
> \[
> \lambda \propto \beta \langle d \rangle
> \]
> is **not** a generic feature of PMAH dynamics.

It is instead a **signature of self-organized criticality**, demonstrated in the companion repository:

- SOC implementation: https://github.com/ARNexus2026/EPPQ-SOC-lambda

---

## 7. How to Run

```bash
python lambda_mdmc.py
