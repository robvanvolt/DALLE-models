# DALLE-models

This repository is a collection of checkpoints for DALLE-pytorch models, from where you can keep on training or start generating images.

The idea of this repository is to make shared and continued training feasible.

The models are trained with lucidrains' DALLE-pytorch (https://github.com/lucidrains/DALLE-pytorch) code.

The folders are named after the hyperparameters used for the training, e.g.:

Models with 12 layers, 8 heads, 64 head dimensions, 128 text dimensions, 512 image dimensions are located in the following folder:

12-layers/8heads/64dim/128textdim_512imgdim/

The filenames of the models represent the model it was trained from and additional hyperparameters, e.g.:

1epoch_12M_256px_new.pt

For a new trained model for one epoch on a 12 million big dataset with an image size of at least 256xX pixels.

2epochs_12M_256px_from_1epoch_12M_256px_new.pt

This model was trained for 2 epochs with a dataset of 12 million images with an image size of at least 256 x X pixels.
