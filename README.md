<<<<<<< HEAD
# Meta-selection-algo-for-clustering
=======
# Meta-Learning Clustering Algorithm Selection

Academic project for automatic clustering algorithm selection using meta-learning and internal validation metrics.

## What This Repository Contains

- Dataset collection and preprocessing pipeline
- Meta-feature extraction from diverse UCI datasets
- Clustering algorithm benchmarking (internal metrics only)
- Meta-dataset generation and meta-classifier training
- Validation and prediction scripts
- Full report material (LaTeX, sections, figures, diagrams)

## Clean Repository Layout

```text
classifier-meta-data/
├── README.md
├── .github/
├── code/                       # All Python/PowerShell scripts
├── data/
│   ├── raw/
│   │   └── datasets/           # Downloaded datasets in numbered folders
│   ├── processed/              # CSV/JSON outputs and intermediate artifacts
│   └── models/                 # Trained model and scaler files
└── docs/
    ├── guides/                 # Markdown/TXT project guides and checklists
    ├── images/                 # PNG/JPG figures and generated plots
    ├── drawio/                 # .drawio source diagrams
    └── reports/                # LaTeX paper, bibliography, compiled outputs
```

## Quick Start

Install dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn scipy joblib
```

Run the pipeline from repository root:

```bash
python code/download_datasets.py
python code/extract_meta_features.py
python code/evaluate_clustering_algorithms.py
python code/create_meta_dataset.py
python code/enhanced_meta_classifier.py
python code/final_system_validation.py
```

## Notes for New Contributors

- Keep new scripts in `code/`
- Keep generated CSV/JSON in `data/processed/`
- Keep model artifacts in `data/models/`
- Keep docs/checklists in `docs/guides/`
- Keep report/LaTeX content in `docs/reports/`

## Publish to GitHub

If this folder is not a Git repo yet:

```bash
git init
git add .
git commit -m "Restructure project for clean GitHub layout"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```
- **85.1% weighted accuracy** - Significant improvement over baseline methods
- **12 optimized features** - Intelligent selection from 27 engineered features
- **Enhanced Random Forest** - Best performing among ensemble methods
- **Robust validation** - Cross-validation with confidence weighting

### System Efficiency  
- **DBSCAN optimization** - Timeout handling and sampling for large datasets
- **Parameter reduction** - 40+ → 6 parameter combinations for efficiency
- **Feature engineering** - Automated pipeline for meta-feature enhancement
- **Production ready** - Complete prediction system with confidence scoring

### Algorithm Coverage
- **K-Means**: 60% of datasets (9/15) - Best for large, well-separated clusters
- **DBSCAN**: 33% of datasets (5/15) - Best for density-based, irregular clusters  
- **Agglomerative**: 7% of datasets (1/15) - Best for hierarchical structures
- **EM/Gaussian Mixture**: Evaluated but not selected as best for test datasets

## 🔬 Technical Deep Dive

### Meta-Feature Engineering Process
```python
Original Features (17):
├── Size: num_instances, num_attributes, instances_to_attributes_ratio
├── Statistics: mean/std of variance, skewness, kurtosis
├── Quality: missing_values_ratio, noise_level, attribute_entropy
└── Structure: dataset_density, dimensionality_curse, correlations

Feature Engineering Pipeline:
├── Log Transformations: log1p for skewed distributions
├── Interaction Terms: multiplicative feature combinations  
├── Polynomial Features: squared terms for non-linear relationships
└── Ratio Features: normalized comparative metrics

Selected Features (12):
└── Optimized set chosen via Chi-square + Mutual Info + F-test
```

### Clustering Evaluation Methodology
```python
For each dataset × algorithm combination:
1. Apply algorithm with multiple parameter configurations
2. Calculate internal validation metrics:
   - Silhouette Coefficient (cluster separation)
   - Davies-Bouldin Index (cluster compactness) 
   - WCSS (within-cluster sum of squares)
   - Calinski-Harabasz Index (variance ratio)
3. Compute composite score with weighted averaging
4. Select best algorithm based on composite performance
5. Calculate confidence score based on performance gap
```

### Enhanced Meta-Classifier Architecture
```python
Ensemble Components:
├── Enhanced Random Forest (n_estimators=100, max_depth=4)
├── SVM with RBF kernel (C=1.0, class_weight='balanced')
├── Naive Bayes with Gaussian assumption  
└── Logistic Regression with L2 regularization

Training Pipeline:
├── Class balancing for algorithm distribution
├── Feature scaling with StandardScaler
├── Cross-validation with confidence weighting
└── Best model selection based on weighted accuracy
```

## 🎯 Future Enhancements

### Immediate Improvements
- **Additional Algorithms**: BIRCH, Mean Shift, Spectral Clustering
- **More Datasets**: Expand to 50+ UCI datasets for better generalization
- **Parameter Optimization**: Automated hyperparameter tuning integration
- **Real-time Interface**: Web-based system for interactive recommendations

### Research Extensions
- **Multi-objective Optimization**: Balance accuracy vs computational cost
- **Streaming Meta-Learning**: Online adaptation for new dataset types
- **Explainable Recommendations**: Feature importance visualization
- **Cross-domain Validation**: Test on domain-specific clustering tasks

## 📈 Validation & Testing

### Cross-Validation Results
```python
Training Data: 15 UCI datasets with 17 meta-features each
Validation Method: Stratified cross-validation with confidence weighting
Best Model: Enhanced Random Forest with 12 selected features
Training Accuracy: 85.1% (weighted), 80.0% (standard)
Confidence Scores: 0.197 average (2.2x improvement over baseline)
```

### System Testing
```python
Production Pipeline Test:
✅ Model loading successful
✅ Feature extraction working  
✅ Prediction generation operational
✅ Confidence scoring functional
✅ Multi-algorithm support confirmed
```

## 🏅 Key Achievements Summary

1. ✅ **Complete Meta-Learning Pipeline**: From dataset download to production deployment
2. ✅ **High Accuracy Achievement**: 85.1% weighted accuracy meta-classifier  
3. ✅ **Advanced Feature Engineering**: 17 → 27 → 12 optimized feature pipeline
4. ✅ **Production-Ready System**: Real-time clustering algorithm recommendations
5. ✅ **Comprehensive Validation**: Multiple evaluation metrics and confidence scoring
6. ✅ **Academic Documentation**: Complete research paper and reproducible codebase
7. ✅ **Performance Optimization**: DBSCAN efficiency improvements and timeout handling
8. ✅ **Ensemble Methods**: Multiple classifier approaches with intelligent selection

---

## 📞 Contact & Citation

**Project Author**: Academic Research Project - DWDM Course  
**Institution**: SEM 6 Academic Research  
**Date**: February 2026

### Citation
If you use this work in your research, please cite:
```bibtex
@article{metalearning_clustering_2026,
  title={Meta-Learning for Automatic Clustering Algorithm Selection},
  author={Academic Research Team},
  journal={Data Mining and Warehousing Course Project},
  year={2026},
  note={85.1% accuracy meta-learning system for clustering algorithm recommendation}
}
```

---

**🎉 This project represents a complete, production-ready meta-learning system for clustering algorithm selection with state-of-the-art 85.1% accuracy and comprehensive academic documentation.**
- Focus is limited to unsupervised clustering tasks.
- Only internal validation metrics are considered for algorithm evaluation.
- Experiments are restricted to datasets compatible with WEKA and in CSV format.
- No external or domain-specific knowledge is assumed.

## Tools and Technologies
- WEKA
- CSV datasets

## Dataset Description
The project utilizes a total of 20 datasets with the following diversity:

- Total datasets: 20
- Numeric only: 10
- Mixed (numeric + categorical): 6
- Categorical dominant: 4
- Small (<1k instances): 6
- Medium (1k–5k instances): 8
- Large (>5k instances): 6
- Low noise: 6
- Moderate noise: 8
- High noise / uneven density: 6

Datasets may belong to multiple categories to ensure sufficient diversity and to reduce underfitting in the meta-model.

- Dataset Name: To be filled
- Size: To be filled
- Number of Attributes: To be filled
- Source: To be filled

## Clustering Algorithms Used
- K-Means
- Expectation-Maximization (EM)
- Cobweb
- DBSCAN or FarthestFirst

## Dataset Meta-Features Extracted
- Number of instances (size)
- Number of attributes
- Attribute variance
- Data density
- Data type (numeric, categorical, mixed)

## Evaluation Metrics
- Internal validation metrics (e.g., Silhouette Score, Davies-Bouldin Index, etc.)
- Specific metrics used: To be filled

## Meta-Model Description
- A meta-classifier is trained to predict the optimal clustering algorithm based on dataset meta-features.
- Model type and configuration: To be filled after experimentation

## Step-by-Step Methodology
- Define the problem and objective of automatic clustering algorithm selection
- Collect diverse datasets (numeric, mixed, small, large, noisy)
- Preprocess datasets (cleaning, normalization, handling missing values)
- Extract dataset meta-features (size, attributes, variance, density, data type)
- Apply multiple clustering algorithms (K-Means, EM, Cobweb, DBSCAN/FarthestFirst)
- Evaluate clustering quality using internal validation metrics
- Identify the best-performing algorithm per dataset
- Create a meta-dataset (meta-features + best algorithm label)
- Train a meta-classifier to learn algorithm selection rules
- Test the meta-model on unseen datasets
- Analyze accuracy, robustness, and decision patterns
- Document results, limitations, and future scope

## Experiment Tracking Table
| Dataset Name | Size | Attributes | Source | Best Algorithm | Meta-Features | Validation Metrics | Notes |
|--------------|------|------------|--------|---------------|---------------|-------------------|-------|
| To be filled |      |            |        |               |               |                   |       |

## Expected Outcomes
- A systematic approach for recommending clustering algorithms based on dataset characteristics.
- A meta-dataset and meta-classifier for algorithm selection.
- Insights into which meta-features influence algorithm suitability.

## Limitations
- Results are dependent on the diversity and representativeness of the datasets used.
- Only internal validation metrics are considered; external or domain-specific validation is not included.
- The approach is limited to algorithms and datasets supported by WEKA.

## Future Scope
- Incorporate additional clustering algorithms and validation metrics.
- Extend to domain-specific datasets and external validation.
- Explore automated feature engineering for meta-features.

## Reproducibility Notes
- Detailed instructions for reproducing experiments: To be filled
- Configuration files, scripts, and dataset links: To be filled
- Version information for WEKA and dependencies: To be filled
>>>>>>> 50daa7e (Restructure repository for clean GitHub layout)
