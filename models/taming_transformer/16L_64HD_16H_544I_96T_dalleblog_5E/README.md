# Training a DALL-E on... generations from DALL-E?

by [afiaka87](https://github.com/afiaka87)

(tl;dr) https://www.dropbox.com/s/x9gbxiartrqaewf/afiaka_544I_96TSL_12D_16H_64DH_sparse.zip

Remember [the day our minds were blown by OpenAI](https://openai.com/blog/dall-e/)? 

That blog post was so cool to me. I've been chasing after an armchair in the shape of an avocado ever since then. 
I dug through the HTML/JS on the site and found a cryptic URL parser which I ran through the JS debugger while refreshing the page until I could write a Python script to figure out the format of the URLs. 
I really didn't expect much, just to grab what they had. You see, the images on the site are tricky to right click -> save as image. That was my primary motivation. 
I left my scraping script running overnight and woke up to *1.1 million generations* from OpenAI's DALL-E. OpenAI presented the top 32 of 512 outputs as reranked by their as-of-yet unreleased CLIP. This means there are about 30,000 unique captions in this dataset which _each_ get their own 32 individual fairly accurate, CLIP-ranked paired images. This makes this dataset _super_ simple to fit - it has more than enough info on each caption and all of the images are very clean. 

#### Download link
The following link includes a normal `dalle.pt`.

I've also included my `dalle-ds-cp` folder which has the DeepSpeed training session's Adam optimizer states and the WarmupLRDecay Scheduler states stored on them. This might prove useful if you wish to finetune this checkpoint. 

https://www.dropbox.com/s/x9gbxiartrqaewf/afiaka_544I_96TSL_12D_16H_64DH_sparse.zip

#### Colab/Linux Download
```sh
$ wget --no-clobber https://www.dropbox.com/s/x9gbxiartrqaewf/afiaka_544I_96TSL_12D_16H_64DH_sparse.zip
$ unzip afiaka_544I_96TSL_12D_16H_64DH_sparse.zip
$ cd afiaka_544I_96TSL_12D_16H_64DH_sparse/ 
$ ls . 
dalle.pt
dalle-ds-cp
auxiliary.pt
latest
vocab.bpe
```

#### Generations

"a female mannequin dressed in an olive button-down shirt and gold palazzo pants"

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_544I_96T_dalleblog_5E/generations/mannequin.png)

"a photo of westwood park, san francisco, from the water in the afternoon"

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_544I_96T_dalleblog_5E/generations/photo.png)

"an emoji of a baby penguin wearing a blue hat, blue gloves, red shirt, and green pants"

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_544I_96T_dalleblog_5E/generations/conceptual.png)

"the exact same teapot on the top colored yellow on the bottom"

![image](https://github.com/robvanvolt/DALLE-models/blob/0507632824d38417ff0c40bbb5c37a4858c56afe/models/taming_transformer/16L_64HD_16H_544I_96T_dalleblog_5E/generations/style_transfer.png)


#### Hyperparameters 

```sh
DIM 544 
TEXT_SEQ_LEN 96 
DEPTH 12 
HEADS 16 
ATTN_TYPES ('sparse')
DIM_HEAD 64 
LEARNING_RATE 3E-4 
RANDOM_RESIZE_CROP_LOWER_RATIO 1.0 
LOSS_IMG_WEIGHT 1 # This seems to work well, but perhaps only in the overfitting regime where your captions are _very_ clean
ATTN_DROPOUT 0.01 
FF_DROPOUT 0.01 
TAMING 
VQGAN_CONFIG_PATH vqgan_imagenet_f16_16384.yaml 
VQGAN_MODEL_PATH vqgan_imagenet_f16_16384.ckpt 
BATCH_SIZE 24
KEEP_N_CHECKPOINTS 10 
FP16 
```