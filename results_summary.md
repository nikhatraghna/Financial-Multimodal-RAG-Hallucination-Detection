# Results summary - FULL run `63bb09a3131b`

Generator: `Qwen/Qwen3-VL-2B-Instruct` @ `89644892e4d85e24eaac8bacfd4f463576704203`; dataset `zhaosuifeng/FinRAGBench-V` @ `d0d65255c94e687caa81ac9da7758ed25ff046a5`.
Labels: silver (automatic reference comparison). Human-label status: PENDING.
Primary matched population: 169 test questions from 52 documents, 4 conditions each.
Deviations recorded: 1 (see deviations.json).

## Retrieval (test)
| split   | method     |   recall@1 |   recall@3 |   recall@5 |   recall@10 |   mrr@10 |   n |
|:--------|:-----------|-----------:|-----------:|-----------:|------------:|---------:|----:|
| test    | bm25       |      0.362 |      0.557 |      0.61  |       0.686 |    0.471 | 210 |
| test    | dense      |      0.352 |      0.476 |      0.529 |       0.595 |    0.427 | 210 |
| test    | hybrid_rrf |      0.371 |      0.557 |      0.629 |       0.719 |    0.482 | 210 |

## RQ1/RQ2 - answer quality by condition (matched set)
| condition   |   n |   exact_match |   numeric_accuracy |   hallucination_rate |   abstention_rate |
|:------------|----:|--------------:|-------------------:|---------------------:|------------------:|
| E1          | 169 |         0.047 |              0.29  |                0.544 |             0.166 |
| E2          | 169 |         0.071 |              0.331 |                0.497 |             0.172 |
| E3          | 169 |         0.047 |              0.249 |                0.533 |             0.219 |
| E4          | 169 |         0.089 |              0.373 |                0.42  |             0.207 |

Paired contrasts (difference in rate, 95% cluster-bootstrap CI, Holm-adjusted exact McNemar p):
- silver_halluc: E2 - E1 = -4.7% [-14.6%, 4.3%], p_holm=1 -> NOT statistically supported
- silver_halluc: E3 - E1 = -1.2% [-10.7%, 8.0%], p_holm=1 -> NOT statistically supported
- silver_halluc: E4 - E1 = -12.4% [-20.6%, -3.7%], p_holm=0.0518 -> NOT statistically supported
- silver_halluc: E3 - E2 = 3.6% [-3.1%, 10.8%], p_holm=1 -> NOT statistically supported
- silver_halluc: E4 - E2 = -7.7% [-14.1%, 0.0%], p_holm=0.213 -> NOT statistically supported
- silver_halluc: E4 - E3 = -11.2% [-18.1%, -4.1%], p_holm=0.0518 -> NOT statistically supported
- correct: E2 - E1 = 4.1% [-3.5%, 12.6%], p_holm=0.689 -> NOT statistically supported
- correct: E3 - E1 = -4.1% [-10.2%, 2.1%], p_holm=0.689 -> NOT statistically supported
- correct: E4 - E1 = 8.3% [1.3%, 15.7%], p_holm=0.174 -> NOT statistically supported
- correct: E3 - E2 = -8.3% [-15.6%, -2.2%], p_holm=0.144 -> NOT statistically supported
- correct: E4 - E2 = 4.1% [-1.3%, 8.9%], p_holm=0.689 -> NOT statistically supported
- correct: E4 - E3 = 12.4% [5.4%, 20.5%], p_holm=0.00305 -> supported

## RQ1 - frozen detectors across modalities (primary interface)
| condition   | detector   |   n |   positives |   precision |   recall |    f1 |   fpr |   auroc |
|:------------|:-----------|----:|------------:|------------:|---------:|------:|------:|--------:|
| E1          | B2         | 141 |          92 |       0.672 |    1     | 0.803 | 0.918 |   0.513 |
| E1          | B3         | 141 |          92 |       0.695 |    0.967 | 0.809 | 0.796 |   0.656 |
| E1          | B3R        | 141 |          92 |       0.659 |    0.88  | 0.753 | 0.857 |   0.514 |
| E1          | B4         | 141 |          92 |       0.661 |    0.402 | 0.5   | 0.388 |   0.536 |
| E1          | B5         | 141 |          92 |       0.736 |    0.728 | 0.732 | 0.49  |   0.631 |
| E2          | B2         | 140 |          84 |       0.618 |    1     | 0.764 | 0.929 |   0.575 |
| E2          | B3         | 140 |          84 |       0.609 |    1     | 0.757 | 0.964 |   0.652 |
| E2          | B3R        | 140 |          84 |       0.612 |    0.94  | 0.742 | 0.893 |   0.53  |
| E2          | B4         | 140 |          84 |       0.667 |    0.643 | 0.655 | 0.482 |   0.605 |
| E2          | B5         | 140 |          84 |       0.67  |    0.845 | 0.747 | 0.625 |   0.619 |
| E3          | B2         | 132 |          90 |       0.706 |    0.989 | 0.824 | 0.881 |   0.611 |
| E3          | B3         | 132 |          90 |       0.713 |    0.967 | 0.821 | 0.833 |   0.703 |
| E3          | B3R        | 132 |          90 |       0.717 |    0.9   | 0.798 | 0.762 |   0.575 |
| E3          | B4         | 132 |          90 |       0.759 |    0.489 | 0.595 | 0.333 |   0.584 |
| E3          | B5         | 132 |          90 |       0.742 |    0.8   | 0.77  | 0.595 |   0.626 |
| E4          | B2         | 134 |          71 |       0.551 |    0.986 | 0.707 | 0.905 |   0.646 |
| E4          | B3         | 134 |          71 |       0.546 |    1     | 0.706 | 0.937 |   0.756 |
| E4          | B3R        | 134 |          71 |       0.537 |    0.915 | 0.677 | 0.889 |   0.552 |
| E4          | B4         | 134 |          71 |       0.632 |    0.676 | 0.653 | 0.444 |   0.656 |
| E4          | B5         | 134 |          71 |       0.606 |    0.803 | 0.691 | 0.587 |   0.635 |

- B2: F1(E2) - F1(E1) = -0.040 [-0.112, 0.035] (CI includes 0)
- B2: F1(E3) - F1(E1) = 0.021 [-0.034, 0.080] (CI includes 0)
- B2: F1(E4) - F1(E1) = -0.096 [-0.159, -0.028]
- B3: F1(E2) - F1(E1) = -0.052 [-0.136, 0.032] (CI includes 0)
- B3: F1(E3) - F1(E1) = 0.012 [-0.048, 0.073] (CI includes 0)
- B3: F1(E4) - F1(E1) = -0.103 [-0.175, -0.027]
- B3R: F1(E2) - F1(E1) = -0.012 [-0.091, 0.072] (CI includes 0)
- B3R: F1(E3) - F1(E1) = 0.045 [-0.028, 0.118] (CI includes 0)
- B3R: F1(E4) - F1(E1) = -0.076 [-0.148, -0.001]
- B4: F1(E2) - F1(E1) = 0.155 [0.064, 0.251]
- B4: F1(E3) - F1(E1) = 0.095 [-0.006, 0.193] (CI includes 0)
- B4: F1(E4) - F1(E1) = 0.153 [0.049, 0.257]
- B5: F1(E2) - F1(E1) = 0.015 [-0.065, 0.101] (CI includes 0)
- B5: F1(E3) - F1(E1) = 0.038 [-0.060, 0.128] (CI includes 0)
- B5: F1(E4) - F1(E1) = -0.041 [-0.152, 0.067] (CI includes 0)

## RQ3 - mitigation (matched set)
| condition   | policy        |   n |   hallucination_rate |   abs_reduction |   rel_reduction |   accuracy |   abstention_rate |   selective_accuracy |   correct_answer_retention |   correction_success_rate |
|:------------|:--------------|----:|---------------------:|----------------:|----------------:|-----------:|------------------:|---------------------:|---------------------------:|--------------------------:|
| E1          | B1_unverified | 169 |                0.544 |           0     |           0     |      0.29  |             0.166 |                0.348 |                      1     |                     0     |
| E1          | B2_abstain    | 169 |                0     |           0.544 |           1     |      0.024 |             0.976 |                1     |                      0.082 |                     0     |
| E1          | B3_abstain    | 169 |                0.018 |           0.527 |           0.967 |      0.059 |             0.923 |                0.769 |                      0.204 |                     0     |
| E1          | B3R_abstain   | 169 |                0.065 |           0.479 |           0.88  |      0.041 |             0.893 |                0.389 |                      0.143 |                     0     |
| E1          | B4_abstain    | 169 |                0.325 |           0.219 |           0.402 |      0.178 |             0.497 |                0.353 |                      0.612 |                     0     |
| E1          | B5_abstain    | 169 |                0.148 |           0.396 |           0.728 |      0.148 |             0.704 |                0.5   |                      0.51  |                     0     |
| E1          | B5_correct    | 169 |                0.201 |           0.343 |           0.63  |      0.183 |             0.615 |                0.477 |                      0.551 |                     0.043 |
| E2          | B1_unverified | 169 |                0.497 |           0     |           0     |      0.331 |             0.172 |                0.4   |                      1     |                     0     |
| E2          | B2_abstain    | 169 |                0     |           0.497 |           1     |      0.024 |             0.976 |                1     |                      0.071 |                     0     |
| E2          | B3_abstain    | 169 |                0     |           0.497 |           1     |      0.012 |             0.988 |                1     |                      0.036 |                     0     |
| E2          | B3R_abstain   | 169 |                0.03  |           0.467 |           0.94  |      0.036 |             0.935 |                0.545 |                      0.107 |                     0     |
| E2          | B4_abstain    | 169 |                0.178 |           0.32  |           0.643 |      0.172 |             0.651 |                0.492 |                      0.518 |                     0     |
| E2          | B5_abstain    | 169 |                0.077 |           0.42  |           0.845 |      0.124 |             0.799 |                0.618 |                      0.375 |                     0     |
| E2          | B5_correct    | 169 |                0.112 |           0.385 |           0.774 |      0.148 |             0.74  |                0.568 |                      0.393 |                     0.036 |
| E3          | B1_unverified | 169 |                0.533 |           0     |           0     |      0.249 |             0.219 |                0.318 |                      1     |                     0     |
| E3          | B2_abstain    | 169 |                0.006 |           0.527 |           0.989 |      0.03  |             0.964 |                0.833 |                      0.119 |                     0     |
| E3          | B3_abstain    | 169 |                0.018 |           0.515 |           0.967 |      0.041 |             0.941 |                0.7   |                      0.167 |                     0     |
| E3          | B3R_abstain   | 169 |                0.053 |           0.479 |           0.9   |      0.059 |             0.888 |                0.526 |                      0.238 |                     0     |
| E3          | B4_abstain    | 169 |                0.272 |           0.26  |           0.489 |      0.166 |             0.562 |                0.378 |                      0.667 |                     0     |
| E3          | B5_abstain    | 169 |                0.107 |           0.426 |           0.8   |      0.101 |             0.793 |                0.486 |                      0.405 |                     0     |
| E3          | B5_correct    | 169 |                0.154 |           0.379 |           0.711 |      0.124 |             0.722 |                0.447 |                      0.429 |                     0.033 |
| E4          | B1_unverified | 169 |                0.42  |           0     |           0     |      0.373 |             0.207 |                0.47  |                      1     |                     0     |
| E4          | B2_abstain    | 169 |                0.006 |           0.414 |           0.986 |      0.036 |             0.959 |                0.857 |                      0.095 |                     0     |
| E4          | B3_abstain    | 169 |                0     |           0.42  |           1     |      0.024 |             0.976 |                1     |                      0.063 |                     0     |
| E4          | B3R_abstain   | 169 |                0.036 |           0.385 |           0.915 |      0.041 |             0.923 |                0.538 |                      0.111 |                     0     |
| E4          | B4_abstain    | 169 |                0.136 |           0.284 |           0.676 |      0.207 |             0.657 |                0.603 |                      0.556 |                     0     |
| E4          | B5_abstain    | 169 |                0.083 |           0.337 |           0.803 |      0.154 |             0.763 |                0.65  |                      0.413 |                     0     |
| E4          | B5_correct    | 169 |                0.112 |           0.308 |           0.732 |      0.166 |             0.722 |                0.596 |                      0.429 |                     0.014 |

- E1 halluc: B5_correct - B1 = -34.3% [-42.2%, -26.8%], p_holm=1.09e-13 -> supported
- E1 correct: B5_correct - B1 = -10.7% [-16.0%, -4.7%], p_holm=0.000534 -> supported
- E2 halluc: B5_correct - B1 = -38.5% [-46.9%, -30.1%], p_holm=2.62e-16 -> supported
- E2 correct: B5_correct - B1 = -18.3% [-24.3%, -12.9%], p_holm=7.15e-07 -> supported
- E3 halluc: B5_correct - B1 = -37.9% [-45.7%, -30.5%], p_holm=4.61e-16 -> supported
- E3 correct: B5_correct - B1 = -12.4% [-18.3%, -6.6%], p_holm=0.000148 -> supported
- E4 halluc: B5_correct - B1 = -30.8% [-39.9%, -23.5%], p_holm=1.34e-13 -> supported
- E4 correct: B5_correct - B1 = -20.7% [-26.9%, -14.8%], p_holm=5.53e-09 -> supported
- E1: B5_correct hallucination 20.1% is NOT lower than the best simple baseline (B2_abstain: 0.0%); accuracy 18.3% vs 2.4%.
- E2: B5_correct hallucination 11.2% is NOT lower than the best simple baseline (B2_abstain: 0.0%); accuracy 14.8% vs 2.4%.
- E3: B5_correct hallucination 15.4% is NOT lower than the best simple baseline (B2_abstain: 0.6%); accuracy 12.4% vs 3.0%.
- E4: B5_correct hallucination 11.2% is NOT lower than the best simple baseline (B3_abstain: 0.0%); accuracy 16.6% vs 2.4%.

## Additional dataset - FinChart-Bench QA (external, n=200, thresholds frozen)
| condition   |   n |   exact_match |   numeric_accuracy |   hallucination_rate |   abstention_rate |   numeric_accuracy_strict_1pct |
|:------------|----:|--------------:|-------------------:|---------------------:|------------------:|-------------------------------:|
| E2          | 200 |         0     |              0.185 |                0.295 |              0.52 |                          0.155 |
| E3          | 200 |         0     |              0.045 |                0.355 |              0.6  |                          0.015 |
| E4          | 200 |         0.005 |              0.25  |                0.32  |              0.43 |                          0.205 |

| condition   | detector   |   n |   positives |   precision |   recall |    f1 |   auroc |
|:------------|:-----------|----:|------------:|------------:|---------:|------:|--------:|
| E2          | B2         |  96 |          59 |       0.611 |    0.983 | 0.753 |   0.557 |
| E2          | B3         |  96 |          59 |       0.615 |    1     | 0.761 |   0.599 |
| E2          | B3R        |  96 |          59 |       0.616 |    0.898 | 0.731 |   0.499 |
| E2          | B4         |  96 |          59 |       0.605 |    0.881 | 0.717 |   0.524 |
| E2          | B5         |  96 |          59 |       0.64  |    0.932 | 0.759 |   0.532 |
| E3          | B2         |  80 |          71 |       0.886 |    0.986 | 0.933 |   0.297 |
| E3          | B3         |  80 |          71 |       0.888 |    1     | 0.94  |   0.274 |
| E3          | B3R        |  80 |          71 |       0.882 |    0.845 | 0.863 |   0.238 |
| E3          | B4         |  80 |          71 |       0.83  |    0.549 | 0.661 |   0.269 |
| E3          | B5         |  80 |          71 |       0.91  |    0.859 | 0.884 |   0.605 |
| E4          | B2         | 114 |          64 |       0.562 |    0.984 | 0.716 |   0.497 |
| E4          | B3         | 114 |          64 |       0.561 |    1     | 0.719 |   0.633 |
| E4          | B3R        | 114 |          64 |       0.579 |    0.969 | 0.725 |   0.575 |
| E4          | B4         | 114 |          64 |       0.535 |    0.844 | 0.655 |   0.493 |
| E4          | B5         | 114 |          64 |       0.588 |    0.938 | 0.723 |   0.566 |

| condition   | policy        |   n |   hallucination_rate |   abs_reduction |   rel_reduction |   accuracy |   abstention_rate |   selective_accuracy |   correct_answer_retention |   correction_success_rate |
|:------------|:--------------|----:|---------------------:|----------------:|----------------:|-----------:|------------------:|---------------------:|---------------------------:|--------------------------:|
| E2          | B1_unverified | 200 |                0.295 |           0     |           0     |      0.185 |             0.52  |                0.385 |                      1     |                         0 |
| E2          | B2_abstain    | 200 |                0.005 |           0.29  |           0.983 |      0     |             0.995 |                0     |                      0     |                         0 |
| E2          | B3_abstain    | 200 |                0     |           0.295 |           1     |      0     |             1     |              nan     |                      0     |                         0 |
| E2          | B3R_abstain   | 200 |                0.03  |           0.265 |           0.898 |      0.02  |             0.95  |                0.4   |                      0.108 |                         0 |
| E2          | B4_abstain    | 200 |                0.035 |           0.26  |           0.881 |      0.015 |             0.95  |                0.3   |                      0.081 |                         0 |
| E2          | B5_abstain    | 200 |                0.02  |           0.275 |           0.932 |      0.03  |             0.95  |                0.6   |                      0.162 |                         0 |
| E2          | B5_correct    | 200 |                0.02  |           0.275 |           0.932 |      0.03  |             0.95  |                0.6   |                      0.162 |                         0 |
| E3          | B1_unverified | 200 |                0.355 |           0     |           0     |      0.045 |             0.6   |                0.112 |                      1     |                         0 |
| E3          | B2_abstain    | 200 |                0.005 |           0.35  |           0.986 |      0     |             0.995 |                0     |                      0     |                         0 |
| E3          | B3_abstain    | 200 |                0     |           0.355 |           1     |      0     |             1     |              nan     |                      0     |                         0 |
| E3          | B3R_abstain   | 200 |                0.055 |           0.3   |           0.845 |      0.005 |             0.94  |                0.083 |                      0.111 |                         0 |
| E3          | B4_abstain    | 200 |                0.16  |           0.195 |           0.549 |      0.005 |             0.835 |                0.03  |                      0.111 |                         0 |
| E3          | B5_abstain    | 200 |                0.05  |           0.305 |           0.859 |      0.015 |             0.935 |                0.231 |                      0.333 |                         0 |
| E3          | B5_correct    | 200 |                0.06  |           0.295 |           0.831 |      0.02  |             0.92  |                0.25  |                      0.444 |                         0 |
| E4          | B1_unverified | 200 |                0.32  |           0     |           0     |      0.25  |             0.43  |                0.439 |                      1     |                         0 |
| E4          | B2_abstain    | 200 |                0.005 |           0.315 |           0.984 |      0.005 |             0.99  |                0.5   |                      0.02  |                         0 |
| E4          | B3_abstain    | 200 |                0     |           0.32  |           1     |      0     |             1     |              nan     |                      0     |                         0 |
| E4          | B3R_abstain   | 200 |                0.01  |           0.31  |           0.969 |      0.025 |             0.965 |                0.714 |                      0.1   |                         0 |
| E4          | B4_abstain    | 200 |                0.05  |           0.27  |           0.844 |      0.015 |             0.935 |                0.231 |                      0.06  |                         0 |
| E4          | B5_abstain    | 200 |                0.02  |           0.3   |           0.938 |      0.04  |             0.94  |                0.667 |                      0.16  |                         0 |
| E4          | B5_correct    | 200 |                0.02  |           0.3   |           0.938 |      0.04  |             0.94  |                0.667 |                      0.16  |                         0 |


## Hypothesis verdicts (silver labels; see Section 1b for decision rules)
| hypothesis   | test                                                                                       |   estimate | ci               | verdict       |
|:-------------|:-------------------------------------------------------------------------------------------|-----------:|:-----------------|:--------------|
| H1           | B2: F1(E2) - F1(E1)                                                                        |     -0.04  | [-0.112, 0.035]  | NOT SUPPORTED |
| H1           | B2: F1(E3) - F1(E1)                                                                        |      0.021 | [-0.034, 0.080]  | NOT SUPPORTED |
| H1           | B2: F1(E4) - F1(E1)                                                                        |     -0.096 | [-0.159, -0.028] | SUPPORTED     |
| H1           | B3: F1(E2) - F1(E1)                                                                        |     -0.052 | [-0.136, 0.032]  | NOT SUPPORTED |
| H1           | B3: F1(E3) - F1(E1)                                                                        |      0.012 | [-0.048, 0.073]  | NOT SUPPORTED |
| H1           | B3: F1(E4) - F1(E1)                                                                        |     -0.103 | [-0.175, -0.027] | SUPPORTED     |
| H1           | B3R: F1(E2) - F1(E1)                                                                       |     -0.012 | [-0.091, 0.072]  | NOT SUPPORTED |
| H1           | B3R: F1(E3) - F1(E1)                                                                       |      0.045 | [-0.028, 0.118]  | NOT SUPPORTED |
| H1           | B3R: F1(E4) - F1(E1)                                                                       |     -0.076 | [-0.148, -0.001] | SUPPORTED     |
| H1           | B4: F1(E2) - F1(E1)                                                                        |      0.155 | [0.064, 0.251]   | NOT SUPPORTED |
| H1           | B4: F1(E3) - F1(E1)                                                                        |      0.095 | [-0.006, 0.193]  | NOT SUPPORTED |
| H1           | B4: F1(E4) - F1(E1)                                                                        |      0.153 | [0.049, 0.257]   | NOT SUPPORTED |
| H1           | B5: F1(E2) - F1(E1)                                                                        |      0.015 | [-0.065, 0.101]  | NOT SUPPORTED |
| H1           | B5: F1(E3) - F1(E1)                                                                        |      0.038 | [-0.060, 0.128]  | NOT SUPPORTED |
| H1           | B5: F1(E4) - F1(E1)                                                                        |     -0.041 | [-0.152, 0.067]  | NOT SUPPORTED |
| H2           | hallucination rate E2 - E1 (matched)                                                       |     -0.047 | [-0.146, 0.043]  | NOT SUPPORTED |
| H3           | E1: B5_correct - B1 hallucination (retention=0.55)                                         |     -0.343 | [-0.422, -0.268] | NOT SUPPORTED |
| H3           | E2: B5_correct - B1 hallucination (retention=0.39)                                         |     -0.385 | [-0.469, -0.301] | NOT SUPPORTED |
| H3           | E3: B5_correct - B1 hallucination (retention=0.43)                                         |     -0.379 | [-0.457, -0.305] | NOT SUPPORTED |
| H3           | E4: B5_correct - B1 hallucination (retention=0.43)                                         |     -0.308 | [-0.399, -0.235] | NOT SUPPORTED |
| H4           | largest mean F1 drop: -arithmetic=0.000, -numeric=0.514, -period_entity=0.364, -unit=0.000 |      0.514 | descriptive      | SUPPORTED     |
| H5           | FinChart-Bench E2: B5_correct - B1 hallucination                                           |     -0.275 | [-0.338, -0.212] | SUPPORTED     |
| H5           | FinChart-Bench E3: B5_correct - B1 hallucination                                           |     -0.295 | [-0.358, -0.229] | SUPPORTED     |
| H5           | FinChart-Bench E4: B5_correct - B1 hallucination                                           |     -0.3   | [-0.363, -0.237] | SUPPORTED     |
| H5           | B2: mean F1 on FinChart-Bench (E2-E4) vs FinRAGBench-V E1                                  |     -0.003 | descriptive      | SUPPORTED     |
| H5           | B3: mean F1 on FinChart-Bench (E2-E4) vs FinRAGBench-V E1                                  |     -0.002 | descriptive      | SUPPORTED     |
| H5           | B3R: mean F1 on FinChart-Bench (E2-E4) vs FinRAGBench-V E1                                 |      0.02  | descriptive      | NOT SUPPORTED |
| H5           | B4: mean F1 on FinChart-Bench (E2-E4) vs FinRAGBench-V E1                                  |      0.178 | descriptive      | NOT SUPPORTED |

## RQ4 - ablations
| variant            | condition   |   n |   positives |   tp |   fp |   fn |   tn |   precision |   recall |      f1 |   fpr |     fnr |   halluc_rate_after_abstain |   abstain_rate_after |   accuracy_after |
|:-------------------|:------------|----:|------------:|-----:|-----:|-----:|-----:|------------:|---------:|--------:|------:|--------:|----------------------------:|---------------------:|-----------------:|
| -arithmetic        | E1          |   4 |           3 |    3 |    1 |    0 |    0 |       0.75  |    1     |   0.857 |   1   |   0     |                         0   |                  1   |            nan   |
| -arithmetic        | E2          |   3 |           2 |    2 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| -arithmetic        | E3          |   5 |           3 |    2 |    1 |    1 |    1 |       0.667 |    0.667 |   0.667 |   0.5 |   0.333 |                         0.2 |                  0.6 |            nan   |
| -arithmetic        | E4          |   2 |           1 |    1 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| -numeric           | E1          |   4 |           3 |    1 |    1 |    2 |    0 |       0.5   |    0.333 |   0.4   |   1   |   0.667 |                         0.4 |                  0.6 |            nan   |
| -numeric           | E2          |   3 |           2 |    1 |    0 |    1 |    1 |       1     |    0.5   |   0.667 |   0   |   0.5   |                         0.2 |                  0.6 |            nan   |
| -numeric           | E3          |   5 |           3 |    1 |    1 |    2 |    1 |       0.5   |    0.333 |   0.4   |   0.5 |   0.667 |                         0.4 |                  0.4 |            nan   |
| -numeric           | E4          |   2 |           1 |    0 |    0 |    1 |    1 |     nan     |    0     |   0     |   0   |   1     |                         0.2 |                  0.6 |            nan   |
| -period_entity     | E1          |   4 |           3 |    2 |    1 |    1 |    0 |       0.667 |    0.667 |   0.667 |   1   |   0.333 |                         0.2 |                  0.8 |            nan   |
| -period_entity     | E2          |   3 |           2 |    2 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| -period_entity     | E3          |   5 |           3 |    1 |    1 |    2 |    1 |       0.5   |    0.333 |   0.4   |   0.5 |   0.667 |                         0.4 |                  0.4 |            nan   |
| -period_entity     | E4          |   2 |           1 |    0 |    0 |    1 |    1 |     nan     |    0     |   0     |   0   |   1     |                         0.2 |                  0.6 |            nan   |
| -unit              | E1          |   4 |           3 |    3 |    1 |    0 |    0 |       0.75  |    1     |   0.857 |   1   |   0     |                         0   |                  1   |            nan   |
| -unit              | E2          |   3 |           2 |    2 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| -unit              | E3          |   5 |           3 |    2 |    1 |    1 |    1 |       0.667 |    0.667 |   0.667 |   0.5 |   0.333 |                         0.2 |                  0.6 |            nan   |
| -unit              | E4          |   2 |           1 |    1 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| full               | E1          |   4 |           3 |    3 |    1 |    0 |    0 |       0.75  |    1     |   0.857 |   1   |   0     |                         0   |                  1   |            nan   |
| full               | E2          |   3 |           2 |    2 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| full               | E3          |   5 |           3 |    2 |    1 |    1 |    1 |       0.667 |    0.667 |   0.667 |   0.5 |   0.333 |                         0.2 |                  0.6 |            nan   |
| full               | E4          |   2 |           1 |    1 |    0 |    0 |    1 |       1     |    1     |   1     |   0   |   0     |                         0   |                  0.8 |            nan   |
| full (+correction) | E1          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  0.8 |              0.2 |
| -correction        | E1          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  1   |              0   |
| full (+correction) | E2          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  0.8 |              0.2 |
| -correction        | E2          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  0.8 |              0.2 |
| full (+correction) | E3          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0.2 |                  0.6 |              0.2 |
| -correction        | E3          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0.2 |                  0.6 |              0.2 |
| full (+correction) | E4          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  0.8 |              0.2 |
| -correction        | E4          |   5 |         nan |  nan |  nan |  nan |  nan |     nan     |  nan     | nan     | nan   | nan     |                         0   |                  0.8 |              0.2 |

## Figures
- fig1_hallucination_by_modality
- fig2_detector_prf_by_modality
- fig3_mitigation_comparison
- fig4_error_categories
- fig5_ablations
- fig6_tradeoff
- fig7_confusion_b5
- fig9_additional_dataset
- fig8_failure_cases