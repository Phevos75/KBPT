# KBPT
The code of paper KBPT: Knowledge-Based Prompt Tuning for Zero-shot Relation Triplet Extraction

![image](https://github.com/Phevos75/KBPT/blob/main/Img/Figure-1.pdf)

# Installation
Python 3.7
If your GPU uses CUDA 11, first install the specific PyTorch: pip install torch==1.10.0 --extra-index-url https://download.pytorch.org/whl/cu113
Install requirements: pip install -r requirements.txt or conda env create --file environment.yml
Download and extract the datasets here to data/
FewRel Pretrained Model (unseen=10, seed=0)
Wiki-ZSL Pretrained Model (unseen=10, seed=0)
Tactred Pretrained Model (unseen=10, seed=0)
NYT Pretrained Model (unseen=10, seed=0)