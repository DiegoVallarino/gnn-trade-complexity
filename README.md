# gnn-trade-complexity

**Code companion for the paper**: *Augmenting Trade Complexity Analysis with Deep Learning: An AI-Based Framework for Small Open Economies*  
**Author**: Diego Vallarino, Inter-American Development Bank (IDB)

---

## Overview

This repository contains a Colab-compatible Python implementation of the full pipeline presented in the paper. It integrates:

- Graph Neural Networks (GNNs) for trade complexity prediction
- Synthetic trade disruption scenarios via GANs
- Node-level explainability using Integrated Gradients
- Visual diagnostics and product-level diversification recommendations

The approach is tailored for **small open economies** under conditions of global volatility, using structural features and macroeconomic constraints to guide diversification strategies.

---

## Files

- `python_code`: Complete, executable notebook with all model steps.

---

## Requirements

Recommended Python version: `>=3.9`

Install dependencies via pip:
```bash
pip install torch torchvision torchaudio
pip install torch-geometric torch-scatter torch-sparse -f https://data.pyg.org/whl/torch-2.0.0+cpu.html
pip install pandas numpy matplotlib seaborn scikit-learn networkx captum
```

---

## How to Use

### Option 1: Google Colab (recommended)
1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload your data (see section below)
3. Run each cell step by step

### Option 2: Local execution
1. Clone this repository
2. Install requirements
3. Run the notebook using Jupyter Lab or VS Code

---

## Required Datasets

This notebook does not include raw datasets. You must extract and preprocess the following data from **public sources**:

| Dataset | Description | Suggested Source |
|--------|-------------|------------------|
| **Export data** | Bilateral exports by country-product-year (HS-6) | CEPII BACI database |
| **PCI (Product Complexity Index)** | Product-level complexity score | Atlas of Economic Complexity |
| **Macroeconomic variables** | GDP per capita, FDI, inflation, population | World Bank WDI |
| **R&D intensity (optional)** | By sector/product | OECD STAN or UNESCO UIS |
| **Product proximity matrix** | Pairwise relatedness between products | Computed from co-export patterns |

Please ensure the trade matrix is filtered using **RCA ≥ 1** before loading into the model.

---

## Outputs

- ECI predictions per node
- Top recommended products for export diversification
- GNN embedding visualization
- Explainability plots with feature attributions
- Simulated trade shocks via GANs

---

## Methodology

The methodology replicates the architecture and logic described in the paper, including:
- GCN architecture (2-layer, ReLU, Adam optimizer)
- Prediction of future ECI using product/country node features
- GAN simulation of tariff or demand shocks
- Attribution of importance via Captum’s Integrated Gradients

For full methodology, see Appendix A of the paper.

---

## Citation

If you use this code, please cite the associated paper:

```
Vallarino, D. (2025). Augmenting trade complexity analysis with deep learning: an AI-based framework for small open economies. Applied Economics Letters, 1–4. https://doi.org/10.1080/13504851.2025.2567618
```

---

## Contact

For questions or collaboration:
- Email: diego.vallarino@gmail.com
- ORCID: https://orcid.org/0009-0003-9166-1874

---

## License

This repository is released for academic and research purposes under an open, non-commercial license. Please contact the author for reuse in policy or commercial contexts.
