### General Model (Example)

#### Download link to model

https://mega.nz/file/5PhBUCSD#kVzo_VFJde1kxPn3-cPpu2cN5dZwaBxFEO_o4hm9RSM

#### Generations

"A scenery view of a beatiful mountain" - Manually picked best of 12 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/main/models/taming_transformer/64L_64HD_8H_756I_128T_cc12m_1E/generations/2.jpg)

"A blue bird in front of a yellow wall." - Manually picked best of 12 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/main/models/taming_transformer/64L_64HD_8H_756I_128T_cc12m_1E/generations/8.jpg)

"An armchair in the shape of an avocado. An armchair imitating an avocado" - Manually picked best of 12 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/main/models/taming_transformer/64L_64HD_8H_756I_128T_cc12m_1E/generations/61.jpg)

"A t-shirt with open-ai written on it." - Manually picked best of 32 generations.

![image](https://github.com/robvanvolt/DALLE-models/blob/main/models/taming_transformer/64L_64HD_8H_756I_128T_cc12m_1E/generations/11.jpg)

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
