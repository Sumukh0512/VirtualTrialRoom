# VirtualTrialRoom
Final Year Project

# Installation
This implementation is built and tested in PyTorch 0.4.1. Pytorch and torchvision are recommended to install with conda: conda install pytorch=0.4.1 torchvision=0.2.1 -c pytorch
For all packages, run pip install -r requirements.txt

# Data Preparation
For training/testing VITON dataset, full and processed dataset is available here: https://1drv.ms/u/s!Ai8t8GAHdzVUiQQYX0azYhqIDPP6?e=4cpFTI. After downloading, unzip to your data directory.

# Training
You get pre trained models from here : https://1drv.ms/u/s!Ai8t8GAHdzVUiQA-o3C7cnrfGN6O?e=EaRiFP .
Otherwise you can train the models manually by following these given steps below:

# Training GMM
python train.py --name GMM --stage GMM --workers 4 --save_count 5000 --shuffle ->[this training process time takes long about 10 hours].
Then run test.py for GMM network with the training dataset, which will generate the warped clothes and masks in "warp-cloth" and "warp-mask" folders inside the "result/GMM/train/" directory. Copy the "warp-cloth" and "warp-mask" folders into your data directory, for example inside "data/train" folder.
Run TOM stage, python train.py --name TOM --stage TOM --workers 4 --save_count 5000 --shuffle
