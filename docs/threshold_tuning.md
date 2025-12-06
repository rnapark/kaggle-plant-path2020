# Evidence of tuning hyperparameters

## Configuration 1
Using thresholds = [0.5, 0.6, 0.4, 0.7] for classes ['healthy','multiple_diseases','rust','scab']) in corresponding order

### Fold 1/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 103     | 14                | 123    | 112    |
| **False Positives (FP)** | 9       | 42                | 11     | 3      |
| **False Negatives (FN)** | 0       | 4                 | 2      | 7      |
| **True Negatives (TN)**  | 253     | 305               | 229    | 243    |
| **Precision**            | 0.9196  | 0.2500            | 0.9179 | 0.9739 |
| **Recall**               | 1.0000  | 0.7778            | 0.9840 | 0.9412 |


### Fold 2/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 103     | 10                | 124    | 111    |
| **False Positives (FP)** | 18      | 15                | 3      | 8      |
| **False Negatives (FN)** | 0       | 8                 | 0      | 8      |
| **True Negatives (TN)**  | 243     | 331               | 237    | 237    |
| **Precision**            | 0.8512  | 0.4000            | 0.9764 | 0.9328 |
| **Recall**               | 1.0000  | 0.5556            | 1.0000 | 0.9328 |

### Fold 3/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 102     | 11                | 124    | 109    |
| **False Positives (FP)** | 18      | 37                | 5      | 6      |
| **False Negatives (FN)** | 1       | 8                 | 0      | 9      |
| **True Negatives (TN)**  | 243     | 308               | 235    | 240    |
| **Precision**            | 0.8500  | 0.2292            | 0.9612 | 0.9478 |
| **Recall**               | 0.9903  | 0.5789            | 1.0000 | 0.9237 |


### Fold 4/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 104     | 12                | 124    | 110    |
| **False Positives (FP)** | 7       | 25                | 10     | 3      |
| **False Negatives (FN)** | 0       | 6                 | 0      | 8      |
| **True Negatives (TN)**  | 253     | 321               | 230    | 243    |
| **Precision**            | 0.9369  | 0.3243            | 0.9254 | 0.9735 |
| **Recall**               | 1.0000  | 0.6667            | 1.0000 | 0.9322 |

### Fold 5/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 102     | 12                | 124    | 102    |
| **False Positives (FP)** | 20      | 22                | 10     | 1      |
| **False Negatives (FN)** | 1       | 6                 | 1      | 16     |
| **True Negatives (TN)**  | 241     | 324               | 229    | 245    |
| **Precision**            | 0.8361  | 0.3529            | 0.9254 | 0.9903 |
| **Recall**               | 0.9903  | 0.6667            | 0.9920 | 0.8644 |

### Interpretation

The Healthy class performs pretty well with the 0.5 threshold, though I would try nearby values to see how this changes. 

The Multiple Diseases class has lower precision, with more false positives, so I might raise the threshold. 

The Rust class has high precision and recall, but I might adjust the value up to reduce false positives, precision could still be improved.

The Scab class has high precision but lower recall, so the threshold is likely too high. I will try lowering this value.

## Configuration 2
Using thresholds = [0.6, 0.65, 0.4, 0.45] for classes ['healthy','multiple_diseases','rust','scab']) in corresponding order

### Fold 1/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 102     | 8                 | 124    | 116    |
| **False Positives (FP)** | 8       | 16                | 12     | 4      |
| **False Negatives (FN)** | 1       | 10                | 1      | 3      |
| **True Negatives (TN)**  | 254     | 331               | 228    | 242    |
| **Precision**            | 0.9273  | 0.3333            | 0.9118 | 0.9667 |
| **Recall**               | 0.9903  | 0.4444            | 0.9920 | 0.9748 |

### Fold 2/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 103     | 8                 | 121    | 113    |
| **False Positives (FP)** | 12      | 21                | 2      | 8      |
| **False Negatives (FN)** | 0       | 10                | 3      | 6      |
| **True Negatives (TN)**  | 249     | 325               | 238    | 237    |
| **Precision**            | 0.8957  | 0.2759            | 0.9837 | 0.9339 |
| **Recall**               | 1.0000  | 0.4444            | 0.9758 | 0.9496 |

### Fold 3/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 100     | 11                | 124    | 112    |
| **False Positives (FP)** | 9       | 17                | 12     | 8      |
| **False Negatives (FN)** | 3       | 8                 | 0      | 6      |
| **True Negatives (TN)**  | 252     | 328               | 228    | 238    |
| **Precision**            | 0.9174  | 0.3929            | 0.9118 | 0.9333 |
| **Recall**               | 0.9709  | 0.5789            | 1.0000 | 0.9492 |

### Fold 4/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 103     | 11                | 124    | 115    |
| **False Positives (FP)** | 7       | 13                | 8      | 11     |
| **False Negatives (FN)** | 1       | 7                 | 0      | 3      |
| **True Negatives (TN)**  | 253     | 333               | 232    | 235    |
| **Precision**            | 0.9364  | 0.4583            | 0.9394 | 0.9127 |
| **Recall**               | 0.9904  | 0.6111            | 1.0000 | 0.9746 |

### Fold 5/5
| Metric                   | Healthy | Multiple Diseases | Rust   | Scab   |
| ------------------------ | ------- | ----------------- | ------ | ------ |
| **True Positives (TP)**  | 101     | 11                | 124    | 107    |
| **False Positives (FP)** | 18      | 12                | 16     | 3      |
| **False Negatives (FN)** | 2       | 7                 | 1      | 11     |
| **True Negatives (TN)**  | 243     | 334               | 223    | 243    |
| **Precision**            | 0.8487  | 0.4783            | 0.8857 | 0.9727 |
| **Recall**               | 0.9806  | 0.6111            | 0.9920 | 0.9068 |


### Interpretation

Overall, I want to prioritize precision and recall evenly(any false is equally bad), so I compared the F1-scores of the two configurations.

The F1 scores for the Healthy threshold varied between configurations and folds, but the 0.6 threshold showed slightly higher F1 scores overall.

I increased the threshold to 0.65 from 0.6 for Multiple Diseases, and 0.6 seemed to have better recall(however, this means more false positives), while 0.65 had better precision(but this means more false negatives). The second configuration had the better F1 score.

I've kept the threshold for Rust the same, and I think it is good enough to keep consistent. 

The Scab does better at 0.45 than 0.7, so I experimented with lowering past this as well.
