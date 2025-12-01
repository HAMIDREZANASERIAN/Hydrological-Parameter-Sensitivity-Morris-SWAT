# Hydrological-Parameter-Sensitivity-Morris-SWAT

A complete workflow for global sensitivity analysis of hydrological parameters in the SWAT model using the **Morris Method (Elementary Effects)**.  
This project integrates parameter perturbation, ArcSWAT model execution, output extraction, and multi-objective evaluation (NSE and flow range).

---

## 📌 Project Overview

This repository contains:

- A reproducible workflow for **Morris global sensitivity analysis**
- A Jupyter Notebook implementing:
  - parameter sampling (SALib)
  - dynamic modification of SWAT input files (`.mgt`, `.bsn`, `.gw`, `.sol`)
  - execution of the SWAT hydrological model
  - extraction of streamflow from `output.rch`
  - computation of NSE and discharge range
  - sensitivity plots for all 12 hydrological parameters
- A `/data` directory containing sample observed streamflow

This project demonstrates a full scientific workflow suitable for hydrological modeling, uncertainty quantification, and environmental system analysis.

---

## 🧪 Methods Used

### **1. Morris Global Sensitivity Analysis**
The Morris method is used to estimate:
- **mu\*** → the overall sensitivity (mean absolute effect)  
- **sigma** → the nonlinearity / interaction strength  

### **2. Objective Functions**
- **NSE (Nash–Sutcliffe Efficiency)**  
  Used to measure how well the simulation fits the observed streamflow.  

- **Flow Range (Max–Min)**  
  Measures variability in simulated discharge.

---

## 🧩 Parameters Analyzed

12 key SWAT parameters:

| Parameter | Description |
|----------|-------------|
| CN2 | SCS Curve Number |
| SURLAG | Surface runoff lag time |
| SFTMP | Snowfall temperature |
| SMTMP | Snow melt base temperature |
| SMFMX | Maximum snowmelt factor |
| SMFMN | Minimum snowmelt factor |
| GW_DELAY | Groundwater delay |
| ALPHA_BF | Baseflow recession constant |
| GWQMN | Groundwater threshold depth |
| RCHRG_DP | Deep aquifer percolation |
| SOL_K | Saturated hydraulic conductivity |
| SOL_AWC | Available water content |

---

## 📂 Repository Structure

```
Hydrological-Parameter-Sensitivity-Morris-SWAT/
│
├── swat_morris_sensitivity.ipynb   # Main notebook
├── README.md                       # Project documentation
├── data/
│   ├── Observed_Streamflow.xlsx    # Example observed data
│   └── (place your SWAT TxtInOut here)
```

---

## ⚠️ **Licensing and SWAT File Restrictions**

Due to SWAT license restrictions, the following files **cannot be included** in this repository:

- `swat2012.exe`
- The full **TxtInOut** directory  
- Any SWAT project files (.mgt, .gw, .bsn, .sol, etc.)

To run the notebook with your own SWAT setup:

1. Place your **TxtInOut** folder inside `/data/`
2. Place your **swat2012.exe** inside `/data/`
3. Update the paths in the notebook if necessary

```
⚠️ Note: This repository contains only *public and reproducible components*.  
All SWAT model files must be supplied by the user.
```

---

## ▶️ How to Run

### **1. Clone the repository**
```bash
git clone https://github.com/HAMIDREZANASERIAN/Hydrological-Parameter-Sensitivity-Morris-SWAT.git
```

### **2. Enter the folder**
```bash
cd Hydrological-Parameter-Sensitivity-Morris-SWAT
```

### **3. Launch Jupyter**
```bash
jupyter notebook
```

### **4. Open and run**
```
swat_morris_sensitivity.ipynb
```

---

## 👨‍💻 Developer
**Hamidreza Naserian**  

---

## 🌟 Purpose of the Repository

This repository showcases:

- Skill in hydrological modeling  
- Experience with SWAT & ArcSWAT  
- ML-based environmental modeling  
- Sensitivity analysis  
- Working with Python scientific ecosystem  
- Ability to create reproducible workflows  
- GitHub proficiency  

Perfect for **PhD applications**, **CVs**, and **research portfolios**.

---
