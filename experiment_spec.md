# Expectation for one additional candidate

The five base results were supplied. This expectation concerns my additional run.

- Base model: `forest_sqrt`
- Parameter and old → new value: `min_samples_leaf`, 30 → 100.
- Conditions held fixed: training seasons 2018–2021; development on the first eleven rounds of 2022; supplied CSV and nine permitted features unchanged; seed 414; same preprocessing and random-forest family; same development-only threshold rule with a maximum 10% alert budget; selected development threshold reused unchanged on train.
- Have you already run this additional candidate? **No** at the time this expectation was recorded.
- Expected effect and mechanism: Increasing the minimum samples required in a leaf should make individual tree leaves less specific and reduce model complexity. I expect the candidate may produce a more conservative or smoother score ranking, potentially reducing false alerts, but it may also miss more distinct pit entries. Because the threshold is reselected on development, I do not expect the alert count or threshold to remain identical. These are hypotheses, not guaranteed outcomes.
- Other trials already made: No other additional configurations tried before this candidate.
