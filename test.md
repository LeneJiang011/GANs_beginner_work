# Policy Gradient-enhanced Scene Graph GAN  
##  Dependencies  
Since the original codes from [mklawonn](https://github.com/mklawonn/Scene-Graph-GAN) is super ambiguious, we choose special dependencies as well as processing method. Before you start, please make sure you have all the following installed.  
- Python 2.7  
- TensorFlow r0.11  
- h5py  
- numpy  
- threading  
- Queue  
- json  
- argparse  
- gc  
- requests  
- time  
- tqdm  
- CUDA 7.5  
While confronting problems of downloading older versions of tensorflow, you may refer to this [site](https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.11.0-cp-none-linux_x86_64.whl). Such as simply run  
`install https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.11.0-cp-none-linux_x86_64.whl`  
For differences between tf0.11 and tf1.0, refer to [image1](https://raw.githubusercontent.com/LeneJiang011/GANs_beginner_work/master/images/tf0.11-1.0.png) and [image2](https://raw.githubusercontent.com/LeneJiang011/GANs_beginner_work/master/images/tf0.11-1.0-2.png).  

## Preprocessing
- While confronting protocol problems, try to add `export PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python`, especially before you compile the `recreateXuEtAlSplit.py`.  
- The original code directly used vocabulary from [Scene Graph Generation by Iterative Message Passing](https://github.com/danfeiX/scene-graph-TF-release/blob/master/README.md), which we found it not enough for the GAN approach. You may use files from the folder `build_vocab` to reconstruct the vocabulary, and we have already added one named `vocab.json` in it.  
- We suppose download the datasets needed one by one rather than directly run the code.  

## Train  
- Run `train.py`  
- Run `test.py`
- Run `postprocessing\drawing.py`  