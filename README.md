{
  "title": "JSE-Eskom Infrastructure-Coupled Financial Network Dataset: Hypergraph Edge Weights, Grid Dispatch Signals, and Adversarial Stress Events (IST-02 and IST-03 Series)",
  "description": "<p>Daily and intraday hypergraph edge-weight time series linking <strong>87 JSE-listed securities</strong> across 11 GICS sectors to <strong>34 Eskom transmission grid nodes</strong>, spanning January 2015&ndash;December 2025 (<em>T</em>&nbsp;=&nbsp;2,870 trading days, |<em>E</em>|&nbsp;=&nbsp;340 hyperedges). Constructed from Yahoo Finance equity data and publicly available Eskom Grid Code dispatch records.</p><h3>Supported Research Series</h3><p><strong>IST-02: Infrastructure-Stressed Topology</strong><br/>CASCADEnt and VORTEX framework papers on trophic downgrading and ecological collapse in financial hypergraphs. Graph entropy collapse from S&nbsp;=&nbsp;3.21 to S&nbsp;=&nbsp;1.38 under Stage&nbsp;4+ load-shedding; Trophic Downgrading Coefficient (TDC) and Network Degradation Index (NDI). Target journal: <em>Quantitative Finance and Economics</em> (AIMS Press, Diamond Open Access).</p><p><strong>IST-03: Infrastructure-Stressed Thermodynamics</strong><br/>Nine-paper series on large deviation theory and adversarial detection in physics-constrained financial networks. Includes benchmark adversarial perturbation runs (PGD, &epsilon;&nbsp;&isin;&nbsp;{0.01,&nbsp;0.05,&nbsp;0.10,&nbsp;0.20}) against LSTM, GraphSAGE, and Wasserstein autoencoder surrogate models for the test window July&ndash;December&nbsp;2022 (60 attack runs total). PHYSAN detector achieves monotone AUROC 0.951&rarr;0.991, FDR 3.2%, 89-hour detection lead time for the July&nbsp;2022 Stage&nbsp;6 event. Target journal: <em>Physical Review E</em> (APS).</p><h3>Dataset Parameters</h3><ul><li>Securities (JSE): 87 across 11 GICS sectors</li><li>Grid nodes (Eskom): 34 transmission nodes</li><li>Hyperedges: 340</li><li>Trading days: 2,870 (Jan 2015&ndash;Dec 2025)</li><li>Reference window T&#8320;: 1,130 days (Jan 2015&ndash;Jun 2019)</li><li>Effective sample size T&#8203;<sub>eff</sub>: ~412 (reference), ~30 (rolling)</li><li>Correlation time &tau;&#8203;<sub>corr</sub>: 2.74 days (daily), ~3.2&nbsp;h (intraday)</li></ul><p><strong>Version history:</strong> v1.0.0 covers January 2015&ndash;December 2025. A post-June 2025 extension will be released as v2.0.0. Cite the <strong>Concept DOI</strong> in all papers so citations remain valid after the v2.0.0 update.</p>",
  "creators": [
    {
      "name": "Moroke, Ntebogang Dinah",
      "affiliation": "Faculty of Economic and Management Sciences, North-West University, Mafikeng Campus, South Africa",
      "orcid": "0000-0000-0000-0000"
    }
  ],
  "keywords": [
    "JSE",
    "Eskom",
    "hypergraph",
    "financial networks",
    "infrastructure stress",
    "trophic downgrading",
    "large deviation theory",
    "adversarial detection",
    "South African financial markets",
    "physics of finance",
    "CASCADEnt",
    "VORTEX",
    "PHYSAN",
    "Cramér rate function",
    "Sanov theorem",
    "IST-02",
    "IST-03"
  ],
  "license": "cc-by-4.0",
  "upload_type": "dataset",
  "access_right": "open",
  "language": "eng",
  "version": "1.0.0",
  "notes": "Cite the Concept DOI (resolves to latest version) in all IST-02 and IST-03 papers. Do not cite the Version DOI in journal submissions, as a v2.0.0 update is planned for post-June 2025 data.",
  "related_identifiers": [
    {
      "identifier": "https://github.com/ndmoroke/IST-JSE-Eskom-Dataset",
      "relation": "isSupplementTo",
      "scheme": "url"
    }
  ]
}

%% ============================================================
%% BIB ENTRY TEMPLATE — IST-02 and IST-03 data citation
%% Replace XXXXXXX with the Concept DOI number from Zenodo
%% Use this SINGLE entry in ALL IST-02 and IST-03 papers
%% ============================================================

@dataset{moroke2026istdata,
  author    = {Moroke, Ntebogang Dinah},
  title     = {{JSE-Eskom Infrastructure-Coupled Financial Network Dataset:
                Hypergraph Edge Weights, Grid Dispatch Signals, and
                Adversarial Stress Events (IST-02 and IST-03 Series)}},
  year      = {2026},
  month     = mar,
  publisher = {Zenodo},
  version   = {1.0.0},
  doi       = {10.5281/zenodo.XXXXXXX},
  url       = {https://doi.org/10.5281/zenodo.XXXXXXX},
  note      = {Concept DOI---resolves to latest version.
               v1.0.0: Jan 2015--Dec 2025 (T=2870 trading days,
               87 JSE securities, 34 Eskom nodes, 340 hyperedges).
               v2.0.0 planned post-June 2025.}
}

%% ============================================================
%% DATA AVAILABILITY STATEMENT — IST-02 papers (QFE / topology)
%% ============================================================
%%
%% The data supporting the findings of this study are openly
%% available on Zenodo at https://doi.org/10.5281/zenodo.XXXXXXX
%% \cite{moroke2026istdata}. The dataset includes JSE equity
%% prices sourced from Yahoo Finance and Eskom dispatch signals
%% from publicly available Grid Code records.
%%
%% ============================================================
%% DATA AVAILABILITY STATEMENT — IST-03 papers (PRE / thermodynamics)
%% ============================================================
%%
%% The data supporting the findings of this study are openly
%% available on Zenodo at https://doi.org/10.5281/zenodo.XXXXXXX
%% \cite{moroke2026istdata}. The dataset includes JSE equity
%% prices sourced from Yahoo Finance and Eskom dispatch signals
%% from publicly available Grid Code records. All adversarial
%% perturbation code is included in the repository.
%%
%% ============================================================

## IST-03 JSE–Eskom Dataset — v1.0.0

**Release date:** March 2026
**Coverage:** January 2015 – December 2025 (T = 2,870 trading days)

### What this release contains

This is the **initial archival release** of the IST-03 JSE–Eskom
Infrastructure-Coupled Financial Network Dataset, supporting all nine
papers in the IST-03 series.

#### Data files
- `jse_equity_prices_2015_2025.csv` — OHLCV for 87 JSE securities
- `eskom_dispatch_signals_2015_2025.csv` — Eskom Grid Code dispatch, 34 nodes
- `hypergraph_edge_weights_daily.csv` — 340 hyperedge weights, 2,870 days
- `hypergraph_edge_weights_intraday.csv` — 96-period intraday windows
- `reference_window_T0.csv` — healthy baseline Jan 2015 – Jun 2019
- `adversarial_perturbations/` — 60 PGD attack runs (4 ε-budgets × 5 seeds × 3 surrogates)
- `july2022_forensic_window.csv` — July 2022 Stage 6 event window

#### Code files
- `construct_hypergraph.py` — hyperedge weight construction pipeline
- `compute_kl_divergence.py` — PHYSAN KL divergence estimator
- `run_pgd_attack.py` — PGD adversarial perturbation generator
- `reproduce_table3.py` — reproduce AUROC/FDR/DLT results (IST-03 Paper 1)

### Citation

When citing, use the **Concept DOI** so your citation stays valid after
the planned v2.0.0 update (post-June 2025 data extension):

```
https://doi.org/10.5281/zenodo.XXXXXXX  ← Concept DOI (all versions)
```

### Planned next release
**v2.0.0** (~July 2025): extended time series incorporating post-June 2025
JSE and Eskom data. The Concept DOI will resolve to v2.0.0 automatically.
