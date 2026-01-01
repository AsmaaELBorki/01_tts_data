# Tracking the Sun — Program Canon and Analytical Architecture

## What Question Does This Program Answer?

**How can we determine whether a residential solar system in California is appropriately sized for its context — or meaningfully over- or under-sized — using only observed installation data?**

This program builds a defensible analytical system for answering that question **without assuming intent, demand, or optimality**, and without introducing structure that the data cannot support.

The resulting framework enables:
- context-aware sizing assessment
- identification of unusual or atypical system designs
- evaluation of sizing risk relative to observed market behavior

These outputs are relevant to:
- analysts studying residential solar adoption and design patterns  
- energy modelers seeking empirically grounded baselines  
- practitioners evaluating system sizing norms and deviations  
- hiring managers assessing analytical rigor beyond tool usage  

---

## Program Value

This program is designed to produce a **reliable analytical substrate** for understanding residential solar system behavior in California.

Its value lies in:

- Establishing **stable reference frames** for system size and scaling behavior  
- Separating **measurement, structure, scaling, and evaluation** so conclusions remain interpretable  
- Enabling **abnormality and sizing risk assessment** without inventing structure downstream  
- Making analytical decisions **explicit, auditable, and reusable**

Rather than optimizing for speed or novelty, the program prioritizes **internal coherence and analytical discipline**, allowing downstream insights to rest on clearly defined foundations.

---

## Program Scope

- **Dataset:** NREL *Tracking the Sun* (publicly released)
- **Geographic focus:** **California only**
- **Population:** **Residential solar systems only**  
  (`customer_segment == "RES"`)

All baselines, structures, and evaluations produced by this program apply **only** within this scope.

---

## Analytical Posture and Boundaries

- Analyses are **descriptive and structural by design**
- Evaluation and risk assessment occur **only within upstream constraints**
- Measurement limits are respected as declared by the dataset owners

### Explicit Non-Goals

- No causal attribution  
- No policy evaluation  
- No counterfactual or normative claims  
- No inference beyond declared measurement limits  

These boundaries are intentional and ensure that downstream results remain interpretable and defensible.

---

## Program Architecture Overview

The program is organized as a **strictly ordered analytical stack**.  
Each repository answers a specific class of questions and establishes preconditions for downstream work.

