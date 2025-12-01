# Hydrological-Parameter-Sensitivity-Morris-SWAT

A complete, reproducible, and research-grade workflow for performing **global sensitivity analysis** of SWAT model hydrological parameters using the **Morris Method (Elementary Effects)**.  
This repository integrates a full scientific pipeline including parameter perturbation, SWAT model execution, uncertainty propagation, and multi-objective performance evaluation.

---

## 🚀 Overview

Hydrological models like **SWAT (Soil & Water Assessment Tool)** contain many parameters that strongly influence watershed simulation results.  
This project performs a *global sensitivity analysis* using the **Morris Method**, identifying the most influential hydrological parameters on:

- **Nash–Sutcliffe Efficiency (NSE)**
- **Streamflow Range (Max–Min)**

The workflow is designed for:

✔ Research & publication  
✔ Masters/PhD thesis work  
✔ Calibration/uncertainty analysis  
✔ Hydrological modeling projects

---

## 📂 Repository Structure

```
Hydrological-Parameter-Sensitivity-Morris-SWAT
│
├── data/
│   ├── Observed Streamflow.xlsx     # Observed discharge data
│   ├── output.rch                   # SWAT simulated discharge
│   └── (Your own TxtInOut files, if needed)
│
├── swat_morris_sensitivity.ipynb    # Main Jupyter Notebook workflow
├── README.md                        # Project documentation
└── .gitignore                       # Ignore large SWAT executable files
```

---

## ⚠️ Important Note About SWAT Files

Due to **licensing restrictions**, the SWAT executable (`swat2012.exe`) and the full `TxtInOut` directory **cannot be distributed** in this repository.

➡️ **Users must provide their own SWAT setup** and place it inside the `/data` folder before running the notebook.

---

## 🧪 How to Run the Project (Step-by-Step)

### 1️⃣ Clone the repository
```bash
git clone https://github.com/HAMIDREZANASERIAN/Hydrological-Parameter-Sensitivity-Morris-SWAT.git
```

### 2️⃣ Enter the project folder
```bash
cd Hydrological-Parameter-Sensitivity-Morris-SWAT
```

### 3️⃣ Launch Jupyter Notebook
```bash
jupyter notebook
```

### 4️⃣ Open and Run
Run all cells in:

```
swat_morris_sensitivity.ipynb
```

Make sure you have placed:

✔ `Observed Streamflow.xlsx`  
✔ `output.rch`  
✔ Your SWAT `TxtInOut` files (if needed)

inside the **data/** folder.

---

## 📊 Sensitivity Analysis Results

The Morris method outputs two key metrics:

- **Mu_star (Absolute Mean Effect)** → Parameter overall influence  
- **Sigma (Standard Deviation)** → Parameter interaction / non-linear effects  

---

## 📈 NSE-Based Sensitivity

![NSE Sensitivity](images/NSE_sensitivity.png)

### **Top Influential Parameters (NSE)**

| Parameter | Mu\* | Sigma |
|----------|------|--------|
| **GWQMN** | 0.1784 | 0.2506 |
| **GW_DELAY** | 0.0560 | 0.0811 |
| **SOL_K** | 0.0392 | 0.0702 |
| **SFTMP** | 0.0317 | 0.0633 |
| **SURLAG** | 0.0220 | 0.0721 |

➡️ **GWQMN** is by far the dominant parameter for NSE.

---

## 📈 Flow Range (Max–Min) Sensitivity

![Range Sensitivity](images/RANGE_sensitivity.png)

### **Top Influential Parameters (Range of Outflow)**

| Parameter | Mu\* | Sigma |
|----------|------|--------|
| **GWQMN** | 3.9901 | 5.8951 |
| **GW_DELAY** | 1.4867 | 2.0259 |
| **SOL_K** | 1.1883 | 2.2491 |
| **SFTMP** | 0.6869 | 1.7444 |
| **SURLAG** | 0.5492 | 1.7823 |

➡️ Again, **GWQMN**, **GW_DELAY**, and **SOL_K** dominate variability.

---

## 🔍 Full Morris Output (Detailed Statistics)

### **Range of Outflow: Detailed Stats**
```
CN2: Mu_star=0.1085, Sigma=0.1745
SURLAG: Mu_star=0.5492, Sigma=1.7823
SFTMP: Mu_star=0.6869, Sigma=1.7444
SMTMP: Mu_star=0.3307, Sigma=0.9637
SMFMX: Mu_star=0.6446, Sigma=1.9991
SMFMN: Mu_star=0.0547, Sigma=0.0910
GW_DELAY: Mu_star=1.4867, Sigma=2.0259
ALPHA_BF: Mu_star=0.5902, Sigma=0.8456
GWQMN: Mu_star=3.9901, Sigma=5.8951
RCHRG_DP: Mu_star=0.5190, Sigma=0.7416
SOL_K: Mu_star=1.1883, Sigma=2.2491
SOL_AWC: Mu_star=0.0517, Sigma=0.0829
```

### **NSE: Detailed Stats**
```
CN2: Mu_star=0.0071, Sigma=0.0141
SURLAG: Mu_star=0.0220, Sigma=0.0721
SFTMP: Mu_star=0.0317, Sigma=0.0633
SMTMP: Mu_star=0.0185, Sigma=0.0364
SMFMX: Mu_star=0.0219, Sigma=0.0599
SMFMN: Mu_star=0.0037, Sigma=0.0062
GW_DELAY: Mu_star=0.0560, Sigma=0.0811
ALPHA_BF: Mu_star=0.0251, Sigma=0.0416
GWQMN: Mu_star=0.1784, Sigma=0.2506
RCHRG_DP: Mu_star=0.0269, Sigma=0.0376
SOL_K: Mu_star=0.0392, Sigma=0.0702
SOL_AWC: Mu_star=0.0019, Sigma=0.0030
```

---

## 🎓 Scientific Interpretation (For Thesis / Supervisor / Reviewer)

- **GWQMN** shows the highest influence on both flow magnitude variability and NSE →  
  indicating its dominant control on groundwater contribution to streamflow.

- **GW_DELAY** and **SOL_K** exhibit strong interaction effects (high Sigma),  
  suggesting nonlinear relationships with the hydrology system.

- Parameters like **SMFMN**, **SOL_AWC**, and **CN2** show minimal influence under the tested watershed conditions.

These results are consistent with hydrological literature on groundwater-dominated basins.

---

## 👤 Author
**Hamidreza Naserian**

---

## 📬 Contact / Collaboration
If you're interested in expanding this project (e.g.,  
Sobol analysis, GLUE uncertainty sampling, or calibration algorithms), feel free to reach out.

---

