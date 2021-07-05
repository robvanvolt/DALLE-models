# Trained Dall-E models

**This repository is a collection of checkpoints for DALLE-pytorch models**, from where you can keep on training or start generating images.

- The idea of this repository is to make shared and continued training feasible and in the long run determine the best model and hyperparameters.

These models were trained via lucidrains' [DALLE-pytorch.](https://github.com/lucidrains/DALLE-pytorch)

---

<p align="center">
  <strong>Inference models via Colab | Discord server</strong>
</p>

<p align="center">

  <a href="https://colab.research.google.com/drive/1b8va5g852hq3p7yro7xWY3Cc-bd2CRdv">
         <img alt="Open in colab" src="https://colab.research.google.com/assets/colab-badge.svg">
  </a>
  
  <a href="https://discord.gg/dall-e">
    <img alt="Join us on Discord" src="https://img.shields.io/discord/823813159592001537?color=5865F2&logo=discord&logoColor=white">
  </a>

</p>

<p align="center">
  <a>Host models on a demo site for inferencing via <a href="https://github.com/rom1504/dalle-service">dalle-service</a></a>
</p>

## Naming convention and metadata
### **1. Foldernames**
---
### **Stem**

The folders are named after the transformer used for training (either taming or open-ai transformer for now):

Models with 12 layers (=depth), 8 heads, 64 head dimensions, 128 text dimensions, 512 image dimensions which are trained with the taming-transformer:

`taming/12L_64HD_8H_512I_128T_cc12m_1E`

The Filenames and folders contain all necessary information for "continuing" training (even though the train_dalle.py script extracts those parameters from
the provided model anyway). The batch size is not included in the filename, as you can continue training on the models with a higher batch size if you have a better GPU for example. The same rule applies for the other hyperparameters listed below, which are not part of the filename. 

So if another person trains with the same dataset for an additional epoch, he can upload the new model into the taming folder and name the subfolder as follows: 

`12L_64HD_8H_512I_128T_cc12m_2E.pt`

### **Epochs**
The last part of the filename/folder is the number of epochs trained and the used dataset - it is the total count of epochs trained on given dataset, so you you train for 2 epochs on a model that was already trained for 3x2 epochs, the last part of the filename is 8E = 8 total number of epochs trained. If you train on a different dataset, just add the name of the dataset and the number of epochs trained. The following model was trained 2 epochs on the conceptual images dataset and one epoch on the wit dataset: 

`12L_64HD_8H_512I_128T_cc12m-2E_wit-1E.pt`

### 2. Hyperparameters
---
Provide a short description of your other training parameters used and the quality of image generation (e.g. with RM-Scores and examples of the generations) like this:

```EPOCHS = 1
BATCH_SIZE = 20
LEARNING_RATE = 3e-4
GRAD_CLIP_NORM = 0.9

MODEL_DIM = 512                   # image dimensions,           "512I"
TEXT_SEQ_LEN = 256                # text dimensions,            "128T"
DEPTH = 12                        # number of layers,            "12L"
HEADS = 8                         # number of heads,              "8H"
DIM_HEAD = 64                     # number of head dimensions,  "64HD"
REVERSIBLE = True
LOSS_IMG_WEIGHT = 7
LR_DECAY = False
ATTN_TYPES = ('full', 'sparse')
```

### 3. Generation capabilities and quality
---
Optionally, you may provide examples of generated images and quantitative metrics of your uploaded model.

### **General model** _(e.g. cc12m, yfcc100m, wit or alike used for training)_ 
* "An armchair in the shape of an avocado. An armchair imitating an avocado."
* "A red tshirt with a black circle drawn on it."
* "People playing soccer on a field."

### **Specific model** _(e.g. CUB200 birds or a fashion dataset used for training)_
* depending on your domain, generate a few examples with a text input which is not part of your training dataset

### 4. Datasets
---
If you want to train on your own and do not want to make a big fuss about downloading and preparing the datasets, you can use helper scripts which automate a large part of the dataset-generations:

> https://github.com/robvanvolt/DALLE-datasets
