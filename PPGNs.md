# Plug & Play Generative Networks: Conditional Interative Generation of Images in Latent Space
* [[paper]](https://arxiv.org/abs/1612.00005)  
* [[code]](https://github.com/Evolving-AI-Lab/ppgn)  

## Introduction
* Limitation with DGN-AM: the lack of diversity in the generated samples.  
* PPGNs: energy-based model, an energy function with different priors and conditions.  

## PPGNs  
Experiment with 4 learned prior modeled by a DAE.  
* PPGN-x: poor modeling of data distribution, the chain mixes slowly.  
* DGN-AM: without a learned prior, but feature from pre-trained classification network. Same problem with original DGN-AM.  
* PPGN-h: learn the prior by the DAE with noise. Still lack quality and quantity.  
* Joint PPGN-h: composed of 3 interleaved DAEs that share parameters, noises added to three variables, 4-loss combination. Better performance.  
* Noiseless Joint PPGN-h: best model is without noise and with three losses. Better image quality, but mixes slightly slower than Joint PPGN-h.  


## Additional Results  
with Noiseless Joint PPGN-h  
* Conditioned On classes: sample with an AlexNet DNN.  
* On captions: swap in an image-captioning recurrent network (IRCN).  
* On hidden neurons  
* On part of an image: can filling in missing pixels.  
