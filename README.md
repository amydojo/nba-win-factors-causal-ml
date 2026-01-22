# NBA Win Factors: Causal ML Analysis 🏀🔍

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)

**Causal discovery + interpretable ML** to identify which on-court factors *actually* drive NBA wins  
(2016–2017 season, game-level + player-level statistics).

🔗 **Live interactive causal network:** https://amydojo.github.io/nba-win-factors-causal-ml/

---

## TL;DR (what this is)

Most sports analytics ends at correlation (“this stat moves with wins”).  
This project goes further: it **learns a causal structure** over team performance metrics and then uses **interpretable ML** to validate and explain predictive signals.

**Core question:**
> **Which stats are likely influencing wins—not just associated with winning?**

---

## Portfolio Highlights ✨

- **End-to-end pipeline:** NBA data → preprocessing → causal discovery → interpretable modeling → shipped visualization
- **Causal graph (DAG) learned from data** using `causalnex`
- **Interpretable models** (decision trees + feature importance) for explainability
- **Publish-ready artifact:** interactive causal network hosted on GitHub Pages

---

## Key Outputs (fast links)

- 🌐 **Interactive causal network (GitHub Pages):** https://amydojo.github.io/nba-win-factors-causal-ml/  
- 📄 **Full report:** [`reports/STATS 295 Final Report.pdf`](reports/STATS%20295%20Final%20Report.pdf)  
- 🧠 **Pruned decision tree explanation:** [`reports/pruned_dt_explation.pdf`](reports/pruned_dt_explation.pdf)  
- 🧩 **Network HTML source:** [`outputs/nba_network.html`](outputs/nba_network.html)

---

## What I Built

### 1) Data (NBA API)
- **Source:** NBA API via `nba_api`
- **Season:** 2016–2017  
- **Scope:** game-level team stats + player-level stats  
  (shooting %, rebounds, assists, turnovers, steals, blocks, etc.)

### 2) Causal Discovery (CausalNex)
Using `causalnex`, the workflow:
- identifies conditional independencies
- learns a **directed acyclic graph (DAG)** structure
- represents dependencies via Bayesian networks to reduce “correlation-only” conclusions

### 3) Interpretable ML
Models are used to validate predictive signals and keep the explanation readable:
- **Decision Tree (pruned)** — clear logic and human-auditable rules
- **Random Forest** — feature importance checks
- **Feature engineering** — derived indicators from box score inputs

---

## Results (high-level)

The learned structure and modeling prioritize a few consistent themes:

- **shooting efficiency** (FG%, 3P%, FT%)  
- **possession quality** (assists, turnovers)  
- **rebounding + defensive activity**  
- **player-level contribution patterns** feeding into team outcomes

For full methodology + charts + interpretation, see the report:  
➡️ [`reports/STATS 295 Final Report.pdf`](reports/STATS%20295%20Final%20Report.pdf)

---

## Run Locally

### Prerequisites
- Python **3.11+**
- pip

### Install
```bash
git clone https://github.com/amydojo/nba-win-factors-causal-ml.git
cd nba-win-factors-causal-ml
pip install -r requirements.txt
```

### Launch Notebook
```bash
jupyter notebook
```

Open and run:
- `notebooks/STAT295_Project_2.ipynb`

### Input Data Files
Located in `data/processed/`:
- `nba_games_cleaned.csv` — cleaned team game statistics  
- `nba_players_2016_2017.csv` — player stats for 2016–2017

---

## Repo Structure

```
nba-win-factors-causal-ml/
│
├── notebooks/
│   └── STAT295_Project_2.ipynb        # main analysis notebook
│
├── data/
│   └── processed/
│       ├── nba_games_cleaned.csv      # cleaned team game statistics
│       └── nba_players_2016_2017.csv  # player stats (2016–2017)
│
├── outputs/
│   └── nba_network.html               # interactive causal network
│
├── reports/
│   ├── STATS 295 Final Report.pdf     # full written report
│   └── pruned_dt_explation.pdf        # decision tree explanation
│
├── docs/
│   └── index.html                     # GitHub Pages entry (network)
│
├── requirements.txt                   # Python dependencies
├── README.md
└── LICENSE
```

---

## Tech Stack

- **Data:** `pandas`, `numpy`, `nba_api`  
- **Causal inference:** `causalnex`  
- **ML:** `scikit-learn`, `xgboost`, `lightgbm`  
- **Viz:** `matplotlib`, `seaborn`, `plotly`, `networkx`  
- **Environment:** `jupyter`, `ipykernel`

---

## Future Work
- extend to multiple seasons (2015–2024)
- incorporate temporal dynamics (momentum, streaks)
- playoff vs. regular season comparison
- causal effect estimation (treatment effects)
- interactive dashboard for exploration + predictions

---

## License
MIT — see [`LICENSE`](LICENSE)

---

## Acknowledgments
- NBA data access: [`nba_api`](https://github.com/swar/nba_api)
- Causal inference foundations influenced by Judea Pearl’s work
- Built for STATS 295

---

## Contact
Want to collaborate, fork this, or extend the analysis? Open an issue.
