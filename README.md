# ML Screening of Amine Sorbents for Post-Combustion CO₂ Capture

## Project Overview
This project applies machine learning to **screen amine-based sorbents** for post-combustion CO₂ capture. It predicts **working capacity** and **regeneration energy** from molecular descriptors, providing a **multi-objective ranking** with uncertainty quantification.

## Motivation
Experimental testing of sorbents is **time-consuming and costly**. ML can triage candidates rapidly and guide experimental design, improving efficiency in carbon capture research.

## Dataset
- Features: molecular weight, boiling point, pKa proxy, H-bond donors/acceptors, ring count, amine type, process conditions (T, P, CO₂ fraction)
- Targets: `working_capacity_mmol_g`, `regen_energy_kJ_mol`
- Data cleaning: missing values handled, outliers winsorized, units harmonized

## Methodology
1. **EDA & Cleaning** – ensured tidy dataset  
2. **Train/Cal/Test Split** – grouped by source to avoid leakage  
3. **Models Tried**: Ridge, Random Forest, Gradient Boosting  
4. **Model Selection**: Random Forest selected (best MAE & RMSE)  
5. **Uncertainty Quantification** – conformal prediction with 90% intervals  
6. **Feature Importance** – H-bond donors most important  
7. **Multi-objective Ranking** – balancing capacity ↑ and regeneration energy ↓

## Results
- **Random Forest Accuracy**  
  - Capacity MAE ≈ 0.31 mmol/g  
  - Capacity RMSE ≈ 0.42 mmol/g  
  - Regen MAE ≈ 4.24 kJ/mol  
  - Regen RMSE ≈ 6.60 kJ/mol  

- **Top-ranked Sorbents**  
  1. PEHA  
  2. Tris(2-aminoethyl)amine  
  3. AEEA  
  4. TETA  
  5. Bis(aminopropyl)amine  

## Usage
1. Clone the repository  
2. Install dependencies: `pip install -r requirements.txt`  
3. Run notebook for full workflow: `ML Screening of Amine Sorbents for Post-Combustion CO₂ Capture.ipynb`


## Notes
- This workflow is **screening aid only**; experimental validation required.  
- Model uncertainty is explicitly captured via conformal prediction.  
- Chemical intuition aligns with feature importance results.

## Author
- Collins I. Chukwuma

