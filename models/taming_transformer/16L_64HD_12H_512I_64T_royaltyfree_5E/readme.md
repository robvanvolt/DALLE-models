### `royalty_free.pt`

This checkpoint was trained on roughly 600,000 captioned images from conceptual captions 12m. 

The idea was to see if visual concepts could be inferred downstream if enough accurately trained.

I haven't had the time to explore it fully but it's a fun checkpoint.

This checkpoint uses W&B open-source tier for free hosting.


## W&B Host

### Python download
You may download it with `wandb` like this:

```python
import wandb
run = wandb.init()
artifact = run.use_artifact('dalle-pytorch-replicate/royalty_free_illustrations/trained-dalle:v7', type='model')
artifact_dir = artifact.download()
```

#### Download link

If you just want a link - either of these should work.
```
https://wandb.ai/dalle-pytorch-replicate/royalty_free_illustrations/artifacts/model/trained-dalle/a10e0559eeea1a3cbd83/files

https://api.wandb.ai/artifactsV2/gcp-us/dalle-pytorch-replicate/QXJ0aWZhY3Q6MTA0ODUwNzQ=/5650cbc9c98793cd3d185645ee4d1552
```

#### Generations

From the end of the training session:
![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_756I_128T_cc12m_1E/generations/training.png)

Two cherrypicked results which were particularly good.
![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_756I_128T_cc12m_1E/generations/cherrypicked.png)


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
