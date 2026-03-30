# IST JSE–Eskom Infrastructure-Coupled Financial Network Dataset

[![DOI](https://zenodo.org/badge/latestdoi/ndmoroke/IST-JSE-Eskom-Dataset.svg)](https://zenodo.org/badge/latestdoi/ndmoroke/IST-JSE-Eskom-Dataset)
**License:** CC-BY-4.0 | **Version:** 1.0.0 | **Coverage:** Jan 2015 – Dec 2025

---

## Overview

This repository is the **unified data and code archive** for two interconnected
research series by Prof. N.D. Moroke (North-West University, South Africa):

| Series | Full Name | Framework | Target Journal |
|---|---|---|---|
| **IST-02** | Infrastructure-Stressed Topology | CASCADEnt / VORTEX | *Quantitative Finance and Economics* |
| **IST-03** | Infrastructure-Stressed Thermodynamics | PHYSAN + 8 more | *Physical Review E* + APS journals |

Both series draw on the **same JSE-Eskom hypergraph dataset**, ensuring full
cross-paper consistency and enabling direct comparison of topology-based and
thermodynamics-based detection approaches.

---

## Dataset Summary

| Variable | Value |
|---|---|
| JSE securities | 87 across 11 GICS sectors |
| Eskom grid nodes | 34 transmission nodes |
| Hyperedges | 340 |
| Trading days | 2,870 (Jan 2015 – Dec 2025) |
| Reference window T₀ | 1,130 days (Jan 2015 – Jun 2019) |
| Effective sample size T_eff | ~412 (reference), ~30 (rolling) |
| Correlation time τ_corr | 2.74 days (daily), ~3.2 h (intraday) |
| ε_spin (spinning reserve) | 0.177 ± 0.009 |

---

## Repository Structure

```
IST-JSE-Eskom-Dataset/
│
├── data/
│   ├── raw/
│   │   ├── jse_equity_prices_2015_2025.csv        # Yahoo Finance OHLCV, 87 securities
│   │   ├── eskom_dispatch_signals_2015_2025.csv   # Grid Code dispatch, 34 nodes
│   │   └── gics_sector_mapping.csv                # GICS sector classification
│   │
│   ├── processed/
│   │   ├── hypergraph_edge_weights_daily.csv      # |E|=340, T=2870 daily weights
│   │   ├── hypergraph_edge_weights_intraday.csv   # 96-period intraday windows
│   │   ├── reference_window_T0.csv                # Healthy baseline Jan2015-Jun2019
│   │   ├── graph_entropy_series.csv               # S_t for IST-02 trophic analysis
│   │   ├── trophic_level_assignments.csv          # Node trophic levels (IST-02)
│   │   └── adversarial_perturbations/             # IST-03 PGD attack runs
│   │       ├── pgd_eps001_5seeds.npz              # ε=0.01, 5 random seeds
│   │       ├── pgd_eps005_5seeds.npz              # ε=0.05
│   │       ├── pgd_eps010_5seeds.npz              # ε=0.10
│   │       └── pgd_eps020_5seeds.npz              # ε=0.20
│   │
│   └── events/
│       ├── july2022_forensic_window.csv           # July 2022 Stage 6 event (IST-03)
│       ├── loadshedding_stage_timeline.csv        # Full 2015-2025 stage record
│       └── event_metadata.json                   # All IST-02/03 forensic events
│
├── code/
│   ├── ist02/
│   │   ├── construct_trophic_levels.py            # Node trophic level assignment
│   │   ├── compute_graph_entropy.py               # S_t = -Σ p_i log p_i
│   │   ├── run_cascadent_gat.py                   # CASCADEnt GAT model
│   │   └── compute_tdc_ndi.py                     # Trophic Downgrading Coefficient
│   │
│   └── ist03/
│       ├── construct_hypergraph.py                # Hyperedge weight construction
│       ├── compute_kl_divergence.py               # PHYSAN KL divergence estimator
│       ├── run_pgd_attack.py                      # PGD adversarial perturbation
│       ├── estimate_espin.py                      # ε̂_spin from dispatch quantile
│       └── reproduce_table3.py                   # AUROC/FDR/DLT results
│
├── CITATION.cff          # Machine-readable citation metadata
├── .zenodo.json          # Zenodo metadata override
├── LICENSE               # CC-BY-4.0
└── README.md             # This file
```

---

## IST-02 Paper Series (Infrastructure-Stressed Topology)

| Paper | Title (abbreviated) | Framework | Target Journal |
|---|---|---|---|
| IST-02 P1 | Trophic Downgrading in Financial Hypergraphs | CASCADEnt / VORTEX | *Quantitative Finance and Economics* |

**Key IST-02 results:**
- Graph entropy collapse: S = 3.21 → 1.38 under Stage 4+ load-shedding
- 73% elimination of complex (multi-party) financial interactions
- Trophic Downgrading Coefficient (TDC) and Network Degradation Index (NDI)
- GAT-based detection with attention weights = trophic interaction strength

---

## IST-03 Paper Series (Infrastructure-Stressed Thermodynamics)

| Paper | Title (abbreviated) | Framework | Target Journal |
|---|---|---|---|
| IST-03 P1 | PHYSAN adversarial detector | PHYSAN | *Physical Review E* |
| IST-03 P2 | COVID-19 multi-market stress | TBD | TBD |
| IST-03 P3 | South African sovereign crisis | TBD | TBD |
| IST-03 P4 | ERCOT Winter Storm Uri | TBD | TBD |
| IST-03 P5 | European energy shock 2021 | TBD | TBD |
| IST-03 P6 | Emerging market contagion | TBD | TBD |
| IST-03 P7 | UK 2022 energy crisis | TBD | TBD |
| IST-03 P8 | Post-COVID recovery dynamics | TBD | TBD |
| IST-03 P9 | Synthesis and open problems | TBD | TBD |

**Key IST-03 P1 results (PHYSAN):**
- AUROC: 0.951 → 0.991 (monotone ↑ with ε); baselines all degrade ↓
- FDR: 3.2% vs 18.4% (LSTM), 11.7% (IF), 9.3% (GMM)
- Detection lead time: 89 h before July 2022 Stage 6 loadshedding
- Threshold Δ* = 0.0648 derived from Grid Code (no training data)

---

## Citing This Dataset

Use the **Concept DOI** in all IST-02 and IST-03 paper citations:

```
Moroke, N.D. (2026). JSE-Eskom Infrastructure-Coupled Financial Network
Dataset: Hypergraph Edge Weights, Grid Dispatch Signals, and Adversarial
Stress Events (IST-02 and IST-03 Series) [Dataset]. Zenodo.
https://doi.org/10.5281/zenodo.XXXXXXX
```

> The Concept DOI always resolves to the latest version. Citing it
> ensures all paper citations remain valid when v2.0.0 is released
> (post-June 2025 data extension), with no corrections required.

---

## Data Availability Statement (copy-paste for journal submissions)

> The data supporting the findings of this study are openly available
> on Zenodo at https://doi.org/10.5281/zenodo.XXXXXXX (Moroke, 2026).
> The dataset includes JSE equity prices sourced from Yahoo Finance
> and Eskom dispatch signals from publicly available Grid Code records.
> All analysis code is included in the repository.

---

## Version History

| Version | Date | Changes |
|---|---|---|
| v1.0.0 | March 2026 | Initial release: Jan 2015 – Dec 2025 (T = 2,870 days) |
| v2.0.0 | ~post-June 2025* | Extended time series post-June 2025 |

*Planned. Concept DOI resolves to v2.0.0 automatically upon release.

---

## License

Released under [CC-BY-4.0](LICENSE). Free to use, share, and adapt with attribution.

# IST Series: Financial Metabolomics – Infrastructure‑Stressed Financial Networks and Thermodynamic Deep Learning

This deposit contains data, code, and supplementary materials for multiple research papers using the JSE–Eskom infrastructure‑coupled dataset. All materials are released under CC‑BY‑4.0.

## Repository Structure

- **`paper1_gws_stnet/`** – Code and data for Paper 1: Gaussian‑Weighted Swin Networks with Contractive Attention and Metabolic Saliency (JSE panel, 87 securities, 2,731 days).  
- **`paper2_metabolic_saliency/`** – Code for Paper 2: Metabolic Saliency as a KL‑Divergence Estimator (KSG, STIF, bootstrap).  
- **`paper3_fractal/`** – Placeholder for Paper 3: Fractal Conservation Law.  
- **`wow_e_w_quadrilogy/`** – Code and data for the earlier Quadrilogy papers (MS‑GARCH, GRU, Riemannian TDA, PPO portfolio).  
- **`ist02_trophic/`** – Code for IST‑02 trophic hypergraph analysis (optional).  
- **`ist03_physan/`** – Code for IST‑03 PHYSAN adversarial detector (optional).  
- **`README.md`** – This file.  
- **`CITATION.cff`** – Citation metadata.

## Dataset

The JSE–Eskom dataset is located in `paper1_gws_stnet/data/`. It includes aggregated sector‑level returns, volumes, realised variances, and aligned Eskom load‑shedding stages (Jan 2015 – Dec 2025). Raw individual security data are proprietary and not redistributed.

## Usage

See each paper’s subdirectory for installation instructions and example commands.

## License

Creative Commons Attribution 4.0 International (CC‑BY‑4.0).

## Citation

If you use this deposit, please cite:

> Moroke, N.D. (2026). IST Series: Financial Metabolomics – Infrastructure‑Stressed Financial Networks and Thermodynamic Deep Learning. Zenodo. https://doi.org/10.5281/zenodo.19072906
