# Image-to-Image Translation with Conditional Adversarial Networks  
* [[paper]](https://arxiv.org/abs/1611.07004)  
* [[code]](https://github.com/phillipi/pix2pix)  

Learn a loss function to train the mapping of input image to output image. Condition on an input image and generate a corresponding output image.  


## What to minimize  
* If Euclidean distance between predicted and ground truth, results in blurry results.  
* GAN, learn a loss that tries to classify if the output image is real or fake.  

## Related work  
### Structured losses for image modeling  
* cGANs learn a structured loss, which penalize the joint configuration of the output.  
### Conditional GANs  
* Differs in nothing is application-specific.  
* Generator used U-Net based architecture, discriminator used a convolutional PatchGAN classifier.  

## Method  
cGANs learn a mapping from observed image *x* and random noise vector *z*  
### Objective  
* Use L1 distance rather than L2 as L1 encourages less blurring.  
* Provide noise only in the form of dropout, applied on several layers of generator at both training and test time.  
### Network architectures  
Both G and D use convolution-BatchNorm-ReLu  
#### Generator with skips  
* low-level information shared between the input and output can be directly shuttled across the net.  
* Add skip connections following the general shape of a "U-Net".  
#### Markovian discriminator (PatchGAN)  
* PatchGAN only penalizes structures at the scale of patches.  
* Run convolutionally, average to provide the ultimate output.  
* Can be understood as a form of texture/style loss.  
#### Optimization and inference  
* One gradient on D and then on G, use minibatch SGD and apply the Adam solver.  

## Experiments  
* input and output simply 1-3 channel images  
* Decent results can often be obtained even on small datasets.  
### Evaluation metrics  
* Two tactics  
* "real vs fake" perceptual studies on Amazon Mechanical Turk (AMT)  
* On off-the-shelf recognition system
#### AMT perceptual studies  
Real and fake images were generated from the same grayscale input.  
#### FCN-score  
FCN-8s architecture for semantic segmentation  
### Analysis of the objective function  
labels to photo problems  
* L1 alone leads to reasonable but blurry results.  
* cGAN alone gives much sharper results.  
* L1+cGAN performs similarly well.  
### From PixelGANs to PatchGans to ImageGANs  
All experiments use 70 X 70 PatchGANs.  
* The PixelGAN has no effect on spatial sharpness, but does increase the colorfulness of the results.  
### Semantic segmentation  
First demonstration of GANs successfully generating "labels", which are nearly discrete.  

## Conclusion  
A promising approach for many image-to-image translation tasks, especially those involving highly structured graphical outputs.  