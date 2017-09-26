#Improved Training of Wasserstein GANs  
[paper](https://arxiv.org/abs/1704.00028)   [code](https://github.com/igul222/improved_wgan_training)  

Introduction
---
* WGAN uses weight clipping to enforce a Lipschitz constraint on the critic (discriminator), which can lead to pathological behavior.
* Propose an alternative: Gradient Penalty.  

Difficulties with weight constraints  
---
Problem caused by simpler functions:
* Experiment: Generator distribution fixed at real distribution plus unit-variance Gaussian noise. Omit batch normalization in the critic. 
* Results: WGAN ignores the data distribution to model simple approximations.  

Problem with Gradients:
* Experiment: Vary the clipping threshold. Both G and D (critic) are 12-layer ReLU MLPs without BN.  
* Results: Either vanishing or exploding gradients.  

Gradient Penalty
---
An alternative way to enforce the Lipscgits constraint: constrain the gradient norm of the critic's output with respect to its input.  
Settings:  
* Sample the penalized distribution along straight lines between pair points sampled from the data distribution and generator distribution.
* Penalty coefficient uses 10.
* Omit BN in the critic. Recommend layer normalization as a replacement.
* Two-sided penalty: from both below 1 and above 1 (towards 1)

Experiments  
---
WGAN with gradient penality: replace any BN in the D with layer normalization.  
Superiorty:  
* Compared to original WGAN: improved training speed and sample quality, preserve the property that their loss correlates with sample quality and converges towards a minimum.  
* Compared to DCGAN: more stable
* Compared to GANs with G log-likelihood to measure overfitting: detect overfitting in the critic, which is faster and easier
* Discrete sampling achievements: first reported result without a supervised maximum-likelihood, only apply a softmax nonlinearity at the output.  
NOTE that the difference lies in that the data distribution is discrete whereas the generator distribution is continuous.  

Future work  
---
* Stronger modeling performance on large-scale image datasets and language.  
* Adapt the penality term to standard GAN objective function.  

Code  
---
Struggling to understand...  

---
Thanks for reading!

