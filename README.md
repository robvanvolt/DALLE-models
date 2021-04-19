# DALLE-models
Here is a collection of checkpoints for DALLE-pytorch models, from where you can keep on training or start generating images.

The folders are named after the hyperparameters used for the training, e.g.:


The filenames of the models represent the model it was trained from and additional hyperparameters, e.g.:

1epoch_12M_256px_new.pt

For a new trained model for one epoch on a 12 million big dataset with an image size of at least 256xX pixels.

2epochs_12M_256px_from_1epoch_12M_256px_new.pt

This model was trained for 2 epochs with a dataset of 12 million images with an image size of at least 256 x X pixels.
