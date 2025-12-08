# Plant Pathology: Identifying foliar diseases in apple trees

The goal of this project is to develop a machine learning model that accurately identifies and classifies foliar diseases in apple trees from images of their leaves. 

## What it does

This project was developed as part of a 2020 Kaggle competition, where the challenge was to detect different types of leaf diseases in apple trees. Accurate and efficient disease identification can significantly reduce resource expenditure, economic losses, and environmental impacts associated with crop diseases. My project uses a convolutional neural network architecture via transfer learning on a ResNet34 to identify the presence of/type of foliar disease in apple trees from images of leaves. I fine-tuned the pre-trained model to be able to distinguish differences in condition despite variations in depth, lighting, and symptoms. Improving the efficiency and accuracy of detecting crop diseases using an ML model can minimize the cost of resources that goes into environmental monitoring as well as economic loss and environmental impacts. 

## Quick Start
Please look at v29 of https://www.kaggle.com/code/rnapark/apple or [notebooks/apple_final.ipynb](https://github.com/rnapark/kaggle-plant-path2020/blob/1482e791d8706b7c51a799245f8905afc4fb14f8/notebooks/apple_final.ipynb) to see the detailed implementation of my project, complete with training logs and visualizations.

To run the project, I've created a "lightweight notebook" at https://www.kaggle.com/code/rnapark/lightweight-apple where you can just download/upload my pretrained model's fold weights to generate a Kaggle submission. Please follow the detailed version of instructions in SETUP.md. 

Otherwise, to see the training logs and error/success visualizations, metric visualizations, reference [notebooks/apple_final.ipynb](https://github.com/rnapark/kaggle-plant-path2020/blob/1482e791d8706b7c51a799245f8905afc4fb14f8/notebooks/apple_final.ipynb). 

## Video Links

**5 min demo**: https://duke.box.com/s/cc62cj1jlzghh5m6d3dorz3rqy5a2k7u

**10 min technical walkthrough**: https://duke.box.com/s/6q216n42jjlvpx4eco5xp1rqffkkrxko 

## Evaluation

*These metrics are based off the full version of the notebook(apple_final.ipynb) that does both training and inference within the notebook. Due to some inconsistencies I was not able to identify, the lightweight version of the notebook was only able to get a Kaggle score of 0.90, posted this concern on Ed post #207.*

**Kaggle best score**: 0.95428 using V29
![alt text](https://github.com/rnapark/kaggle-plant-path2020/blob/001325ba2cd9f48710e9043e6a2719ddc635331a/docs/images/kaggle_score.png)

**Overall Accuracy:** 0.8704

**Precision per class:** [0.89043478 0.34756098 0.93072289 0.9379085 ]

**Recall per class:** [0.99224806 0.62637363 0.99356913 0.96959459]

**F1-score per class:** [0.93858845 0.44705882 0.96111975 0.95348837]

**Macro ROC AUC:** 0.9581

**Training curves**: ![alt text](https://github.com/rnapark/kaggle-plant-path2020/blob/1d8e7baf2a2d9cb691147f8c8b59082a6f116b69/docs/images/training_curve_eval.png)

**Average Validation Accuracy across all folds:** 0.9232

Qualitative inspection revealed that most misclassifications occurred for the multiple_diseases class, which is consistent with its lower Macro-F1 score across folds. Many errors involved images with occluded leaves, overlapping disease symptoms, or bad lighting. Often, ground truth labels were ambiguous even to humans, suggesting that some dataset noise contributes to lower performance on multiple_diseases. High-confidence correct predictions for healthy, rust, and scab classes typically displayed strong color contrast and clear lesion patterns, reflecting their consistently high F1-scores.
