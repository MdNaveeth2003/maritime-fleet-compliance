# maritime-fleet-compliance

## Key Results Summary

### Fleet-Wide GHG Intensity
- Average intensity: **88.07 kg CO₂ per unit distance**
- 2026 regulatory target (5% reduction): **83.67 kg CO₂ per unit distance**
- **68 vessels** in Surplus (compliant)
- **52 vessels** in Deficit (at risk of penalty)

### Machine Learning Model (Task A)
A **linear regression model** predicts CO₂ emissions using:
- One-hot encoded `ship_type`
- `distance`
- `fuel_consumption`

**Performance**:
- Mean Absolute Error (MAE): **~617 kg** on training data
- Fuel consumption dominates (coefficient ≈ 2.76), confirming strong physical correlation
- Ship type adds meaningful adjustments (e.g., Tankers have higher baseline)

The model is simple, interpretable, and suitable for regulatory forecasting.

### Dashboard Features (Task B)
- **Liability Map**: Color-coded table and chart showing penalty risk levels (Surplus, Low/Medium/High Deficit)
- **Pooling Simulator**: Interactive tool to pair a Deficit vessel with a Surplus vessel and instantly see if pooling eliminates the penalty (with estimated $ savings at $100/kg excess CO₂)

### Anomaly Insight (Task C)
Identified a clear fuel consumption outlier (vessel NG077, June trip) due to **stormy weather** causing increased hydrodynamic and aerodynamic resistance – a real physical effect, not sensor error.

## Setup & Running Instructions

### Requirements
- Python 3.8+
- Jupyter Notebook or JupyterLab
- Anaconda recommended (handles dependencies easily)

### Installation
```bash
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Create and activate a conda environment (recommended)
conda create -n fleet-compliance python=3.11 -y
conda activate fleet-compliance

# Install dependencies
pip install pandas numpy matplotlib ipywidgets scikit-learn
