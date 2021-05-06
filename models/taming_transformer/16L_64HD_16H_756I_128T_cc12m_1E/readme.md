### General Model (Example)

#### Download link to model

https://mega.nz/file/kShC2QjR#5BEPvrouy89XgRFo130hYdSLZu_hyz9s7oWUnhQsXb4

#### Generations

"An armchair in the shape of an avocado. An armchair imitating an avocado" - Manually picked best of 32 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_756I_128T_cc12m_1E/generations/avocado_armchair.jpg)

#### Hyperparameters

This is a model was trained on the cc12m dataset with.

```
16_BIT_PRECISION = True
BATCH_SIZE = 42
LEARNING_RATE = 3e-4
GRAD_CLIP_NORM = 0.9

MODEL_DIM = 756           
TEXT_SEQ_LEN = 128 
DEPTH = 16                    
HEADS = 16               
DIM_HEAD = 64           
REVERSIBLE = False
LOSS_IMG_WEIGHT = 7
LR_DECAY = False
ATTN_TYPES = ('full', 'sparse')
```
