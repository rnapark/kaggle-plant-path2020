*These setup instructions are for verification of Kaggle performance. Any outputs/training logs/interpretations can be viewed directly through the notebooks in notebooks.*

## For lightweight notebook
The "lightweight notebook" just downloads my pretrained model's fold weights and uses them to generate a submission.

I've uploaded the pre-trained model weights to Duke Box here(https://duke.box.com/s/6b1enqvyv6enew6ocnso3n6bm73kwf8d), please download this folder, then create a dataset in Kaggle by uploading it. 

To create a dataset in Kaggle, go to >Datasets in the left options bar, select Create New Dataset, and upload the folder of fold weights you downloaded from the Box link, naming the folder `model_fold_weights` or update the notebook weight download to use a different path, as it is set to `torch.load(f"/kaggle/input/model-fold-weights/fold_{k}.pth"`.
![alt text](https://github.com/rnapark/kaggle-plant-path2020/blob/8d7885e3b52db67c0df4f701be94dee059d7a765/docs/images/create_dataset.png)

Copy this notebook that uses the downloaded model weights [https://www.kaggle.com/code/rnapark/lightweight-apple], and "add input" on the sidebar from your newly created dataset above, filtering for "Your Work" and "Datasets". Submit to competition to see the score. 

![alt_text](https://github.com/rnapark/kaggle-plant-path2020/blob/8d7885e3b52db67c0df4f701be94dee059d7a765/docs/images/add_input.png)
![alt text](https://github.com/rnapark/kaggle-plant-path2020/blob/8d7885e3b52db67c0df4f701be94dee059d7a765/docs/images/add_input_filter.png)

## For the original notebook
The original notebook contains all the details and technical components of my model,including the training loop and inference together. It should be sufficient just to view the notebook here [notebooks/apple_final.ipynb](https://github.com/rnapark/kaggle-plant-path2020/blob/1482e791d8706b7c51a799245f8905afc4fb14f8/notebooks/apple_final.ipynb), as it contains all the training logs and code. 

To view the notebook/run in Kaggle, copy the notebook directly via this public link: [https://www.kaggle.com/code/rnapark/apple], but before running, you must create a dataset as described for the lightweight version, using the ResNet34 pretrained weights, Box link here: https://duke.box.com/s/bfmqoollw98uet47iamcg2tinqgagq86. Please also name the folder `resnet34-b627a593.pth` as the code downloads the weights from `torch.load("/kaggle/input/resnet34-b627a593-pth/resnet34-b627a593.pth`. The training and inference should finish in between 2-3 hours.
