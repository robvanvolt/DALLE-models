### General Model (Example)

#### Download link to model

https://mega.nz/file/5PhBUCSD#kVzo_VFJde1kxPn3-cPpu2cN5dZwaBxFEO_o4hm9RSM

#### Generations

"An armchair in the shape of an avocado. An armchair imitating an avocado" - Manually picked best of 32 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_756I_128T_cc12m_1E/generations/avocado_armchair.jpg)

#### Hyperparameters

This is model was trained on the cc12m dataset.

```
AMP = True
16_BIT_PRECISION = False
EPOCHS = 1
BATCH_SIZE = 40
LEARNING_RATE = 4.5e-4
GRAD_CLIP_NORM = 0.9

MODEL_DIM = 756
TEXT_SEQ_LEN = 128
DEPTH = 64
HEADS = 8
DIM_HEAD = 64
REVERSIBLE = True
LOSS_IMG_WEIGHT = 7
LR_DECAY = False
```
