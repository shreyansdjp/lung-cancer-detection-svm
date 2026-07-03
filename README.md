# Lung Cancer Detection SVM

A machine learning project that predicts lung cancer risk using Support Vector Machine (SVM) classification. This project uses **uv** for dependency management and **VS Code** for development.

## Overview

This project builds a predictive model to identify lung cancer risk based on patient survey data. The model uses an SVM classifier with hyperparameter tuning to achieve optimal performance. The dataset contains 16 attributes from 284 patient instances, including smoking habits, medical symptoms, and demographic information.

## Tech Stack

- **Language**: Python 3.14+
- **Package Manager**: [uv](https://docs.astral.sh/uv/) - Fast Python package installer and resolver
- **IDE**: [VS Code](https://code.visualstudio.com/) - Recommended development environment
- **ML Libraries**: scikit-learn, pandas

## Getting Started with uv & VS Code

### Prerequisites

- [VS Code](https://code.visualstudio.com/) installed
- [uv](https://docs.astral.sh/uv/getting-started/installation/) installed

### Setup

1. **Open the project in VS Code**:
   ```bash
   code .
   ```

2. **Install dependencies with uv**:
   ```bash
   uv sync
   ```
   This automatically creates a virtual environment and installs all required packages from `pyproject.toml`.

3. **Select the uv Python interpreter in VS Code**:
   - Press `Cmd+Shift+P` (or `Ctrl+Shift+P` on Linux/Windows)
   - Search for "Python: Select Interpreter"
   - Choose the interpreter from the `.venv` directory created by uv

4. **Open the Jupyter notebook**:
   - VS Code will automatically detect `main.ipynb`
   - Click "Run All" or run cells individually

## Project Structure

```
.
├── main.ipynb                    # Main Jupyter notebook with analysis
├── pyproject.toml               # uv project configuration
├── README.md                    # This file
└── data/
    └── survey lung cancer.csv   # Dataset (284 instances, 16 attributes)
```

## Dataset Features

The lung cancer survey dataset includes:

- **Demographic**: Gender, Age
- **Lifestyle**: Smoking, Alcohol consumption, Peer pressure
- **Medical Symptoms**: Yellow fingers, Anxiety, Chronic disease, Fatigue, Allergy, Wheezing, Coughing, Shortness of breath, Swallowing difficulty, Chest pain
- **Target**: Lung cancer (YES/NO)

## Model Pipeline

The project uses an SVM pipeline with:

1. **Data Preprocessing**: 
   - Encoding categorical variables (Gender, Target)
   - Normalizing numerical values
   - Feature standardization with `StandardScaler`

2. **SVM Classifier**:
   - Kernel: Polynomial (degree=3)
   - Class weighting: Balanced
   - Hyperparameter tuning via GridSearchCV

3. **Hyperparameter Optimization**:
   - C parameter: [0.01, 0.1, 1, 10, 100]
   - Gamma: [1e-4, 1e-3, 1e-2, 1e-1, 1, 'scale']
   - 5-fold cross-validation with balanced accuracy scoring

## Running the Analysis

In VS Code with the notebook open:
- **Run all cells**: Click "Run All" button or press `Ctrl+Alt+Enter`
- **Run individual cells**: Click the play button on each cell
- **View outputs**: Results, confusion matrices, and classification reports display inline

## Dependencies

Managed by uv in `pyproject.toml`:

- `pandas>=3.0.4` - Data manipulation and analysis
- `scikit-learn>=1.9.0` - Machine learning algorithms and utilities

To add new dependencies:
```bash
uv pip install <package-name>
```

## Development Notes

- The notebook performs all analysis in a single flow: data loading → preprocessing → model training → hyperparameter tuning
- Results include classification reports and confusion matrices for model evaluation
- The project uses stratified train-test split (80/20) for balanced class distribution

## VS Code Recommended Extensions

- Python (Microsoft)
- Jupyter (Microsoft)
- Pylance (optional, for enhanced type checking)

---

**Project**: Lung Cancer Detection SVM  
**Status**: Coursework (CBA-GH)  
**Last Updated**: 2026
