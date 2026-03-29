# Early Warning System for Student Mental Health

A research-oriented ML pipeline to flag students at risk of mental health decline early in the semester using synthetic questionnaire data. Includes XAI tooling to keep model behavior interpretable.

## Scope
- Purpose: Predict high-distress risk from early-semester profile data to enable proactive support.
- Data: Synthetic Student Mental Health and Burnout dataset (1,000,000 rows, 20 features).

## Early input features
Use only attributes available at semester start:
- Socio-academic: Age, gender/sex, university.
- Academic standing: Department/major, academic year/level.
- Performance & support: Current CGPA, scholarship/waiver flag.

## Risk labels (targets)
Derived from later questionnaire responses:
- Anxiety risk: High scores (2/3) on nervousness or inability to stop worrying due to academics.
- Stress risk: High frequency (3/4) of feeling upset or unable to control important academic affairs.
- Depression risk: Persistent low mood, hopelessness, or concentration trouble.
- Critical alert: Any positive response to thoughts of self-harm.

## Modeling plan
- Task: Binary classification per risk type (High vs Low) using early features.
- Baselines: Logistic Regression; stronger models: Random Forest, XGBoost.
- Imbalance handling: Class weights and SMOTE/SMOTE-NC; threshold tuning on precision-recall.
- Evaluation: PR-AUC (primary), recall at fixed precision, confusion matrix, calibration (Brier score), AUROC (secondary).

## XAI
- Global: Feature importance (gain/permutation), partial dependence/ICE for top factors.
- Local: SHAP (TreeExplainer/KernelExplainer) for case-level rationales; contrastive examples when feasible.
- Reporting: Pair each prediction with a brief factor summary (e.g., top 3 SHAP contributors).

## MLOps-lite workflow
- Split: Train/validation/test (stratified) with a temporal split if available; keep a holdout.
- Preprocess: Encode categoricals, scale numerics when needed, handle rare categories.
- Train: Cross-validated hyperparameter search with n_jobs tuned to avoid over-parallelism.
- Validate: Monitor PR-AUC, recall@precision, and calibration; check drift on key features.
- Save: Persist model, encoder, and metrics to versioned artifacts; log configs and seeds.

## Ethical and safety notes
- Synthetic data avoids PII, but treat outputs as sensitive; avoid deployment without institutional review.
- Emphasize human-in-the-loop review for any alerts; this is a research prototype, not a clinical device.

## Next steps
- Add a data dictionary mapping each column to question text and scale.
- Implement training notebook/script with metrics and SHAP plots.
- Package inference + explanation into a simple API or batch scoring job with alert thresholds.
