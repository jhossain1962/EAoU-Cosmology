# EAoU-4 Cosmology Pipeline

This repository provides the analysis code for the paper:  
**“The Effective Age of the Universe (EAoU): Empirical Validation with Supernovae, GRBs, and Quasars.”**

It implements χ² fitting of luminosity distance–redshift relations under both the standard ΛCDM and the EAoU formulations.

---

## 📌 Features
- Fits **ΛCDM** (Ωₘ) and **EAoU** (Ωₘ, α).  
- Analytic marginalization over the nuisance parameter μ₀ (removes H₀/absolute magnitude dependence).  
- Reports χ², χ²/ν, Δχ², AIC, BIC.  
- Provides redshift histograms and residual plots for each dataset.  
- Works with SNe Ia, GRBs, and Quasars, with optional BAO and H(z) chronometers.

---

## 📂 Data Schema

The notebook expects input data in CSV format with the following columns:

```
ID, z, mu, sigma_mu, source
```

- **ID** → unique object identifier (e.g., `SN1998aq`, `GRB050904`, `QSO_J1148+5251`)  
- **z** → redshift  
- **mu** → distance modulus  
  \[
  \mu = m - M = 5 \log_{10}\left(\frac{D_L}{\text{Mpc}}\right) + 25
  \]  
- **sigma_mu** → uncertainty in the distance modulus  
- **source** → dataset origin (e.g., `Pantheon+`, `SH0ES`, `Amati2008`, `Risaliti2019`)

### Example rows:
```
SN1998aq, 0.0039, 32.23, 0.15, Pantheon+
GRB050904, 6.29, 48.12, 0.35, Amati2008
QSO_J1148+5251, 6.42, 47.95, 0.30, Risaliti2019
```

---

## 🚀 Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/EAoU-4.git
   cd EAoU-4
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook and open:
   ```bash
   jupyter notebook EAoU_chi2_fit.ipynb
   ```

4. Ensure your CSV datasets are in the same folder (or update the file paths inside the notebook).

---

## 🔬 Methodology

- **ΛCDM fit:** Brent’s bounded scalar minimization.  
- **EAoU fit:** L-BFGS-B optimization with bounds on (Ωₘ, α).  
- **Marginalization:** μ₀ (absolute magnitude/H₀ offset) is marginalized analytically following Conley et al. (2011) and Brout et al. (2022).  

---

## 📊 Reproducibility

- Absolute calibration (H₀) is absorbed into μ₀ and does not affect results.  
- Δχ², AIC, and BIC are reported for model comparison.  
- Figures include redshift distributions and Hubble residuals.  

---

## 📖 Citation

If you use this code or results, please cite:

- Hossain, J. (2025). *The Effective Age of the Universe (EAoU): Empirical Validation with Supernovae, GRBs, and Quasars.* Preprints, DOI: [10.20944/preprints202508.0758.v1](https://doi.org/10.20944/preprints202508.0758.v1)  
- Brout, D., et al. (2022). *The Pantheon+ Analysis: Cosmological Constraints.* ApJ, 938, 110.  
- Conley, A., et al. (2011). *Supernova Constraints and μ₀ Marginalization.* ApJS, 192, 1.  
- Byrd, R.H., Lu, P., Nocedal, J., & Zhu, C. (1995). *A Limited Memory Algorithm for Bound Constrained Optimization.* SIAM J. Sci. Comput. 16(5), 1190–1208.  

---

## 📜 License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
