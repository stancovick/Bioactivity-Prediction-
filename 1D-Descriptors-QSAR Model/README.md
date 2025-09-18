# Bioactivity Prediction (QSAR Modeling)

This repository contains a machine learning workflow for predicting **bioactivity (pChEMBL values)** of chemical compounds using molecular descriptors generated with **RDKit**.  

The project applies cheminformatics and regression models to evaluate the relationship between chemical structure and biological activity.

## 🔬 Workflow Overview

1. **Data Loading**  
   - Input file: `Raw_Qsar.csv`  
   - Columns used:  
     - `Molecule ChEMBL ID`  
     - `Smiles`  
     - `pChEMBL Value`  

2. **Descriptor Calculation (via RDKit)**  
   The following molecular descriptors are calculated:  
   - Molecular Weight (`MolWt`)  
   - LogP (`MolLogP`)  
   - Number of H-bond Acceptors (`nHA`)  
   - Number of H-bond Donors (`nHD`)  
   - Fraction of sp³ carbons (`CSP3`)  
   - Ring Count (`RingCount`)  
   - Topological Polar Surface Area (`TPSA`)  
   - Number of Aromatic Rings (`NumAromaRing`)  
   - Number of Aliphatic Heterocycles (`ALHC`)  

3. **Feature Matrix & Labels**  
   - **X (features):** Molecular descriptors  
   - **y (target):** pChEMBL values  

4. **Model Training & Testing**  
   - Train/test split (90/10)  
   - Models tested:  
     - `RandomForestRegressor` (scikit-learn)  
     - (Optional: Linear Regression for baseline)  

5. **Evaluation Metrics**  
   - Mean Absolute Error (MAE)  
   - Mean Squared Error (MSE)  
   - Root Mean Squared Error (RMSE)  
   - R² score  

6. **Visualization**  
   - Scatter plot comparing predicted vs. actual values  
   - Perfect prediction line (`y=x`) as reference  

## 📦 Requirements

Install dependencies via pip:

```bash
pip install pandas scikit-learn matplotlib rdkit-pypi