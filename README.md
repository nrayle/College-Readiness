# College Readiness & Completion Analysis
### Classes of 2016–2025

---

## What This Is

This repository contains the data analysis notebook and supporting files for
a study examining whether a school's college readiness designation predicts
college graduation within six years. The analysis was conducted by the school's
Academic Data Manager as part of an M.S. in Data Science capstone project.

The full methodology, findings, and interpretation are documented in the
notebook. This file covers what is in the repository and how to run it.

---

## Repository Contents

```
├── College Readiness Data.txt       # Source data file (not included in public repo)
├── notebook.ipynb                   # Main analysis notebook
├── README.md                        # This file
└── outputs/
    ├── graduation_rate_by_readiness.png
    ├── permutation_tests.png
    ├── bootstrap_ci.png
    ├── logistic_regression.png
    ├── quadrant_analysis.png
    └── projection.png
```

---

## Data Sources

- **Student Information System (SIS)** — GPA and graduating class year
- **ACT** — Standardized test scores and benchmark attainment (Classes of 2016–2020)
- **College Board** — SAT benchmark definitions and concordance table
- **National Student Clearinghouse** — Post-secondary enrollment and completion outcomes

*Data is not included in this repository. All records are student-level and
subject to FERPA. Contact the institution for access inquiries.*

---

## Requirements

```
python >= 3.9
pandas
numpy
matplotlib
scikit-learn
```

Install dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn
```

---

## How to Run

1. Place `College Readiness Data.txt` in the root directory
2. Open `notebook.ipynb` in Jupyter
3. Run all cells in order

All outputs are saved to the `outputs/` directory.

---

## Notes

- The Class of 2021 is excluded from all analysis due to COVID-19 testing
  cancellations
- The Class of 2020 is included in the analysis cohort with a caveat noted
  in the notebook — final Clearinghouse data for this class is expected in
  summer 2026
- The dataset represents the full population of graduates, not a sample
- All statistical methods are interpreted under population-level assumptions
  as described in the notebook

---
