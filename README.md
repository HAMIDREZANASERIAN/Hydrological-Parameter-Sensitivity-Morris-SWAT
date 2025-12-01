# Hydrological-Parameter-Sensitivity-Morris-SWAT

A complete, reproducible, and research-grade workflow for performing **global sensitivity analysis** of key hydrological parameters in the **SWAT (Soil and Water Assessment Tool)** model using the **Morris Method (Elementary Effects)**.

This project integrates:

- ArcSWAT model parameter perturbation  
- Morris sampling using **SALib**  
- Hydrological output extraction from `output.rch`  
- Comparison of simulated vs. observed streamflow  
- Evaluation using **Nash–Sutcliffe Efficiency (NSE)** and **Flow Range (Max–Min)**  
- Ranking SWAT parameters based on sensitivity indices (μ\*, σ)

This repository demonstrates a **scientific, well-documented, automated**, and **fully reproducible** analysis pipeline designed for hydrologic modeling and understanding watershed sensitivity.

---

## 🌍 Project Motivation

Understanding parameter influence in SWAT is essential for:

- Model calibration  
- Reducing uncertainty  
- Improving streamflow predictions  
- Identifying dominant watershed processes  

The **Morris Elementary Effects method** offers an efficient global sensitivity approach suitable for complex hydrologic models such as SWAT.

---

## ⚙️ Methodology Overview

### **1️⃣ Parameter Selection & Perturbation**

Selected hydrological parameters (e.g., CN2, ALPHA_BF, GW_DELAY, SOL_K, SOL_AWC, GWQMN, SURLAG, RCHRG_DP, etc.)  
are perturbed using Morris sampling.

Each trajectory includes:

- Writing updated parameters to the SWAT TxtInOut files  
- Running the SWAT executable  
- Extracting discharge time series from `output.rch`  

---

### **2️⃣ Morris Sampling (SALib)**

| Setting | Value |
|--------|--------|
| Sample Size (N) | 3000 |
| Trajectories | 16 |
| Levels | 8 |
| Method | Optimized Morris |

The SALib library generates parameter combinations fed into SWAT simulations.

---

### **3️⃣ Hydrological Metrics Computed**

For each simulation:

#### ✔ **Nash–Sutcliffe Efficiency (NSE)**  
Measures predictive accuracy of streamflow.

#### ✔ **Flow Range (Max–Min)**  
Captures discharge variability.

Both metrics quantify the hydrological response sensitivity to parameter perturbations.

---

### **4️⃣ Sensitivity Analysis Output**

For each parameter:

- **μ\*** → Mean absolute effect (total influence)  
- **σ** → Variability due to interactions & non-linearity  

Large **μ\*** → highly influential parameter  
Large **σ** → interactive / nonlinear parameter  

---

## 📁 Repository Structure

```
Hydrological-Parameter-Sensitivity-Morris-SWAT
│
├── data/
│   ├── Observed Streamflow.xlsx    # Observed discharge data
│   ├── output.rch                  # SWAT simulated discharge
│   └── (additional SWAT TxtInOut files if needed)
│
├── swat_morris_sensitivity.ipynb   # Main Jupyter Notebook workflow
├── README.md                       # Project documentation
├── .gitignore
└── Data.rar                        # Optional: compressed SWAT folder
```

---

## 🚀 Running the Project

### **1️⃣ Install Dependencies**

```
pip install SALib pandas numpy scipy matplotlib openpyxl
```

---

### **2️⃣ Place Input Data into `/data` Folder**

Required:

- `Observed Streamflow.xlsx`  
- `output.rch`  

Optional:

- Full SWAT `TxtInOut` folder for automatic runs  

---

### **3️⃣ Open the Notebook**

Using Anaconda:

```
jupyter notebook swat_morris_sensitivity.ipynb
```

Or open in **Google Colab** and upload the `data` folder.

---

### **4️⃣ Run All Cells**

The notebook automatically:

- Generates Morris samples  
- Updates SWAT parameters  
- Runs SWAT (if TxtInOut is present)  
- Reads observed and simulated data  
- Computes NSE + Flow Range  
- Performs Morris analysis  
- Produces sensitivity plots and rankings  

---

## 📊 Outputs

The workflow produces:

### **Sensitivity Results**
- μ\* (mean absolute effects)  
- σ (interaction / nonlinearity)

### **Performance Metrics**
- NSE  
- Flow Range  

### **Plots**
- NSE-based sensitivity scatter  
- Flow-range sensitivity scatter  
- Hydrograph comparisons  

---

## 🧠 Scientific Contribution

This project demonstrates:

- Full automation of SWAT sensitivity analysis  
- Integration of hydrological modeling with Python  
- Global sensitivity quantification using Morris method  
- Reproducible workflow for academic and applied hydrology  
- Identification of dominant watershed parameters  

Suitable for:

- MSc / PhD research  
- SWAT calibration preparation  
- Parameter screening  
- Watershed modeling & environmental studies  

---

## 👤 Developer

**Hamidreza Naserianhanzaei**

Hydrological Modeling • Watershed Systems • Python Automation • SWAT • Sensitivity Analysis

---

## 📄 License

Provided for academic and research use. Redistribution of SWAT executable is not permitted.

