# NBA Win Factors: Causal ML Analysis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)

> Causal discovery + interpretable ML to identify key factors behind NBA wins (2016–2017 season)

## 📋 Project Summary

This project combines **causal inference** and **interpretable machine learning** to analyze what factors truly drive NBA team success. Rather than just finding correlations, we use causal discovery algorithms to understand the cause-and-effect relationships between team statistics and winning outcomes.

**Key objectives:**
- Identify causal relationships between NBA team statistics and wins
- Build interpretable ML models to predict game outcomes
- Quantify the impact of different performance factors
- Provide actionable insights backed by rigorous statistical analysis

**Interactive visualization:** [View the causal network →](https://amydojo.github.io/nba-win-factors-causal-ml/)

## 🔬 Methods

### Data Collection
- **Source:** NBA API (`nba_api` package)
- **Period:** 2016-2017 season
- **Scope:** Team-level and player-level game statistics including shooting percentages, rebounds, assists, turnovers, steals, and blocks

### Causal Discovery
We apply causal discovery algorithms using the `causalnex` library:
- Identifies conditional independence relationships
- Constructs a directed acyclic graph (DAG) representing causal connections
- Distinguishes correlation from causation using Bayesian networks

### Interpretable Machine Learning
Multiple models are trained to validate causal findings:
- **Random Forest:** Ensemble learning with built-in feature importance
- **Decision Trees:** Interpretable tree-based models with pruning
- **Feature Engineering:** Advanced statistical features from game data

## 📊 Results

See the [full report](reports/STATS%20295%20Final%20Report.pdf) for detailed findings and analysis.

### Key Findings

The analysis reveals the causal structure of factors influencing NBA game outcomes, with particular focus on:
- Shooting efficiency metrics (field goal %, 3-point %, free throw %)
- Ball movement and possession (assists, turnovers)
- Rebounding and defensive statistics
- Player-level contributions to team success

### Interactive Visualization

An [interactive network diagram](https://amydojo.github.io/nba-win-factors-causal-ml/) visualizes the discovered causal relationships between NBA statistics and game outcomes.

## 🚀 How to Run

### Prerequisites
- Python 3.11 or higher
- pip package manager

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/amydojo/nba-win-factors-causal-ml.git
cd nba-win-factors-causal-ml
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Launch Jupyter**
```bash
jupyter notebook
```

### Running the Analysis

Open and run the main analysis notebook:

**`notebooks/STAT295_Project_2.ipynb`**
- Fetches NBA data using the NBA API
- Performs data cleaning and preprocessing
- Conducts causal discovery using CausalNex
- Builds and evaluates machine learning models
- Generates visualizations and exports results

The notebook uses the preprocessed data files in `data/processed/`:
- `nba_games_cleaned.csv` - Cleaned team game statistics
- `nba_players_2016_2017.csv` - Player-level statistics for 2016-2017 season

## 📁 File Tour

```
nba-win-factors-causal-ml/
│
├── notebooks/
│   └── STAT295_Project_2.ipynb        # Main analysis notebook
│
├── data/
│   └── processed/
│       ├── nba_games_cleaned.csv      # Cleaned team statistics
│       └── nba_players_2016_2017.csv  # Player statistics (2016-17)
│
├── outputs/
│   └── nba_network.html               # Interactive causal network visualization
│
├── reports/
│   ├── STATS 295 Final Report.pdf     # Comprehensive project report
│   └── pruned_dt_explation.pdf        # Decision tree model explanation
│
├── docs/
│   └── index.html                      # GitHub Pages site (causal network)
│
├── requirements.txt                    # Python dependencies
├── README.md                           # This file
└── LICENSE                             # MIT License
```

## 🛠️ Technology Stack

- **Data:** `pandas`, `numpy`, `nba_api`
- **Causal Inference:** `causalnex`
- **Machine Learning:** `scikit-learn`, `xgboost`, `lightgbm`
- **Visualization:** `matplotlib`, `seaborn`, `plotly`, `networkx`
- **Environment:** `jupyter`, `ipykernel`

## 📈 Future Work

- [ ] Extend analysis to multiple NBA seasons (2015-2024)
- [ ] Incorporate temporal dynamics (momentum, streaks)
- [ ] Add playoff vs. regular season comparison
- [ ] Develop causal effect estimation with treatment effects
- [ ] Build interactive dashboard for real-time predictions

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- NBA data provided by [nba_api](https://github.com/swar/nba_api)
- Causal inference methods inspired by Judea Pearl's work
- Statistical analysis course: STATS 295

## 📧 Contact

For questions or collaboration opportunities, please open an issue on this repository.

---

**Made with 🏀 and 🤖 by causal ML enthusiasts**
