## AI Tool Usage
This project used AI assistance (e.g., ChatGPT, Co-Lab Gemini) in the following ways:

### Code Generation

#### Plotting Functions
- Functions such as `plot_confusion_matrix`, `plot_roc_curve`, and other `plot_*` utilities were initially generated using AI.  
- I manually reviewed AI-generated code for correctness, removed unused parts, added comments, and adjusted styling.

#### Helper / Utility Functions
- Helper functions like `apply_thresholds` were drafted via AI.

### Non-Code Assistance

#### Training Log Summaries
- AI summarized long training logs into aggregated metrics (F1, accuracy, etc.) to speed up analysis.  
- These summaries were used for human interpretation and debugging only.

## Sources from Course Material
- The function `plot_training_curves` was taken directly from CS372 course homework handouts.  

## Model Architecture Attribution
The ResNet architecture (ResNet18/ResNet34) is based on the work:

**He, K., Zhang, X., Ren, S., & Sun, J. (2016).  
“Deep Residual Learning for Image Recognition.”  
Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR).**

ResNet was originally developed by **Microsoft Research**.

### Citation
```bibtex
@inproceedings{he2016deep,
  title={Deep residual learning for image recognition},
  author={He, Kaiming and Zhang, Xiangyu and Ren, Shaoqing and Sun, Jian},
  booktitle={Proceedings of the IEEE conference on computer vision and pattern recognition},
  pages={770--778},
  year={2016}
}
---

## Original Work
- Model training loop  
- Data preprocessing  
- Evaluation and metric logic  
- Experiment setup and hyperparameter tuning  
- Final integration and code verification  

All above components were written manually without direct AI-generated code.
