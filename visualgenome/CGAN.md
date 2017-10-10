# Conditional Generative Adversarial Nets  
* [[paper]](https://arxiv.org/abs/1411.1784)   
* [[model]](https://github.com/hwalsuklee/tensorflow-generative-model-collections/blob/master/CGAN.py)  
* [[codes based on DCGAN]](https://github.com/zhangqianhui/Conditional-Gans)  

Condition on both G and D. Can generate MNIST digits conditioned on class labels.  

## Introduction  
* GAN is to approximate many intractable probabilistic computations.  
* CGAN can direct the data generation.  
* Conditioning should be based on class labels, data for inpaiting like, data from different modality.  
* Two experiments: one on MNIST digit data conditioned on class lebels and one on MIR Flicker 25,000 dataset for multi-model learning.  

## Related Work  
### Multi-model Learning For Image Labelling  
* Leverage additional information from other modalities.  
* Use a conditional probabilistic generative model, one-to-many mapping.  

## Conditional Adversarial Nets  
### Conditional Adversarial Nets  
* Conditioned on extra information *y*  as additional input layer.  
* In G the input noise and *y* are combined in joint hidden representation.  

## Experimental Results  
### Unimodal  
* Encoded as one-hot vectors  
* ReLu to map to hidden layers, dimensionality 1200  
* G output with sigmoid unit, 784-dimensional  
* D maps *x* and *y* to a maxout layer  
* Trained with SGD with mini-batches of size 100 and initial lr of 0.1, decreased to .000001 with decay factor of 1.00004. Momentum of initial .5, increased up to 0.7. Dropout of 0.5 both to G and D.  
* Outperformed by other non-conditional architectures.  
### Multimodal  
* Pre-trained a convolutional model to get representations.  
* Traied a skip-gram model.  
* Extract image and tags features from MIR Flicker 25,000 dataset using the above two models.  
* Cosine similarity of vector representation.  

## Future Work  
* Only used tags individually.  
