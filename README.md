# Plant Pathology: Identifying foliar diseases in apple trees

My project was working on a 2020 Kaggle competition, which involved identifying the type of foliar diseases in apple trees from images of their leaves. 

## What it does
My project uses a convolutional neural network architecture via transfer learning on a ResNet34 to identify the presence of/type of foliar disease in apple trees from images of leaves. I fine-tuned the pre-trained model to be able to distinguish differences in condition despite variations in depth, lighting, and symptoms. Improving the efficiency and accuracy of detecting crop diseases using an ML model can minimize the cost of resources that goes into environmental monitoring as well as economic loss and environmental impacts. 

## Quick Start
https://www.kaggle.com/code/rnapark/apple  

## Video Links

## Evaluation

**Kaggle best score**: 0.95428 using V29

**Overall Accuracy:** 0.8704

**Precision per class:** [0.89043478 0.34756098 0.93072289 0.9379085 ]

**Recall per class:** [0.99224806 0.62637363 0.99356913 0.96959459]

**F1-score per class:** [0.93858845 0.44705882 0.96111975 0.95348837]

**Macro ROC AUC:** 0.9581

Training curves: ![alt text](https://github.com/rnapark/kaggle-plant-path2020/blob/1d8e7baf2a2d9cb691147f8c8b59082a6f116b69/docs/images/training_curve_eval.png)

**Average Validation Accuracy across all folds:** 0.9232

Qualitative inspection revealed that most misclassifications occurred for the multiple_diseases class, which is consistent with its lower Macro-F1 score across folds. Many errors involved images with occluded leaves, overlapping disease symptoms, or bad lighting. Often, ground truth labels were ambiguous even to humans, suggesting that some dataset noise contributes to lower performance on multiple_diseases. High-confidence correct predictions for healthy, rust, and scab classes typically displayed strong color contrast and clear lesion patterns, reflecting their consistently high F1-scores.
