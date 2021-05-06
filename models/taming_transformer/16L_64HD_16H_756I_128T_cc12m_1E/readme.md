### General Model (Example)

#### Hyperparameters

This is a model i trained on the cc12m dataset with.

```
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


#### Generations

"An armchair in the shape of an avocado. An armchair imitating an avocado" - Manually picked best of 32 generations.
