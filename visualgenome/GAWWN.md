# Learning What and Where to Draw  
* [[paper]](https://arxiv.org/abs/1610.02454?context=cs)  

## Introduction  
* Current approaches only used simple conditioning varibles, and did not allow for controlling where objects appear in the scene.  
* Proposed model learns to perform location and content-controllable image synthesis.  


## Generative Adversarial What-Where Networks  
bounding-box- and keypoint-conditional GAWWN  
### Bounding-box-conditional text-to-image model  
* Concatenate the coarse spatial structure with the noise vector *z*.  
* Generator branches into local and global processing stages.  
### Keypoint-conditional text-to-image model  
* The keypoint tensor is fed into several stafes of the network. Noise-text-keypoint vector.  
### Conditional keypoint generation model  
* assign each object part observed and unobserved as a gating mechanism.  


## Experiments  
* Eecode the captions using a pre-trained char-CNN-CRU.  
* Average four randomly-sampled caption encodings.  
* Training: ADAM solver with batch size 16 and learning rate 0.0002.  

## Discussion  
Showed how to generate images conditioned on both informal text descriptions and object locations.  
