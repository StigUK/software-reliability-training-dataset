# Software Reliability Training Dataset

Cross-project training dataset for software defect prediction and reliability modeling.

## Overview

This repository contains a cross-project dataset designed for studying relationships between software development process decisions, defect occurrence, and software reliability.

The dataset was created for research in:

- Software defect prediction
- Software reliability modeling
- Cross-project learning
- Process-aware quality assessment
- Fuzzy and machine learning approaches for software engineering

The dataset includes **25 software projects** with similar development goals and **10 development stages** per project.

---

## Dataset Structure

Each project is represented by ten development stages.

Each stage contains three operation types:

- **R** — Work (implementation)
- **K** — Control (verification/testing)
- **D** — Rework (correction and optimization)

For each operation, execution is encoded as:

```text
(method, variant)
```

Where:

### Execution Method (`method`)
- 1 — before optimization
- 2 — after optimization

### Implementation Variant (`variant`)

For Work and Rework:

1. Template-based generation  
2. Manual coding  
3. Adapted code reuse  
4. Development from scratch  

For Control:

1. Manual verification  
2. Automated testing  
3. Static analysis  
4. Integration testing  

If a stage is absent in a project:

```text
(0,0)
```

indicates a missing stage.

---

## Additional Variables

The dataset includes defect probability features:

- Work defect probability  
- Defect escape probability during control  
- Defect probability during rework  

These variables were added to model the relationship:

```text
Defect = f(method, variant)
```

and support reliability estimation.

---

## Progress Variable

Each stage includes:

```text
S_i_progress ∈ [0,1]
```

representing cumulative stage completion progress.

---

## Files

### Raw dataset
Contains encoded project data in original research format.

- `raw_dataset.xlsx`
- `raw_dataset.csv`

---

### ML-ready dataset
Expanded feature representation for machine learning.

Includes:

- separated method / variant features  
- defect probability features  
- stage presence indicators  
- progress values

Files:

- `ml_ready_dataset.xlsx`
- `ml_ready_dataset.csv`

---

## Example Features

Example columns:

```text
S1_R_code
S1_R_defect_rate
S1_K_code
S1_K_defect_rate
S1_D_code
S1_D_defect_rate
S1_progress
```

---

## Potential Applications

This dataset can be used for:

- Defect prediction
- Reliability estimation
- Transfer learning experiments
- Fuzzy inference modeling
- Benchmarking process-aware software quality models

---

## Research Motivation

The dataset assumes software defectiveness depends on:

- execution strategy  
- implementation variant  
- development stage characteristics

and supports modeling of software reliability using process-aware features.

---

## Citation

If you use this dataset, please cite:

```bibtex
@dataset{prus2026software_reliability,
  author = {Bohdan Prus},
  title = {Software Reliability Training Dataset},
  year = {2026}
}
```

---

## License

This dataset is released under:

CC BY 4.0

---

## Author

Bohdan Prus  
PhD Researcher in Software Engineering
