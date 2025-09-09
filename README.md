# EAoU-Cosmology

Code and data framework for the **Effective Age of the Universe (EAoU)** cosmology model.  
This repository provides tools for χ² fitting, model comparison, and residual analysis across multiple cosmological probes, including **Supernovae (Pantheon+ SH0ES), Gamma-Ray Bursts (GRBs), and Quasars**.

EAoU extends ΛCDM by introducing a relativistic time-dilation correction exponent α, yielding an **effective cosmic age of ~45 Gyr** and resolving multiple cosmological tensions.

---

## 📖 Overview

The repository contains:
- **EAoU_chi2_fit.ipynb** – Jupyter notebook implementing ΛCDM vs EAoU χ² fits, AIC/BIC comparisons, and residual plots.
- **requirements.txt** – Dependencies for running the notebook.
- **README.md** – Documentation (this file).
- **LICENSE** – MIT License with citation requirement.
- **CITATION.cff** – Machine-readable citation metadata for GitHub’s “Cite this repository” feature.

---

## ⚙️ Installation

Clone this repository and install dependencies:

```bash
git clone https://github.com/jhossain1962/EAoU-Cosmology.git
cd EAoU-Cosmology
pip install -r requirements.txt
```

Dependencies include:
- `numpy`
- `pandas`
- `matplotlib`
- `scipy` (optional, for optimization)

---

## 🚀 Usage

Open the Jupyter notebook and run analyses:

```bash
jupyter notebook EAoU_chi2_fit.ipynb
```

The notebook provides:
- χ² fits for **ΛCDM** and **EAoU**  
- Residual plots for SNe data  
- AIC/BIC information criteria for model selection  
- Support for Pantheon+ SNe, BAO, and chronometer data (via CSVs in `./data/`)  

### Input Data Schema

For supernovae, the expected CSV format is:

```
ID, z, mu, sigma_mu, source
```

- `ID`: Object identifier (e.g., SN name)  
- `z`: Redshift  
- `mu`: Distance modulus  
- `sigma_mu`: Uncertainty in `mu`  
- `source`: Reference catalog (e.g., Pantheon+, GRB dataset, Quasar sample)  

Example datasets will be added in the `data/` folder.

---

## 📊 Example Analysis

- Compare EAoU vs ΛCDM fits for Pantheon+ data  
- Generate residual plots (μ_obs − μ_model vs z)  
- Compute effective cosmic age under EAoU  

---

## 📜 License

This project is licensed under the **MIT License** (see `LICENSE` file).  
If you use this software in **scientific work or publications**, please **cite it** (see below).

---

## 📑 Citation

If you use this repository, please cite:

**Jami Hossain (2025).**  
*Beyond the Comoving Frame: Effective Age of the Universe and its Empirical Validation Across 4284 Cosmological Probes.*  
Submitted to *The European Physical Journal C (EPJC)*.  

Citation metadata is also included in the file `CITATION.cff`, and can be accessed via GitHub’s **“Cite this repository”** option.

---

## 🔮 Future Work

- Extend EAoU analysis to **BAO** and **CMB** datasets  
- Explore implications for structure formation and cosmic chronometers  
- Release versioned datasets for reproducibility  

---
