# DALLE-pytorch models

This repository is a collection of checkpoints for DALLE-pytorch models, from where you can keep on training or start generating images.

The idea of this repository is to make shared and continued training feasible.

The models are trained with lucidrains' DALLE-pytorch (https://github.com/lucidrains/DALLE-pytorch) code.

## Naming convention

The folders are named after the transformer used for training (either taming or open-ai transformer for now):

Models with 12 layers (=depth), 8 heads, 64 head dimensions, 128 text dimensions, 512 image dimensions which are trained with the taming-transformer:

`taming/12L_64HD_8H_512I_128T_cc12m_1E.pt`

The Filenames and folders contain all necessary information for "continuing" training (even though the train_dalle.py script extracts those parameters from
the provided model anyway). The last part of the filename is the number of epochs trained and the used dataset. So if another person trains with the 
same dataset for an additional epoch, he can upload the new model into the taming folder and name the dalle.pt as follows: 

`12L_64HD_8H_512I_128T_cc12m_2E.pt`

Please also provide a short description of your other training parameters used and the quality of image generations (e.g. with RM-Scores).

```EPOCHS = 20
BATCH_SIZE = 4
LEARNING_RATE = 3e-4
GRAD_CLIP_NORM = 0.5

MODEL_DIM = 512
TEXT_SEQ_LEN = 256
DEPTH = 2
HEADS = 4
DIM_HEAD = 64
REVERSIBLE = True
LOSS_IMG_WEIGHT = 7
LR_DECAY = False
