# Dataset Overview

This document describes the NREL *Tracking the Sun* dataset as released by its owners and contributing program administrators.

The dataset captures reported information about distributed solar photovoltaic installations across the United States over multiple decades. All descriptions here reflect how the data were recorded and reported, not how they are later analyzed.

---

## Coverage

The dataset includes reported installations across:
- residential, commercial, and other customer segments
- installation years spanning from the late 1990s to 2024
- technical, financial, geographic, and configuration-related attributes

Data are collected through **administrative reporting** to state, utility, and program-level entities (e.g., incentive programs, interconnection processes). Coverage therefore varies by year, reporting program, and jurisdiction.

This variability is structural, not incidental.

---

## Structure

The dataset is wide rather than tall.

It includes:
- multiple identifier fields
- mixed temporal representations
- repeated component families (e.g. modules, inverters)
- indicator flags encoded as integers
- measurements expressed in physical and monetary units

Several columns encode multiplicity through positional suffixes (`_1`, `_2`, `_3`) rather than normalization. This reflects how systems are reported by programs, not a modeling choice.

---

## Known Reporting Characteristics

The dataset exhibits:
- uneven reporting precision across time
- provider-specific gaps
- evolving technology representations
- mixed use of nulls, zeros, and structural absences

These characteristics arise from heterogeneous reporting standards and requirements. They are not treated as errors by default; they define limits on comparability and inference.

---

## Measurement Implications

Because the dataset is compiled from heterogeneous administrative reports:
- missing values may indicate non-reporting rather than non-existence
- temporal fields may reflect program timelines rather than physical installation events
- comparisons across time or geography may embed reporting artifacts

As a result, the dataset supports descriptive and comparative analysis of **reported installations**, but does not support inference about intent, optimality, or unobserved household characteristics.

---

## What a Row Represents (and Does Not Represent)

Each row in the Tracking the Sun dataset represents a reported administrative record,
not a direct measurement of a physical solar installation.

Multiple rows may refer to the same physical system due to:
- updates to reported information,
- participation in multiple programs,
- or differing reporting obligations across jurisdictions and time.

No row in this dataset is assumed to uniquely represent a system.
System-level entities are not defined at the raw data level and may not be inferred
from row-level structure alone.

---

## Relationship to Downstream Analysis

This document records what the dataset contains and how it was reported.

It does not define how the data are cleaned, transformed, or analyzed.  
Those activities are constrained downstream by:
- column role definitions
- the data contract
- declared violation types
- raw and canonical schemas

All downstream analysis is expected to respect the measurement limits described here.

---

## Status

The dataset is treated as fixed input.

Understanding of its reporting structure may evolve as documentation improves, but interpretation remains constrained by how the data were generated and recorded.
 
