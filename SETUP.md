To view the notebook/run in Co-Lab, download the .ipynb from this repository, upload to Co-Lab, and remove the first 4 cells that ask for Kaggle login/access Kaggle datasets. 

In the function "initialize_model()", replace \
`model = models.resnet34()` \
`# Construct the full path to the .pth file inside the downloaded directory` \
`weights_file_path = os.path.join(rnapark_resnet34_b627a593_pth_path, 'resnet34-b627a593.pth')` \
`state_dict = torch.load(weights_file_path, map_location="cpu")` \
`model.load_state_dict(state_dict)` with 
`model = models.resnet34(weights="DEFAULT")`


To view the notebook/run in Kaggle, copy the notebook directly via this public link: [https://www.kaggle.com/code/rnapark/apple]

Model weights can be downloaded from the Box file: https://duke.box.com/s/63d5ypmqb5kyn5e83wm7c3utd9d359yf
