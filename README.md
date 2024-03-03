# KBPT
The code of paper KBPT: Knowledge-Based Prompt Tuning for Zero-shot Relation Triplet Extraction

![Image text](https://github.com/Phevos75/KBPT/blob/main/Img/Figure-1.pdf)

# Installation
* Python 3.7
* If your GPU uses CUDA 11, first install the specific PyTorch: pip install torch==1.10.0 --extra-index-url https://download.pytorch.org/whl/cu113
* Install requirements: pip install -r requirements.txt or conda env create --file environment.yml
* Download and extract the datasets here to data/
  + FewRel Pretrained Model (unseen=10, seed=0)
  + Wiki-ZSL Pretrained Model (unseen=10, seed=0)
  + Tactred Pretrained Model (unseen=10, seed=0)
  + NYT Pretrained Model (unseen=10, seed=0)

#  Experiment Scripts
Run training in [wrapper.py](https://github.com/Phevos75/KBPT/blob/main/wrapper.py) (You can change "fewrel" to "wiki"、"Tactred"、"NYT" or unseen to 5/10/15 or seed to 0/1/2/3/4):

```
python wrapper.py main \
--path_train data/fewrel/unseen_10_seed_0/train.jsonl \                                       
--path_dev data/fewrel/unseen_10_seed_0/dev.jsonl \                                           
--path_test data/fewrel/unseen_10_seed_0/test.jsonl \                                         
--save_dir outputs/wrapper/fewrel/unseen_10_seed_0 

```

Run evaluation (Output single relation triplet)

```
python wrapper.py run_eval \                                                                                               
--path_model outputs/wrapper/fewrel/unseen_10_seed_0/extractor_final \                                                  
--path_test outputs/data/splits/zero_rte/fewrel/unseen_10_seed_0/test.jsonl \
--mode single
```

Run evaluation (Out Multiple relation triplets)

```
python wrapper.py run_eval \                                                                                               
--path_model wrapper/fewrel/unseen_10_seed_0/extractor_final \                                                  
--path_test data/fewrel/unseen_10_seed_0/test.jsonl \
--mode multi

```