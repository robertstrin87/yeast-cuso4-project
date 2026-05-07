# Effects of Copper Sulfate on Yeast Growth and Viability

**Course:** BIOL 1406 – General Biology I Lab  
**Institution:** Sam Houston State University  
**Date:** Spring 2026  
**Authors:** Kimberly Alonso, Chase Hartford, Emely Lira, Laney Reynolds, Robert Stringer

---

## Overview

This project investigates how copper sulfate (CuSO₄) affects the growth and viability of *Saccharomyces cerevisiae* (baker's yeast) over time. Experiments were conducted over three weeks, measuring optical density (OD600) and cell viability (% live cells via methylene blue staining) across three treatment groups.

This repository contains the raw data, a fully annotated Python analysis notebook, and all figures — structured as a beginner data science portfolio project.

---

## Biological Question

> **Does copper sulfate reduce the growth and viability of *Saccharomyces cerevisiae*, and if so, by how much over a 4-hour period?**

**Hypothesis:** Addition of copper sulfate to *S. cerevisiae* will result in decreased cell viability and reduced growth compared to controls, due to its toxic effects on cellular processes.

---

## Experimental Design

| Group | Description | Purpose |
|---|---|---|
| **NC** — Negative Control | Yeast in YPD medium only | Establishes healthy baseline growth |
| **PC** — Positive Control | Yeast + Miconazole (0.09 µM) | Known antifungal — confirms inhibition is detectable |
| **CuSO₄** — Experimental | Yeast + Copper Sulfate | Tests the effect of the compound of interest |

- **Timepoints:** Hours 0, 1, 2, 3, 4 (Week 1 extended to hour 5)
- **Biological replicates:** 3 independent experimental weeks (W1, W2, W3)
- **Measurements:** OD600 absorbance (spectrophotometer) + % viability (methylene blue + cell counting)

---

## Key Results

| Comparison | p-value | Significant? |
|---|---|---|
| PC vs NC (viability, hour 4) | 0.0022 | ✅ Yes |
| PC vs CuSO₄ (viability, hour 4) | 0.0112 | ✅ Yes |
| NC vs CuSO₄ (viability, hour 4) | 0.1824 | ❌ No |
| One-way ANOVA (all groups, hour 4) | 0.0029 (F = 16.87) | ✅ Yes |

**CuSO₄ viability trend (mean across 3 weeks):**  
Hour 0 → 89.7% &nbsp;|&nbsp; Hour 2 → 55.7% &nbsp;|&nbsp; Hour 4 → 46.0%

The most dramatic decline was observed in **Week 3**, where viability dropped from 96% at hour 0 to just 9% by hour 4.

---

## Repository Structure

```
yeast-cuso4-project/
│
├── data/
│   └── cuso4_yeast_real_data.csv   # Tidy dataset (46 rows, all 3 groups × 3 weeks)
│
├── notebooks/
│   └── yeast_analysis.ipynb        # Full analysis notebook (Google Colab ready)
│
├── figures/
│   ├── viability_over_time.png     # Mean viability ± SD across treatment groups
│   ├── od600_over_time.png         # Mean OD600 ± SD across treatment groups
│   ├── combined_figure.png         # Publication-style side-by-side figure
│   ├── viability_by_week.png       # Per-week breakdown (individual replicates)
│   └── viability_bar_stats.png     # Bar chart with significance brackets
│
└── README.md                       # This file
```

---

## How to Run the Analysis

### Option 1 — Google Colab (recommended, no install needed)

1. Click the badge below or go to [colab.research.google.com](https://colab.research.google.com)
2. Choose **File → Open notebook → GitHub**
3. Paste this repo URL and select `notebooks/yeast_analysis.ipynb`
4. Run cells top to bottom with `Shift + Enter`
5. Upload `data/cuso4_yeast_real_data.csv` when prompted

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

### Option 2 — Run locally

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/yeast-cuso4-project.git
cd yeast-cuso4-project

# Install dependencies
pip install pandas matplotlib seaborn scipy numpy

# Launch Jupyter
jupyter notebook notebooks/yeast_analysis.ipynb
```

---

## Methods Summary

- **Culture preparation:** Three 10 mL cultures in YPD medium (NC, PC, CuSO₄) prepared using aseptic technique
- **Growth measurement:** OD600 absorbance measured hourly using a spectrophotometer (blanked with CuSO₄ solution)
- **Viability assessment:** 10 µL culture + 2 µL methylene blue stained on microscope slide; 100 cells counted per sample
- **Statistics:** Two-tailed t-tests (equal variance) and one-way ANOVA performed at hour 4 across 3 biological replicates

---

## Technologies Used

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/pandas-data%20analysis-lightblue)
![Matplotlib](https://img.shields.io/badge/matplotlib-visualization-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-notebook-orange?logo=jupyter)
![Google Colab](https://img.shields.io/badge/Google%20Colab-ready-yellow?logo=googlecolab)

---

## References

1. *BIOL 1406: General Biology I Lab Manual*. Spring 2026 ed., Sam Houston State University, 2026.
2. Liu, Z., Wang, Z., and Li, H. "Effect of Copper Stress on Yeast Fermentation and Growth Characteristics." *Food Chemistry*, vol. 187, 2015, pp. 545–554.
3. Matsumoto, A., Terashima, I., & Uesono, Y. (2022). "A rapid and simple spectroscopic method for the determination of yeast cell viability using methylene blue." *Yeast*, 39.
4. Gerstein, A. C., et al. (2015). "Too Much of a Good Thing: The Unique and Repeated Paths Toward Copper Adaptation." *Genetics*, 199(2), 555–571.

---

*This project was completed as part of BIOL 1406 and is shared here as a data analysis portfolio piece.*
