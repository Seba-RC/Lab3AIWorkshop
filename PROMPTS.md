# Common AI recommendation audit

**Reject.** Choosing the model and threshold with 2026 results and reporting those same results as an independent final test would leak evaluation information into model selection. Training through 2021 does not make 2026 independent after it has been used for tuning.
Check the notebook's configuration and threshold-selection cells and `outputs/run_manifest_v3.json`: the candidate is selected using 2022 development only, and no 2026 data are loaded.

## Truthful use / no-use record

Tool and use: ChatGPT was used to help interpret the lab instructions, draft explanations and inspect the generated development outputs.

One actual suggestion: compare `forest_sqrt` with `min_samples_leaf` changed from 30 to 100, and keep the same time split, features, seed and development threshold policy.

What we accepted/rejected: accepted this as the one additional candidate; rejected any use of 2026 results for model selection or claims that the development set is an independent test.

Exact check performed and repository evidence: ran `Lab03_ModelComparison_Student_v3.ipynb` with Restart/Run All; checked the six-system/twelve-row `comparison_table.md`, `outputs/comparison_v3.csv`, `outputs/development_predictions_v3.csv` and `outputs/run_manifest_v3.json`. The manifest records `experiment_complete: true`, `min_samples_leaf` 30 → 100 and the development-only threshold rule.

One limitation: this run used the available Python environment (3.13.5; numpy 2.3.5, pandas 2.2.3, scikit-learn 1.8.0, scipy 1.17.1, joblib 1.5.3), rather than the exact Python 3.12 environment documented as tested in README; the outputs should be reproduced in the submission environment.

## Contributions

- Contributor 1 (Álvaro): completed the controlled candidate run and drafted the experiment interpretation, failure-pattern analysis, memo and AI audit in the notebook and Markdown files.
- Contributor 2 (Sebastian): Ran the notebook on personal computer, reviewed experiment interpretation and gave ideas for improvement. Integrated own takes on interpretation.
