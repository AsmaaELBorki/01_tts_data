# Data Contract

This document defines how reported data may be interpreted **given how it was generated and recorded by reporting programs**.

It does not describe how data is cleaned.
It defines what “valid,” “usable,” and “out of scope” mean **based on declared reporting characteristics**.

All downstream repositories inherit these constraints unchanged.

---

## installation_date

**Role:** temporal

---

## Identifier Validity and Admissibility

Identifiers used to represent analytical entities must satisfy strict admissibility criteria.

An identifier is considered valid for entity-level use only if it:
- is stable across reporting instances,
- is consistent across all rows referring to the same real-world object,
- and is not reused across distinct physical systems.

Identifiers assigned for administrative, programmatic, or reporting purposes
do not satisfy these criteria by default.

### Violations

The following constitute **hard violations** when an identifier is used for
system-level analysis:

- instability of identifier values across reports,
- conflicting identifier values within a candidate entity group,
- reuse of an identifier across multiple physical systems,
- promotion of a provider or reporting identifier to system identity.

Hard violations prohibit entity construction and require exclusion or deferral
to upstream resolution.

---

### Raw State

- source type: string
- format: inconsistent
- precision: mixed (year-only, partial, full date)
- nullability: allowed

In raw form, `installation_date` is a valid reported field but is not directly usable for analytical comparison.

---

### Canonical Representation

All time-based analysis relies on a derived field:

- `installation_year` (integer)

This represents the **minimum temporal resolution supported by reporting consistency**.

No downstream analysis relies directly on raw date strings.

---

### Reporting Window

- earliest valid year: 1998
- latest valid year: current reporting year

Values outside this window are treated as reporting errors and excluded from time-based analysis.

---

### Validity and Violations

**Hard violations**
- unparseable values
- future dates
- values outside the reporting window

Hard violations exclude records from all time-based analysis.

**Soft violations**
- missing month or day
- provider-specific reporting gaps

Soft violations restrict usage but do not require exclusion.

**Structural absences**
- missing values in early cohorts with known reporting limitations

Structural absences are treated as properties of reporting history, not data quality failures.

---

### Allowed Assumptions

The following assumptions are explicitly adopted due to reporting limitations:

- installation year is treated as a proxy for commissioning year
- year-level aggregation is acceptable where finer precision is unavailable
- reporting gaps are cohort- and provider-specific rather than random

These assumptions are conditional and may not be silently altered or strengthened downstream.
