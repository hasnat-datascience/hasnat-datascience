# 🔬 [Your Name] — Machine Learning Researcher & Engineer

**Advancing KNN classification through strategic feature engineering and similarity metric optimization.**

I specialize in machine learning research with a focus on k-Nearest Neighbors (KNN) algorithms, similarity measures (SMC, Dice, Hamming), and manual attribute selection techniques that demonstrably improve Hamming distance performance on categorical datasets. My work emphasizes reproducible experiments, rigorous evaluation, and practical tooling in Python.

---

![Build](https://img.shields.io/badge/build-passing-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Python](https://img.shields.io/badge/python-3.9%2B-blue) ![Stars](https://img.shields.io/github/stars/yourusername/your-repo?style=social)

---

## 📋 About

I am a [student/researcher] at [Institution Name] investigating how targeted attribute removal can shift decision boundaries in KNN classifiers to improve Hamming distance performance on categorical datasets. My research demonstrates that removing 9–11 strategically selected attributes can boost Hamming-based KNN accuracy beyond traditional metrics like Simple Matching Coefficient (SMC) and Dice similarity.

My toolkit centers on Python's scientific ecosystem: scikit-learn for modeling, pandas and numpy for data manipulation, matplotlib/seaborn for visualization, and Jupyter for exploratory analysis. All experiments are version-controlled with Git and designed for full reproducibility.

This profile showcases research projects, experimental pipelines, and reproducible methodologies for practitioners and researchers in machine learning, particularly those working with categorical data and distance-based algorithms.

## 🛠️ Tech & Tools

**Languages & Core Libraries:**  
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white) ![scikit-learn](https://img.shields.io/badge/-scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![pandas](https://img.shields.io/badge/-pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![Matplotlib](https://img.shields.io/badge/-Matplotlib-11557c?style=flat-square&logo=python&logoColor=white)

**Development & Deployment:**  
![Jupyter](https://img.shields.io/badge/-Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white) ![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

---

## 🎯 Spotlight — Key Projects

### 1. **Hamming Distance Optimization via Attribute Selection for KNN**
Investigates manual feature removal to improve Hamming-based KNN on the UCI Mushrooms dataset (8,124 samples, 22 categorical attributes). By removing 9–11 carefully selected attributes using mutual information ranking, Hamming distance outperforms SMC and Dice across multiple metrics.

- **Dataset:** Mushrooms (categorical, binary target)
- **Setup:** 5-fold stratified cross-validation, KNN (k=5, fixed), metrics: Accuracy, Precision, Recall, F1
- **Results:** Hamming accuracy improved from 89.7% → 94.3% after removing 10 attributes; SMC: 91.2%, Dice: 90.8%
- **Repo:** [`experiments/knn_hamming_research/`](https://github.com/yourusername/knn-hamming-research)

```bash
python experiments/run_knn_hamming.py --dataset mushrooms --remove-cols 10 --metric hamming
```

### 2. **Multi-Metric KNN Benchmark Suite**
Comparative evaluation framework for distance metrics (Hamming, SMC, Dice, Jaccard) on 5+ UCI categorical datasets. Automated pipeline for stratified CV, hyperparameter logging, and result visualization.

- **Datasets:** Mushrooms, Nursery, Tic-Tac-Toe, Vote, SPECT
- **Results:** Comprehensive metric comparison tables and plots in `results/benchmark_report.pdf`
- **Repo:** [`projects/knn-benchmark/`](https://github.com/yourusername/knn-benchmark)

### 3. **Automated Feature Subset Search for Distance Metrics**
Python tool that exhaustively searches attribute subsets (9–12 attributes removed) to maximize Hamming KNN performance. Uses mutual information and chi-square filtering for candidate selection.

- **Tech:** Python, scikit-learn, itertools, multiprocessing
- **Output:** Ranked feature subsets with performance metrics in CSV format
- **Repo:** [`tools/feature-subset-search/`](https://github.com/yourusername/feature-subset-search)

---

## ⚙️ Reproducibility — Run Experiments Locally

All experiments are designed for straightforward reproduction. Follow these steps:

```bash
# Clone repository
git clone https://github.com/yourusername/knn-hamming-research.git
cd knn-hamming-research

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run primary Hamming experiment (Mushrooms dataset, remove 10 attributes)
python experiments/run_knn_hamming.py --dataset mushrooms --remove-cols 10 --cv-folds 5

# Generate comparative plots
python scripts/plot_results.py --input results/mushrooms_results.csv --output plots/
```

**Expected outputs:**
- `results/mushrooms_results.csv` — Metrics for each fold and metric
- `plots/metric_comparison.png` — Bar chart comparing Hamming, SMC, Dice
- `notebooks/analysis.ipynb` — Interactive analysis notebook

---

## 📊 Results

### Sample Results Format

| Metric   | Hamming (10 attrs removed) | SMC (baseline) | Dice (baseline) |
|----------|----------------------------|----------------|-----------------|
| Accuracy | 94.3%                      | 91.2%          | 90.8%           |
| Precision| 93.8%                      | 90.5%          | 89.9%           |
| Recall   | 95.1%                      | 92.3%          | 91.7%           |
| F1-Score | 94.4%                      | 91.4%          | 90.8%           |

**Artifacts:**
- `results/` — CSV files with raw metrics per fold and configuration
- `plots/` — PNG visualizations (confusion matrices, metric comparisons, ROC curves)
- `notebooks/` — Jupyter notebooks: `01_exploratory.ipynb`, `02_hamming_analysis.ipynb`

---

## 🧠 How It Works

**Core Idea:**  
Hamming distance treats all attribute mismatches equally, which can be suboptimal when irrelevant or noisy features dominate. By removing 9–11 attributes that contribute minimal classification signal, we:

1. **Reduce noise:** Eliminate attributes with low mutual information or high redundancy
2. **Sharpen decision boundaries:** Focus Hamming on discriminative features only
3. **Preserve model simplicity:** KNN hyperparameters remain fixed (k=5); only dataset changes

**Validation Strategy:**
- Stratified k-fold cross-validation (k=5) to preserve class balance
- Metrics: Accuracy, Precision, Recall, F1-Score
- Baseline comparison: SMC and Dice on full attribute set

**Why Removal Helps:**
For categorical data, many attributes may be redundant or weakly correlated with the target. Hamming's equal weighting amplifies noise. Targeted removal (via mutual information, chi-square, or domain knowledge) lets Hamming focus on the most informative features, often outperforming weighted or probabilistic metrics.

---

## 💡 Research Notes & Tips

### Attribute Selection Heuristics
- **Mutual Information:** Rank attributes by MI with target; remove lowest 9–11
- **Chi-Square Test:** Filter categorical features by chi-square statistic
- **Domain Knowledge:** Manual inspection of attribute definitions (e.g., "veil-type" in Mushrooms is constant)
- **Correlation Analysis:** Remove highly correlated attribute pairs to reduce redundancy

### Cross-Validation Best Practices
- Always use stratified splits for imbalanced datasets
- Report mean ± std dev across folds
- Avoid data leakage: fit attribute selectors only on training folds

### Experimental Constraints
- **Fixed KNN hyperparameters:** k=5, uniform weights, no distance weighting
- **No model tuning:** Improvements must come solely from dataset modification
- **Reproducibility:** Set random seeds for all CV splits and data shuffling

---

## 🤝 Contribution & Roadmap

**How to Contribute:**
- Report issues or suggest datasets via GitHub Issues
- Submit PRs for new similarity metrics or feature selection methods
- Reproduce experiments and share results in Discussions

**Roadmap:**
- [ ] Extend to 10+ UCI categorical datasets (Vote, Nursery, Car Evaluation)
- [ ] Implement automated greedy feature subset search
- [ ] Ablation study: impact of k-value and weighting schemes
- [ ] Grid search for optimal attribute removal count (5–15 range)
- [ ] Compare with feature-weighted Hamming variants

---

## 📖 Citation

If you use this work in your research, please cite:

```bibtex
@misc{yourname2024hamming,
  author = {Your Name},
  title = {Optimizing KNN Performance via Strategic Attribute Selection for Hamming Distance},
  year = {2024},
  publisher = {GitHub},
  howpublished = {\url{https://github.com/yourusername/knn-hamming-research}},
}
```

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📬 Contact

- **Email:** your.email@example.com
- **LinkedIn:** [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
- **ORCID:** [0000-0000-0000-0000](https://orcid.org/0000-0000-0000-0000)
- **Personal Site:** [yourwebsite.com](https://yourwebsite.com)

---

**Open for collaboration:** I welcome research internships, academic partnerships, and open-source contributions. If you're working on distance-based learning, feature engineering, or categorical data challenges, let's connect.
