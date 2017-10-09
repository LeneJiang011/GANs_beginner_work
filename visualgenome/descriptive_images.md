# A Hierarchical Approach for Generating Descriptive Image Paragraphs  
* [[paper]](http://visualgenome.org/paper)  
Generate entire paragraphs for describing images.  

## Introduction  
* Traditional image captioning: limitation of details.  
* Dense captioning: not coherent  
* Generate paragraphs for images  
* Decompose images and paragraphs: break images into semantically meaningful regions, reason about language with a hierarchical recurrent neural network.  

### Related Work  
#### Image Captioning  
Recent methods train RNN language models conditioned on image features and sample from them to generate text.  
#### Hierarchical Recurrent Networks  
Different parts of the model operate on differen time scales.  

### Paragraphs are Different  
* Paragraph is longer and more descriptive than any one sentence.  
* A single paragraph can be more detailed than all five sentence captions, even when combined.  
* Sentence within paragraphs are substantially more diverse than sentence captions.  


### Method  
#### Overview  
* Decompose the input image by a region detector (CNN and RPN).    
* A pooled representation of compact image semantics.  
* A hierarchical RNN of two levels, a sentence RNN (generate senyence topic vectors) and a word RNN (generate sentences).  
#### Region Detector  
#### Region Pooling  
aggregate vectors into a single pooled vector  
#### Hierarchical Recurrent Network  
* Standard LSTM architecture for both the word RNN (one-layer) and the sentence RNN (two-layer).  
* Advantageous because reduces length of time for reasoning.  
#### Training and Sampling  
*x* an image and *y* a ground-truth paragraph description for that image.  
#### Transfer Learning  
* Initialize region detection network from a model trained for dense image captioning.  
* initialize the word embedding vectors, recurrent network weights, and output linear projection of the word RNN from a language model that had been trained on region-level captions.  

