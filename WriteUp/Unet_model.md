## Unet Model

### Motivation
The Unet model was initially created for image segmentation problems, where it outputs a complete high resolution image in which all the pixels are classified. We can tailor the unet model to categorizing galaxies, as it learns the ?what? info, or galaxy parameters, and captures the ?where? info, or the shape, orientation, and centering of the galaxies. 

![](Unet_model/unet-architecture.png)

This is the unet model architecture from the original paper<a id="note1" href="#note1ref"><sup>1</sup></a>. The Structure is similar to autoencoder, where it has an encoder and decoder. In the encoder the Image size reduces as depth increases. In the Decoder, the image size increases as depth increases. It also includes skip connections by combining output of feature maps from Encoder convolution layers at same level. We make modifications by flattening the last convolution layer and adding a dense layer to output our 5 learned parameters. We also added batch normalization layers to the encoder, and compiled the model with a learning rate scheduler.

### Prediction Results

#### Noisy Simulated Data

![](Unet_model/noisy_preds.png)

![](Unet_model/snr_preds.png)

#### Non-noisy Simulated Data



<a id="note1" href="#note1ref"><sup>1</sup></a>[Ronneberger et al](https://arxiv.org/pdf/1505.04597.pdf)