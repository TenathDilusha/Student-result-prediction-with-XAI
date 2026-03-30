# Predict Students' Dropout and Academic Success

## Overview
This project uses machine learning to predict student dropout and academic success in higher education. The dataset, sourced from a Portuguese higher education institution, contains demographic, academic, and socio-economic information for 4,424 students across various undergraduate degrees. The goal is to identify students at risk of dropping out or failing, enabling early intervention.

## Dataset
- **Source:** UCI Machine Learning Repository ([DOI: 10.24432/C5MC89](https://doi.org/10.24432/C5MC89))
- **Instances:** 4,424 students
- **Features:** 36 (real, categorical, integer)
- **Target:** Three categories — dropout, enrolled, graduate (imbalanced classes)
- **No missing values**
- **Recommended split:** 80% train, 20% test

### Variables
The dataset includes:
- Academic path (course, application mode/order, previous qualification)
- Demographics (age, gender, nationality, marital status)
- Socio-economic factors (parents' education/occupation, scholarship, tuition status)
- Academic performance (grades, curricular units, evaluations)

See the [UCI dataset page](https://archive.ics.uci.edu/ml/datasets/Predict+Students%27+Dropout+and+Academic+Success) for full variable descriptions.

## Usage
### Installation
Install dependencies (see `requirements.txt` or use pip):
```bash
pip install pandas scikit-learn xgboost matplotlib seaborn
```

### Data Loading Example
```python
import pandas as pd
df = pd.read_csv('dataset/processed_dataset.csv')
```

### Model Training Example
See `notebooks/main.ipynb` for full workflow:
- Data preprocessing
- Feature selection (RFECV)
- Model training (RandomForest, XGBoost)
- Evaluation (accuracy, classification report, confusion matrix)

## Citation
If you use this dataset, please cite:

M.V. Martins, D. Tolledo, J. Machado, L. M.T. Baptista, V. Realinho. (2021) "Early prediction of student’s performance in higher education: a case study" Trends and Applications in Information Systems and Technologies, vol.1, Advances in Intelligent Systems and Computing series. Springer. DOI: 10.1007/978-3-030-72657-7_16

## License
This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.

## Keywords
Academic performance, Imbalanced classes, Multi-class classification, Dropout prediction

## Contact
- Valentim Realinho, Instituto Politécnico de Portalegre
- Mónica Vieira Martins, Instituto Politécnico de Portalegre
- Jorge Machado, Instituto Politécnico de Portalegre
- Luís Baptista, Instituto Politécnico de Portalegre
